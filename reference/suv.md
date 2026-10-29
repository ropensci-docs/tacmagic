# Calculate average SUV over time window, or maximum SUV

Calculate the standardized uptake value (SUV) from a tac object, the
participant's weight, and the tracer dose. These values may be in the
tac object or manually supplied. The weight must be in kg, and the
tracer units must be specified. The dose is converted to MBq, the tac is
converted to kBq/cc, and the final SUV units are thus in g/cc. Aside
from the tac object, the remaining parameters should be left NULL if the
required data is in the tac object attributes (as can be done with
batch_load()).

## Usage

``` r
suv(tac, SUV_def, dose = NULL, dose_unit = NULL, weight_kg = NULL,
  ...)
```

## Arguments

- tac:

  time-activity curve object (decay-corrected)

- SUV_def:

  vector of start times for window for SUV weighted average, or
  alternatively, "max" for the maximum ROI SUV value

- dose:

  the injected tracer dose

- dose_unit:

  unit of tracer dose (e.g. "MBq", "kBq", "mCi"...)

- weight_kg:

  the participant's weight in kg

- ...:

  When called from tm_batch, unused parameters may be supplied

## Value

table of SUV values

## See also

Other SUV functions:
[`tac_suv`](https://docs.ropensci.org/tacmagic/reference/tac_suv.md)

## Examples

``` r
f <- system.file("extdata", "AD06.tac", package="tacmagic")
fv <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")
AD06_tac <- load_tac(f, format="PMOD")
AD06_volume <- load_vol(fv, format="voistat")
AD06 <- tac_roi(tac=AD06_tac, volumes=AD06_volume, ROI_def=roi_ham_pib(),
                merge=FALSE, PVC=FALSE)
# dose and weight are fabricated for the example
AD06_suvmax <- suv(AD06, "max", dose = 9.0, dose_unit = "mCi",
                     weight_kg = 70)
AD06_suv <- suv(AD06, c(3000, 3300, 3600), dose = 9.0, dose_unit = "mCi",
                  weight_kg = 70)
```
