# Loads ROI volumes from file for use by other functions

Loads ROI volumes from file for use by other functions

## Usage

``` r
load_vol(filename, format = "voistat")
```

## Arguments

- filename:

  (e.g. participant.voistat)

- format:

  (default is the TAC .voistat format from PMOD, also accepts "DFT and
  "BPndPaste")

## Value

data.frame with loaded TAC data

## See also

Other Loading functions:
[`as.tac`](https://docs.ropensci.org/tacmagic/reference/as.tac.md),
[`load_tac`](https://docs.ropensci.org/tacmagic/reference/load_tac.md),
[`load_voistat`](https://docs.ropensci.org/tacmagic/reference/load_voistat.md)

## Examples

``` r
f_raw_vol <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")

vol <- load_vol(f_raw_vol)
```
