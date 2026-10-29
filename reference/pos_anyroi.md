# Dichotomize participants based on ROI cutoff values

Aizenstein et al. (2008) proposed a standardized method of calculating
PIB+ cutoff values to classify participants as PIB+ or PIB-. They used
the DVR from 7 ROIs associated with amyloid deposition. This function
takes the ROI-based cutoff values, e.g. from cutoff_aiz(), and returns a
table specifying which participants are positive, i.e. which have at
least one ROI greater than the cutoff.

## Usage

``` r
pos_anyroi(modelstats, cutoff)
```

## Arguments

- modelstats:

  SUVR or DVR data for group of participants from batch_tm()

- cutoff:

  cutoffs for ROIs as from cutoff_aiz()

## Value

data.frame of participants and positive/negative status

## References

Aizenstein HJ, Nebes RD, Saxton JA, et al. 2008. Frequent amyloid
deposition without significant cognitive impairment among the elderly.
Arch Neurol 65: 1509-1517.

## See also

Other Cutoff functions:
[`cutoff_aiz`](https://docs.ropensci.org/tacmagic/reference/cutoff_aiz.md)
