# Load (+/- merge) ROIs for batch of participants

For a vector of participant IDs and correspondingly named tac files,
this loads the tac files. If roi_m = T, then can also merge ROIs into
larger ROIs based on the optional parameters that follow.

## Usage

``` r
batch_load(participants, dir = "", tac_file_suffix = ".tac",
  tac_format = "PMOD", roi_m = FALSE, PVC = NULL,
  vol_file_suffix = NULL, vol_format = NULL, merge = NULL,
  ROI_def = NULL, tracer_dose = NULL, dose_unit = NULL,
  weight_kg = NULL)
```

## Arguments

- participants:

  A vector of participant IDs

- dir:

  A directory and/or file name prefix for the tac/volume files

- tac_file_suffix:

  How participant IDs corresponds to the TAC files

- tac_format:

  Format of tac files provided: See load_tac()

- roi_m:

  TRUE if you want to merge atomic ROIs into larger ROIs (and if not,
  the following parameters are not used)

- PVC:

  For PVC, true where the data is stored as \_C in same tac file

- vol_file_suffix:

  How participant IDs correspond to volume files

- vol_format:

  The file format that includes volumes: See load_vol()

- merge:

  Passes value to tac_roi(); T to also incl. original atomic ROIs

- ROI_def:

  Object that defines combined ROIs, see ROI_definitions.R

- tracer_dose:

  optionally, a vector of tracer doses (in the same order as
  participants), for SUV

- dose_unit:

  if tracer_dose is specified, note the unit (e.g "MBq")

- weight_kg:

  optionally, a vector of participant weights in kg, for SUV

## Value

A list of data.frames, each is a participant's TACs

## Details

See load_tac() for specifics.

## See also

Other Batch functions:
[`batch_tm`](https://docs.ropensci.org/tacmagic/reference/batch_tm.md),
[`batch_voistat`](https://docs.ropensci.org/tacmagic/reference/batch_voistat.md)

## Examples

``` r
# For the working example, the participants are full filenames.
participants <- c(system.file("extdata", "AD06.tac", package="tacmagic"),
                  system.file("extdata", "AD07.tac", package="tacmagic"),
                  system.file("extdata", "AD08.tac", package="tacmagic"))

tacs <- batch_load(participants, tac_file_suffix="")
```
