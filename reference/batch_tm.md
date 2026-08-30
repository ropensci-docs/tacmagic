# Calculate one or more models for a batch of participants

For a list of tac data (from load_batch) this calculates specified
models and saves in a tidy data.frame. Current model options are "SUVR",
"Logan".

## Usage

``` r
batch_tm(all_tacs, models, custom_model = NULL, ...)
```

## Arguments

- all_tacs:

  A list by participant, of tac data (load_batch())

- models:

  A vector of names of the models to calculate

- custom_model:

  A function that can be run like other models (advanced)

- ...:

  The arguments that get passed to the specified models/custom model,
  many are required; please check with model desired.

## Value

A table of SUVR values for the specified ROIs for all participants

## Details

For further details about how the models are calculated, see the
individual functions that they rely on. "SUVR" uses suvr(), "Logan" uses
DVR_all_ref_Logan().

## See also

Other Batch functions:
[`batch_load`](https://docs.ropensci.org/tacmagic/reference/batch_load.md),
[`batch_voistat`](https://docs.ropensci.org/tacmagic/reference/batch_voistat.md)

## Examples

``` r
participants <- c(system.file("extdata", "AD06.tac", package="tacmagic"),
                  system.file("extdata", "AD07.tac", package="tacmagic"),
                  system.file("extdata", "AD08.tac", package="tacmagic"))

tacs <- batch_load(participants, tac_file_suffix="")

# Keeps only the ROIs without partial-volume correction (PMOD convention)
tacs <- lapply(tacs, split_pvc, FALSE)

batch <- batch_tm(tacs, models=c("SUVR", "Logan"), ref="Cerebellum_r",
                  SUVR_def=c(3000,3300,3600), k2prime=0.2, t_star=23)
```
