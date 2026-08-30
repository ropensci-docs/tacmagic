# Loads TAC from file for use by other functions (default is PMOD .tac format)

This is the main function for loading an individual participant's TAC
data. The minimal required information within the supplied files is the
start and stop times and a time unit (either seconds or minutes), as
well as the activity values for 1 or more ROIs, and units for activity.
The currently supported formats (with the corresponding format
argument), include:

- "PMOD": PMOD .tac files

- "voistat": PMOD TAC .voistat files used in combination with PMOD
  .acqtimes file for start/stop times.

- "magia": magia pipeline .mat tac file

- "DFT": Turku PET Centre's DFT format

## Usage

``` r
load_tac(filename, format = "PMOD", acqtimes = NULL,
  time_unit = NULL, activity_unit = NULL)
```

## Arguments

- filename:

  (e.g. "participant01.tac")

- format:

  A character string, with options listed above (e.g. "PMOD")

- acqtimes:

  Filename for a .acqtimes file (as in PMOD), required for
  format="voistat"

- time_unit:

  NULL if in file (e.g. PMOD .tac), or set to "seconds" or "minutes" if
  not in file or to override file

- activity_unit:

  NULL if in file (e.g. PMOD .tac), or set to "kBq/cc", "Bq/cc",
  "nCi/cc"

## Value

tac object

## See also

Other Loading functions:
[`as.tac`](https://docs.ropensci.org/tacmagic/reference/as.tac.md),
[`load_voistat`](https://docs.ropensci.org/tacmagic/reference/load_voistat.md),
[`load_vol`](https://docs.ropensci.org/tacmagic/reference/load_vol.md)

## Examples

``` r
f_raw_tac <- system.file("extdata", "AD06.tac", package="tacmagic") 
tac <- load_tac(f_raw_tac)
```
