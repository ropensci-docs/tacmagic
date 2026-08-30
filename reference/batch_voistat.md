# Obtain values from voistat files (using load_voistat() for a batch.

For a vector of participant IDs and correspondingly named .voistat
files, this extracts the value from the files for the specified ROIs.
participants can also be a vector of filenames, in which case set dir=""
and filesuffix="", as in the example.

## Usage

``` r
batch_voistat(participants, ROI_def, dir = "", filesuffix = ".voistat",
  varname = "VALUE")
```

## Arguments

- participants:

  A vector of participant IDs

- ROI_def:

  Object that defines combined ROIs, see ROI_definitions.R

- dir:

  Directory and/or filename prefix of the files

- filesuffix:

  Optional filename characters between ID and ".voistat"

- varname:

  The name of the variable being extracted, e.g. "SRTM"

## Value

A table of values for the specified ROIs for all participants

## Details

See load_voistat() for specifics.

## See also

Other Batch functions:
[`batch_load`](https://docs.ropensci.org/tacmagic/reference/batch_load.md),
[`batch_tm`](https://docs.ropensci.org/tacmagic/reference/batch_tm.md)

## Examples

``` r
participants <- c(system.file("extdata", "AD06_BPnd_BPnd_Logan.voistat", 
                              package="tacmagic"),
                   system.file("extdata", "AD07_BPnd_BPnd_Logan.voistat", 
                               package="tacmagic"),
                   system.file("extdata", "AD08_BPnd_BPnd_Logan.voistat", 
                               package="tacmagic"))

batchtest <- batch_voistat(participants=participants, ROI_def=roi_ham_pib(), 
                           dir="", filesuffix="", varname="Logan") 
```
