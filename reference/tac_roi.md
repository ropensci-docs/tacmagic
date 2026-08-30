# Calculate weighted time-activity curves for specified regions of interest

Calculate weighted time-activity curves for specified regions of
interest

## Usage

``` r
tac_roi(tac, volumes, ROI_def, merge, PVC)
```

## Arguments

- tac:

  The time-activity curve data from loading function

- volumes:

  The ROI volume data from loading function

- ROI_def:

  The definition of ROIs by combining smaller ROIs from TAC file

- merge:

  If TRUE, includes the original ROIs in the output data

- PVC:

  If TRUE, appends "\_C" to ROI name header (as in PMOD TAC files)

## Value

Time-activity curves for the specified ROIs

## See also

Other tac functions:
[`plot.tac`](https://docs.ropensci.org/tacmagic/reference/plot.tac.md),
[`save_tac`](https://docs.ropensci.org/tacmagic/reference/save_tac.md),
[`split_pvc`](https://docs.ropensci.org/tacmagic/reference/split_pvc.md)

## Examples

``` r
# f_raw_tac and f_raw_vol are the filenames of PMOD-generated files
f_raw_tac <- system.file("extdata", "AD06.tac", package="tacmagic") 
f_raw_vol <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")

tac <- load_tac(f_raw_tac)
vol <- load_vol(f_raw_vol)
AD06_tac_nc <- tac_roi(tac, vol, roi_ham_full(), merge=FALSE, PVC=FALSE)
```
