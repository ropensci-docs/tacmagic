# Calculate SUV from TAC

Calculate the standardized uptake value (SUV) time-activity curve from a
tac object, the participant's weight, and the tracer dose. The weight
must be in kg, and the tracer dose must be specified. The dose is
converted to MBq, the tac is converted to kBq/cc, and the final SUV
units are thus in g/cc. Aside from the tac object, the remaining
parameters should be left NULL if the required data is in the tac object
attributes (as can be done with batch_load().

## Usage

``` r
tac_suv(tac, dose = NULL, dose_unit = NULL, weight_kg = NULL)
```

## Arguments

- tac:

  time-activity curve object (decay-corrected)

- dose:

  the injected tracer dose

- dose_unit:

  unit of tracer dose (e.g. "MBq", "kBq", "mCi"...)

- weight_kg:

  the participant's weight in kg

## Value

tac object with SUV values

## See also

Other SUV functions:
[`suv`](https://docs.ropensci.org/tacmagic/reference/suv.md)

## Examples

``` r
f <- system.file("extdata", "AD06.tac", package="tacmagic")
fv <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")
AD06_tac <- load_tac(f, format="PMOD")
AD06_volume <- load_vol(fv, format="voistat")
AD06 <- tac_roi(tac=AD06_tac, volumes=AD06_volume, ROI_def=roi_ham_pib(),
                merge=FALSE, PVC=FALSE)
# dose and weight are fabricated for the example
AD06_suv <- tac_suv(AD06, dose = 9.0, dose_unit = "mCi", weight_kg = 70)
```
