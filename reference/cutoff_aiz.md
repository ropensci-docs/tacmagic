# Cutoff value calculation using method described in Aizenstein et al. 2008

See the reference below and the tacmagic walkthrough vignette.
Aizenstein et al. (2008) proposed a standardized method of calculating
Pittsburgh Compound B (PIB) cutoff values to classify participants as
PIB+ or PIB-. They used the distribution volume ratio (DVR) from several
ROIs associated with amyloid deposition. The steps are summarized below.
cutoff_aiz() implements 1-3, returning cutoff values for each ROI. It
can be used to dichotomize participants, with pos_anyroi().

## Usage

``` r
cutoff_aiz(modelstats, ROIs)
```

## Arguments

- modelstats:

  SUVR or DVR data for group of participants from batch_tm()

- ROIs:

  list of variables (ROIs) to use for cutoff detection

## Value

Cutoff values for each ROI based on the above method

## Details

1\. Remove outliers from a group of cognitively normal individuals. An
outlier is defined as having any ROI with DVR \> upper inner fence of
that ROI (= 3rd quartile + (1.5 \* IQR). 2. Iterate step 1 as needed
until there are no more outlying participants. 3. From this subset of
the group with outliers removed, the cutoff value for each ROI is set as
the upper inner fence. 4. For all participants, if there is any ROI
above the cutoff for that region, then the participant is deemed to be
PIB+.

## References

Aizenstein HJ, Nebes RD, Saxton JA, et al. 2008. Frequent amyloid
deposition without significant cognitive impairment among the elderly.
Arch Neurol 65: 1509-1517.

## See also

Other Cutoff functions:
[`pos_anyroi`](https://docs.ropensci.org/tacmagic/reference/pos_anyroi.md)

## Examples

``` r
cutoff_aiz(fake_DVR, c("ROI1_DVR", "ROI2_DVR", "ROI3_DVR", "ROI4_DVR"))
#> Iteration: 1 Removed: 10
#> Iteration: 2 Removed: 1
#> Iteration: 3 Removed: 0
#> ROI1_DVR ROI2_DVR ROI3_DVR ROI4_DVR 
#> 1.370899 1.332725 1.330504 1.273470 
```
