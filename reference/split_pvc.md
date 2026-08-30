# Subset PMOD tacs with or without PVC

When partial volume correction (PVC) is used in PMOD, the saved tac
files have ROIs with and without PVC. When loaded with load_tac()) it
may be desirable to keep only either the PVC or non-PVC tacs. This
returns a tac object that is a subset of the input tac object with only
the PVC or non-PVC tacs. This relies on PMOD's convention of labelling
tac columns with "\_C".

## Usage

``` r
split_pvc(tac, PVC = TRUE)
```

## Arguments

- tac:

  The time-activity curve data from loading function (PMOD)

- PVC:

  If TRUE, includes columns with "\_C", if FALSE, ones without "\_C"

## Value

Time-activity curve object

## See also

Other tac functions:
[`plot.tac`](https://docs.ropensci.org/tacmagic/reference/plot.tac.md),
[`save_tac`](https://docs.ropensci.org/tacmagic/reference/save_tac.md),
[`tac_roi`](https://docs.ropensci.org/tacmagic/reference/tac_roi.md)

## Examples

``` r
# f_raw_tac and f_raw_vol are the filenames of PMOD-generated files
f_raw_tac <- system.file("extdata", "AD06.tac", package="tacmagic") 

tac <- load_tac(f_raw_tac)
tac_pvc <- split_pvc(tac, TRUE)
tac_nc <- split_pvc(tac, FALSE)
```
