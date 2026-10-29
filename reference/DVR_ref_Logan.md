# Non-invasive reference Logan method

This calculates the coefficient from the non-invasive Logan method,
which is equal to DVR. Works for a single tac (target).

## Usage

``` r
DVR_ref_Logan(tac_data, target, ref, k2prime, t_star, error = 0.1,
  method = "trapz")
```

## Arguments

- tac_data:

  The time-activity curve data from tac_roi()

- target:

  The name of the target ROI, e.g. "frontal"

- ref:

  The reference region, e.g. "cerebellum"

- k2prime:

  A fixed value for k2' must be specified (e.g. 0.2)

- t_star:

  If 0, t\* will be calculated using find_t_star()

- error:

  For find_t_star()

- method:

  Method of integration, "trapz" or "integrate"

## Value

Data frame with calculate DVRs for all ROIs

## References

Logan, J., Fowler, J. S., Volkow, N. D., Wang, G.-J., Ding, Y.-S., &
Alexoff, D. L. (1996). Distribution Volume Ratios without Blood Sampling
from Graphical Analysis of PET Data. Journal of Cerebral Blood Flow &
Metabolism, 16(5), 834-840.
https://doi.org/10.1097/00004647-199609000-00008

## See also

Other Logan plot functions:
[`DVR_all_ref_Logan`](https://docs.ropensci.org/tacmagic/reference/DVR_all_ref_Logan.md),
[`dvr`](https://docs.ropensci.org/tacmagic/reference/dvr.md),
[`plot.ref_Logan`](https://docs.ropensci.org/tacmagic/reference/plot.ref_Logan.md)

## Examples

``` r
f <- system.file("extdata", "AD06.tac", package="tacmagic")
fv <- system.file("extdata", "AD06_TAC.voistat", package="tacmagic")
AD06_tac <- load_tac(f, format="PMOD")
AD06_volume <- load_vol(fv, format="voistat")
AD06 <- tac_roi(tac=AD06_tac, volumes=AD06_volume, ROI_def=roi_ham_pib(),  
                merge=FALSE, PVC=FALSE)                             
               
AD06_DVR_fr <- DVR_ref_Logan(AD06, target="frontal", ref="cerebellum",
                             k2prime=0.2, t_star=0) 
#> t* is 23
                            
```
