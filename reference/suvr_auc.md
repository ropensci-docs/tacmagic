# Calculate SUVRs for regions of interest with AUC from mid-frame times

Calculate the standardized uptake value ratio (SUVR) for all ROIs in the
provided tac data, using the specified reference region. This is an
alternate to suvr() which should provide very similar values.

## Usage

``` r
suvr_auc(tac, SUVR_def, ref, ...)
```

## Arguments

- tac:

  The time-activity curve data from tac_roi()

- SUVR_def:

  a vector of start times for window to be used in SUVR

- ref:

  is a string, e.g. "cerebellum", to specify reference region

- ...:

  When called from tm_batch, unused parameters may be supplied

## Value

A data.frame of SUVR values for the specified ROIs \#' f \<-
system.file("extdata", "AD06.tac", package="tacmagic") fv \<-
system.file("extdata", "AD06_TAC.voistat", package="tacmagic") AD06_tac
\<- load_tac(f, format="PMOD") AD06_volume \<- load_vol(fv,
format="voistat") AD06 \<- tac_roi(tac=AD06_tac, volumes=AD06_volume,
ROI_def=roi_ham_pib(), merge=FALSE, PVC=FALSE)

AD06_SUVR \<- suvr_auc(AD06, SUVR_def=c(3000,3300,3600),
ref="cerebellum")

## See also

Other SUVR functions:
[`suvr`](https://docs.ropensci.org/tacmagic/reference/suvr.md)
