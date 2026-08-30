# Plots time activity curves from 1 or 2 participants or groups.

Plots time activity curves from 1 or 2 participants or groups.

## Usage

``` r
# S3 method for class 'tac'
plot(x, tac2 = NULL, ROIs, ymax = 25, time = "minutes",
  title = "", colors = rainbow, ...)
```

## Arguments

- x:

  A tac object containing time-activity curves to plot, e.g. from
  tac_roi() or load_tac()

- tac2:

  An optional, second TAC, to plot for comparison

- ROIs:

  A vector of ROIs to plot, names matching the TAC headers

- ymax:

  The maximum value on the y-axis

- time:

  "seconds" or "minutes" depending on desired x-axis, converts tac

- title:

  A title for the plot

- colors:

  If null, rainbow palette is used, otherwise another palette can be
  specified (heat.colors, terrain.colors, topo.colors, cm.colors

- ...:

  Additional arguments

## Value

Creates a plot

## See also

Other tac functions:
[`save_tac`](https://docs.ropensci.org/tacmagic/reference/save_tac.md),
[`split_pvc`](https://docs.ropensci.org/tacmagic/reference/split_pvc.md),
[`tac_roi`](https://docs.ropensci.org/tacmagic/reference/tac_roi.md)

## Examples

``` r
# f_raw_tac and f_raw_vol are the filenames of PMOD-generated files
f_raw_tac <- system.file("extdata", "AD06.tac", package="tacmagic") 
f_raw_vol <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")

tac <- load_tac(f_raw_tac)
vol <- load_vol(f_raw_vol)
AD06_tac_nc <- tac_roi(tac, vol, roi_ham_full(), merge=FALSE, PVC=FALSE)
plot(AD06_tac_nc, ROIs=c("frontal", "cerebellum"), title="Example Plot")
```
