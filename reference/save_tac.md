# Save a tac object as a .tac file

Saves a tac object, created by load_tac(), tac_roi() or manually, and
saves it as a PMOD-formatted tac file. Using the .tac extension in the
file name is recommended.

## Usage

``` r
save_tac(tac, outfile)
```

## Arguments

- tac:

  The time-activity curve data, e.g. from load_tac() or tac_roi()

- outfile:

  The output filename

## Value

Does not return an object, only saves a file

## See also

Other tac functions:
[`plot.tac`](https://docs.ropensci.org/tacmagic/reference/plot.tac.md),
[`split_pvc`](https://docs.ropensci.org/tacmagic/reference/split_pvc.md),
[`tac_roi`](https://docs.ropensci.org/tacmagic/reference/tac_roi.md)
