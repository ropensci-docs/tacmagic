# Creates a tac object from a data.frame

tac objects can be created from data.frame objects with \`as.tac()\`.
The time and activity units must be specified as arguments if not
already set as attributes in the data.frame. The columns of the data
frame are the regional time activity curves, with the column names the
names of the ROIs.

## Usage

``` r
as.tac(x, time_unit = NULL, activity_unit = NULL)
```

## Arguments

- x:

  data.frame with start, end time and tac data

- time_unit:

  NULL if in data.frame or set to "seconds" or "minutes"

- activity_unit:

  NULL if in data.frame or set to "kBq/cc", "Bq/cc", "nCi/cc"

## Value

tac object

## Details

If the time_unit and activity_unit attributes are already in the
data.frame, they do not need to be set again, but otherwise they will
need to be specified in the input parameters.

## See also

Other Loading functions:
[`load_tac`](https://docs.ropensci.org/tacmagic/reference/load_tac.md),
[`load_voistat`](https://docs.ropensci.org/tacmagic/reference/load_voistat.md),
[`load_vol`](https://docs.ropensci.org/tacmagic/reference/load_vol.md)

## Examples

``` r
manual <- data.frame(start=c(0:4), end=c(2:6), 
                     ROI1=c(10.1:14.2), ROI2=c(11:15))
manual_tac <- as.tac(manual, time_unit="minutes", activity_unit="kBq/cc")
```
