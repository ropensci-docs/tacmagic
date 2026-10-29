# Non-invasive reference Logan plot

This plots the non-invasive Logan plot.

## Usage

``` r
# S3 method for class 'ref_Logan'
plot(x, ...)
```

## Arguments

- x:

  Reference Logan model data object from DVR_ref_Logan()

- ...:

  Additional parameters than can be passed to plotting function

## Value

No return f \<- system.file("extdata", "AD06.tac", package="tacmagic")
fv \<- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")
AD06_tac \<- load_tac(f, format="PMOD") AD06_volume \<- load_vol(fv,
format="voistat") AD06 \<- tac_roi(tac=AD06_tac, volumes=AD06_volume,
ROI_def=roi_ham_pib(), merge=FALSE, PVC=FALSE) AD06_DVR_fr \<-
DVR_ref_Logan(AD06, target="frontal", ref="cerebellum", k2prime=0.2,
t_star=0) plot(AD06_DVR_fr)

## See also

Other Logan plot functions:
[`DVR_all_ref_Logan`](https://docs.ropensci.org/tacmagic/reference/DVR_all_ref_Logan.md),
[`DVR_ref_Logan`](https://docs.ropensci.org/tacmagic/reference/DVR_ref_Logan.md),
[`dvr`](https://docs.ropensci.org/tacmagic/reference/dvr.md)
