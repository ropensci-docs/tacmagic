# Distribution volume ratio (DVR) for one or more ROIs

This calculates the DVR using the non-invasive reference Logan method
for all TACs in a supplied tac file. It uses DVR_ref_Logan if a target
ROI is specified, otherwise will calculate DVR for all ROIs with
DVR_ref_all_Logan()

## Usage

``` r
dvr(tac, model = "logan", target = NULL, ref, k2prime, t_star,
  error = 0.1, method = "trapz")
```

## Arguments

- tac:

  The time-activity curve data from load_tac() or tac_roi()

- model:

  Only model currently available is "logan"

- target:

  Optional - otherwise will calculate DVR for all regions

- ref:

  Required – The reference region, e.g. "cerebellum"

- k2prime:

  Required – A fixed value for k2' must be specified (e.g. 0.2)

- t_star:

  Required – If 0, t\* will be calculated using find_t_star()

- error:

  For find_t_star()

- method:

  Method of integration, "trapz" or "integrate"

## Value

Data frame with calculated DVRs

## Details

For other model parameters, directly call DVR_ref_Logan().

## References

Logan, J., Fowler, J. S., Volkow, N. D., Wang, G.-J., Ding, Y.-S., &
Alexoff, D. L. (1996). Distribution Volume Ratios without Blood Sampling
from Graphical Analysis of PET Data. Journal of Cerebral Blood Flow &
Metabolism, 16(5), 834-840.
https://doi.org/10.1097/00004647-199609000-00008

## See also

Other Logan plot functions:
[`DVR_all_ref_Logan`](https://docs.ropensci.org/tacmagic/reference/DVR_all_ref_Logan.md),
[`DVR_ref_Logan`](https://docs.ropensci.org/tacmagic/reference/DVR_ref_Logan.md),
[`plot.ref_Logan`](https://docs.ropensci.org/tacmagic/reference/plot.ref_Logan.md)

## Examples

``` r
f <- system.file("extdata", "AD06.tac", package="tacmagic")
fv <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")
AD06_tac <- load_tac(f, format="PMOD")
AD06_volume <- load_vol(fv, format="voistat")
AD06 <- tac_roi(tac=AD06_tac, volumes=AD06_volume, ROI_def=roi_ham_pib(),  
                merge=FALSE, PVC=FALSE)  

AD06_DVRs <- dvr(AD06, ref="cerebellum", k2prime=0.2, t_star=23)
#> Trying leftfrontal
#> Trying rightfrontal
#> Trying lefttemporal
#> Trying righttemporal
#> Trying leftparietal
#> Trying rightparietal
#> Trying leftoccipital
#> Trying rightoccipital
#> Trying leftcingulate
#> Trying rightcingulate
#> Trying frontal
#> Trying temporal
#> Trying parietal
#> Trying occipital
#> Trying cingulate
#> Trying cerebellum
#> Trying totalcortical
#> Trying leftdeep
#> Trying rightdeep
#> Trying deep
#> Trying ventricles
#> Trying whitematter
#> Trying amyloidcomp

AD06_DVR <- dvr(AD06, target="frontal", ref="cerebellum", 
             k2prime=0.2, t_star=23)
```
