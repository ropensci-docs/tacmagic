# Reads PMOD .voistat files and optionally merges volume-weighted ROIs

PMOD can produce .voistat files with the average model values by ROI for
its voxelwise binding potential (BPnd) models, such as Logan, SRTM, etc.
This function reads the .voistat file and returns a data.frame with the
ROI as rows and the model value as the column. Optionally, the ROIs can
be combined into larger ROIs if ROI_def is specified, just as with TAC
loading.

## Usage

``` r
load_voistat(filename, ROI_def = NULL, model = "VALUE")
```

## Arguments

- filename:

  (e.g. participant_logan.voistat)

- ROI_def:

  Optional ROI definitions to combine ROIs (e.g. roi_ham_pib())

- model:

  A string to name the variable being extracted, e.g. "Logan_DVR"

## Value

data.frame with loaded model data in specified combined weighted ROIs

## See also

Other Loading functions:
[`as.tac`](https://docs.ropensci.org/tacmagic/reference/as.tac.md),
[`load_tac`](https://docs.ropensci.org/tacmagic/reference/load_tac.md),
[`load_vol`](https://docs.ropensci.org/tacmagic/reference/load_vol.md)

## Examples

``` r
f <- system.file("extdata", "AD06_BPnd_BPnd_Logan.voistat", 
                 package="tacmagic")
vs <- load_voistat(f, ROI_def=roi_ham_pib(), model="Logan")
```
