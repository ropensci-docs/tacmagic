# Convert radioactivity units

Change the radioactivity units of a tac or numeric object to the
specified desired units (e.g. Bq, kBq, MBq, nCi, uCi, mCi, Ci). For
convenience, if the unit is per volume ("x/cc" or "x/mL"), the "/cc"
part is ignored for the conversion.

## Usage

``` r
change_units(x, to_unit, from_unit)
```

## Arguments

- x:

  time-activity curve or numeric object

- to_unit:

  the desired unit (e.g. "kBq")

- from_unit:

  not used for tac object (it is in the tac object), but for numeric
  objects, must be specified (e.g. "nCi")

## Value

the converted object, same type as x

## Examples

``` r
f <- system.file("extdata", "AD06.tac", package="tacmagic")
AD06_tac <- load_tac(f, format="PMOD")
AD06_tac_nCicc <- change_units(AD06_tac, to_unit = "nCi/cc")

change_units(5, to_unit = "kBq", from_unit = "nCi")
#> [1] 0.185
change_units(0.185, to_unit = "nCi", from_unit = "kBq")
#> [1] 5
```
