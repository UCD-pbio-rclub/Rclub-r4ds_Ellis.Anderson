# Chapter5

# Chapter 5 Assignment, Part 1


```r
# Setup
library(tidyverse)
```

```
## Warning: package 'tidyverse' was built under R version 3.2.5
```

```
## Loading tidyverse: ggplot2
## Loading tidyverse: tibble
## Loading tidyverse: tidyr
## Loading tidyverse: readr
## Loading tidyverse: purrr
## Loading tidyverse: dplyr
```

```
## Warning: package 'ggplot2' was built under R version 3.2.5
```

```
## Warning: package 'tibble' was built under R version 3.2.5
```

```
## Warning: package 'tidyr' was built under R version 3.2.5
```

```
## Warning: package 'purrr' was built under R version 3.2.5
```

```
## Warning: package 'dplyr' was built under R version 3.2.5
```

```
## Conflicts with tidy packages ----------------------------------------------
```

```
## filter(): dplyr, stats
## lag():    dplyr, stats
```

```r
library(nycflights13)
```

## Exercise 5.2.4

```r
View(flights)
# Ex 1.1
filter(flights, arr_delay >= 120)
```

```
## # A tibble: 10,200 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      811       101     1047       137      MQ  N531MQ
## 2   2013     1     1      848       853     1001       851      MQ  N942MQ
## 3   2013     1     1      957       144     1056       123      UA  N534UA
## 4   2013     1     1     1114       134     1447       145      UA  N76502
## 5   2013     1     1     1505       115     1638       127      EV  N17984
## 6   2013     1     1     1525       105     1831       125      B6  N231JB
## 7   2013     1     1     1549        64     1912       136      EV  N21197
## 8   2013     1     1     1558       119     1718       123      EV  N826AS
## 9   2013     1     1     1732        62     2028       123      EV  N16911
## 10  2013     1     1     1803       103     2008       138      MQ  N504MQ
## # ... with 10,190 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 1.2
filter(flights, dest %in% c('IAH', 'HOU'))
```

```
## # A tibble: 9,313 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      517         2      830        11      UA  N14228
## 2   2013     1     1      533         4      850        20      UA  N24211
## 3   2013     1     1      623        -4      933         1      UA  N459UA
## 4   2013     1     1      728        -4     1041         3      UA  N488UA
## 5   2013     1     1      739         0     1104        26      UA  N37408
## 6   2013     1     1      908         0     1228         9      UA  N12216
## 7   2013     1     1     1028         2     1350        11      UA  N76508
## 8   2013     1     1     1044        -1     1352         1      UA  N667UA
## 9   2013     1     1     1114       134     1447       145      UA  N76502
## 10  2013     1     1     1205         5     1503        -2      UA  N39418
## # ... with 9,303 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 1.3
filter(flights, carrier %in% c('UA', 'AA', 'DL'))
```

```
## # A tibble: 139,504 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      517         2      830        11      UA  N14228
## 2   2013     1     1      533         4      850        20      UA  N24211
## 3   2013     1     1      542         2      923        33      AA  N619AA
## 4   2013     1     1      554        -6      812       -25      DL  N668DN
## 5   2013     1     1      554        -4      740        12      UA  N39463
## 6   2013     1     1      558        -2      753         8      AA  N3ALAA
## 7   2013     1     1      558        -2      924         7      UA  N29129
## 8   2013     1     1      558        -2      923       -14      UA  N53441
## 9   2013     1     1      559        -1      941        31      AA  N3DUAA
## 10  2013     1     1      559        -1      854        -8      UA  N76515
## # ... with 139,494 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 1.4
filter(flights, month %in% c(7,8,9))
```

```
## # A tibble: 86,326 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     7     1        1       212      236       157      B6  N653JB
## 2   2013     7     1        2         3      344         0      B6  N805JB
## 3   2013     7     1       29       104      151       110      B6  N348JB
## 4   2013     7     1       43       193      322       188      B6  N794JB
## 5   2013     7     1       44       174      300       120      AA  N324AA
## 6   2013     7     1       46       235      304       186      B6  N640JB
## 7   2013     7     1       48       287      308       243      VX  N627VA
## 8   2013     7     1       58       183      335       172      B6  N535JB
## 9   2013     7     1      100       194      327       177      B6  N531JB
## 10  2013     7     1      100       135      337       122      B6  N663JB
## # ... with 86,316 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 1.5
filter(flights, dep_delay <= 0 & arr_delay >= 120)
```

```
## # A tibble: 29 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1    27     1419        -1     1754       124      MQ  N1EAMQ
## 2   2013    10     7     1350         0     1736       130      EV  N611QX
## 3   2013    10     7     1357        -2     1858       124      AA  N3CMAA
## 4   2013    10    16      657        -3     1258       122      B6  N703JB
## 5   2013    11     1      658        -2     1329       194      VX  N629VA
## 6   2013     3    18     1844        -3       39       140      UA  N560UA
## 7   2013     4    17     1635        -5     2049       124      MQ  N721MQ
## 8   2013     4    18      558        -2     1149       179      AA  N3EXAA
## 9   2013     4    18      655        -5     1213       143      AA  N565AA
## 10  2013     5    22     1827        -3     2217       127      MQ  N518MQ
## # ... with 19 more rows, and 7 more variables: flight <int>, origin <chr>,
## #   dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>, minute <dbl>
```

```r
# Ex 1.6
filter(flights, dep_delay >= 60 & (dep_delay-arr_delay) >= 30)
```

```
## # A tibble: 2,074 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1     1716        91     2140        61      B6  N651JB
## 2   2013     1     1     2205       285       46       246      AA  N5DNAA
## 3   2013     1     1     2326       116      131        73      B6  N594JB
## 4   2013     1     3     1503       162     1803       128      UA  N835UA
## 5   2013     1     3     1821       171     2131       141      AA  N357AA
## 6   2013     1     3     1839        99     2056        66      AA  N631AA
## 7   2013     1     3     1850        65     2148        28      AA  N332AA
## 8   2013     1     3     1923        68     2036        38      9E  N8836A
## 9   2013     1     3     1941       102     2246        67      UA  N402UA
## 10  2013     1     3     1950        65     2228         1      B6  N636JB
## # ... with 2,064 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 1.7
filter(flights, dep_time == 2400 | dep_time <= 600)
```

```
## # A tibble: 9,373 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      517         2      830        11      UA  N14228
## 2   2013     1     1      533         4      850        20      UA  N24211
## 3   2013     1     1      542         2      923        33      AA  N619AA
## 4   2013     1     1      544        -1     1004       -18      B6  N804JB
## 5   2013     1     1      554        -6      812       -25      DL  N668DN
## 6   2013     1     1      554        -4      740        12      UA  N39463
## 7   2013     1     1      555        -5      913        19      B6  N516JB
## 8   2013     1     1      557        -3      709       -14      EV  N829AS
## 9   2013     1     1      557        -3      838        -8      B6  N593JB
## 10  2013     1     1      558        -2      753         8      AA  N3ALAA
## # ... with 9,363 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 2
filter(flights, between(month, 7, 9))
```

```
## # A tibble: 86,326 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     7     1        1       212      236       157      B6  N653JB
## 2   2013     7     1        2         3      344         0      B6  N805JB
## 3   2013     7     1       29       104      151       110      B6  N348JB
## 4   2013     7     1       43       193      322       188      B6  N794JB
## 5   2013     7     1       44       174      300       120      AA  N324AA
## 6   2013     7     1       46       235      304       186      B6  N640JB
## 7   2013     7     1       48       287      308       243      VX  N627VA
## 8   2013     7     1       58       183      335       172      B6  N535JB
## 9   2013     7     1      100       194      327       177      B6  N531JB
## 10  2013     7     1      100       135      337       122      B6  N663JB
## # ... with 86,316 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 3
miss_dep <- filter(flights, is.na(dep_time))
# these flights are also missing delays and arrival times and are likely cancelled flights

# Ex 4
# I'm not entirely sure what this question is asking but anything ^ 0 is still 1, anything | True is True and anything & False is still False. 
```

## Exercise 5.3.1

```r
# Ex 1
arrange(flights, desc(is.na(dep_time)))
```

```
## # A tibble: 336,776 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1       NA        NA       NA        NA      EV  N18120
## 2   2013     1     1       NA        NA       NA        NA      AA  N3EHAA
## 3   2013     1     1       NA        NA       NA        NA      AA  N3EVAA
## 4   2013     1     1       NA        NA       NA        NA      B6  N618JB
## 5   2013     1     2       NA        NA       NA        NA      EV  N10575
## 6   2013     1     2       NA        NA       NA        NA      EV  N13949
## 7   2013     1     2       NA        NA       NA        NA      EV  N10575
## 8   2013     1     2       NA        NA       NA        NA      EV  N759EV
## 9   2013     1     2       NA        NA       NA        NA      EV  N13550
## 10  2013     1     2       NA        NA       NA        NA      AA        
## # ... with 336,766 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 2
arrange(flights, desc(dep_delay))
```

```
## # A tibble: 336,776 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     9      641      1301     1242      1272      HA  N384HA
## 2   2013     6    15     1432      1137     1607      1127      MQ  N504MQ
## 3   2013     1    10     1121      1126     1239      1109      MQ  N517MQ
## 4   2013     9    20     1139      1014     1457      1007      AA  N338AA
## 5   2013     7    22      845      1005     1044       989      MQ  N665MQ
## 6   2013     4    10     1100       960     1342       931      DL  N959DL
## 7   2013     3    17     2321       911      135       915      DL  N927DA
## 8   2013     6    27      959       899     1236       850      DL  N3762Y
## 9   2013     7    22     2257       898      121       895      DL  N6716C
## 10  2013    12     5      756       896     1058       878      AA  N5DMAA
## # ... with 336,766 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
arrange(flights, dep_delay)
```

```
## # A tibble: 336,776 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013    12     7     2040       -43       40        48      B6  N592JB
## 2   2013     2     3     2022       -33     2240       -58      DL  N612DL
## 3   2013    11    10     1408       -32     1549       -10      EV  N825AS
## 4   2013     1    11     1900       -30     2233       -10      DL  N934DL
## 5   2013     1    29     1703       -27     1947       -10      F9  N208FR
## 6   2013     8     9      729       -26     1002         7      MQ  N711MQ
## 7   2013    10    23     1907       -25     2143         0      EV  N13994
## 8   2013     3    30     2030       -25     2213       -37      MQ  N725MQ
## 9   2013     3     2     1431       -24     1601       -30      9E  N929XJ
## 10  2013     5     5      934       -24     1225       -44      B6  N531JB
## # ... with 336,766 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 3
arrange(flights, air_time)
```

```
## # A tibble: 336,776 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1    16     1355        40     1442        31      EV  N16911
## 2   2013     4    13      537        10      622        -6      EV  N12167
## 3   2013    12     6      922        31     1021        27      EV  N27200
## 4   2013     2     3     2153        24     2247        23      EV  N13913
## 5   2013     2     5     1303       -12     1342       -29      EV  N13955
## 6   2013     2    12     2123        -7     2211       -14      EV  N12921
## 7   2013     3     2     1450       -10     1547       -21      US  N947UW
## 8   2013     3     8     2026        51     2131        35      9E  N8501F
## 9   2013     3    18     1456        87     1533        67      EV  N12160
## 10  2013     3    19     2226        41     2305        19      EV  N16987
## # ... with 336,766 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
# Ex 4
arrange(flights, distance)
```

```
## # A tibble: 336,776 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     7    27       NA        NA       NA        NA      US        
## 2   2013     1     3     2127        -2     2222        -2      EV  N13989
## 3   2013     1     4     1240        40     1333        27      EV  N14972
## 4   2013     1     4     1829       134     1937       136      EV  N15983
## 5   2013     1     4     2128        -1     2218        -6      EV  N27962
## 6   2013     1     5     1155        -5     1241       -25      EV  N14902
## 7   2013     1     6     2125        -4     2224         0      EV  N22909
## 8   2013     1     7     2124        -5     2212       -12      EV  N33182
## 9   2013     1     8     2127        -3     2304        39      EV  N11194
## 10  2013     1     9     2126        -3     2217        -7      EV  N17560
## # ... with 336,766 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

```r
arrange(flights, desc(distance))
```

```
## # A tibble: 336,776 × 16
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      857        -3     1516       -14      HA  N380HA
## 2   2013     1     2      909         9     1525        -5      HA  N380HA
## 3   2013     1     3      914        14     1504       -26      HA  N380HA
## 4   2013     1     4      900         0     1516       -14      HA  N384HA
## 5   2013     1     5      858        -2     1519       -11      HA  N381HA
## 6   2013     1     6     1019        79     1558        28      HA  N385HA
## 7   2013     1     7     1042       102     1620        50      HA  N385HA
## 8   2013     1     8      901         1     1504       -26      HA  N389HA
## 9   2013     1     9      641      1301     1242      1272      HA  N384HA
## 10  2013     1    10      859        -1     1449       -41      HA  N388HA
## # ... with 336,766 more rows, and 7 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>
```

## Exercise 5.4.1

```r
# Ex 1
select(flights, starts_with("dep"), starts_with("arr"))
```

```
## # A tibble: 336,776 × 4
##    dep_time dep_delay arr_time arr_delay
##       <int>     <dbl>    <int>     <dbl>
## 1       517         2      830        11
## 2       533         4      850        20
## 3       542         2      923        33
## 4       544        -1     1004       -18
## 5       554        -6      812       -25
## 6       554        -4      740        12
## 7       555        -5      913        19
## 8       557        -3      709       -14
## 9       557        -3      838        -8
## 10      558        -2      753         8
## # ... with 336,766 more rows
```

```r
select(flights, dep_time, arr_time, dep_delay, arr_delay)
```

```
## # A tibble: 336,776 × 4
##    dep_time arr_time dep_delay arr_delay
##       <int>    <int>     <dbl>     <dbl>
## 1       517      830         2        11
## 2       533      850         4        20
## 3       542      923         2        33
## 4       544     1004        -1       -18
## 5       554      812        -6       -25
## 6       554      740        -4        12
## 7       555      913        -5        19
## 8       557      709        -3       -14
## 9       557      838        -3        -8
## 10      558      753        -2         8
## # ... with 336,766 more rows
```

```r
select(flights, ends_with('_time'), ends_with('_delay'))
```

```
## # A tibble: 336,776 × 5
##    dep_time arr_time air_time dep_delay arr_delay
##       <int>    <int>    <dbl>     <dbl>     <dbl>
## 1       517      830      227         2        11
## 2       533      850      227         4        20
## 3       542      923      160         2        33
## 4       544     1004      183        -1       -18
## 5       554      812      116        -6       -25
## 6       554      740      150        -4        12
## 7       555      913      158        -5        19
## 8       557      709       53        -3       -14
## 9       557      838      140        -3        -8
## 10      558      753      138        -2         8
## # ... with 336,766 more rows
```

```r
select(flights, dep_time:arr_delay)
```

```
## # A tibble: 336,776 × 4
##    dep_time dep_delay arr_time arr_delay
##       <int>     <dbl>    <int>     <dbl>
## 1       517         2      830        11
## 2       533         4      850        20
## 3       542         2      923        33
## 4       544        -1     1004       -18
## 5       554        -6      812       -25
## 6       554        -4      740        12
## 7       555        -5      913        19
## 8       557        -3      709       -14
## 9       557        -3      838        -8
## 10      558        -2      753         8
## # ... with 336,766 more rows
```

```r
select(flights, matches("^(dep|arr)_(time|delay)$"))
```

```
## # A tibble: 336,776 × 4
##    dep_time dep_delay arr_time arr_delay
##       <int>     <dbl>    <int>     <dbl>
## 1       517         2      830        11
## 2       533         4      850        20
## 3       542         2      923        33
## 4       544        -1     1004       -18
## 5       554        -6      812       -25
## 6       554        -4      740        12
## 7       555        -5      913        19
## 8       557        -3      709       -14
## 9       557        -3      838        -8
## 10      558        -2      753         8
## # ... with 336,766 more rows
```

```r
# Ex 2
select(flights, dep_time, dep_time)
```

```
## # A tibble: 336,776 × 1
##    dep_time
##       <int>
## 1       517
## 2       533
## 3       542
## 4       544
## 5       554
## 6       554
## 7       555
## 8       557
## 9       557
## 10      558
## # ... with 336,766 more rows
```

```r
# Nothing really, the code works as if it was only added once

# Ex 3
?one_of
# This allows you to supply a list of terms in the form of a variable
vars <- c("year", "month", "day", "dep_delay", "arr_delay")
select(flights, one_of(vars))
```

```
## # A tibble: 336,776 × 5
##     year month   day dep_delay arr_delay
##    <int> <int> <int>     <dbl>     <dbl>
## 1   2013     1     1         2        11
## 2   2013     1     1         4        20
## 3   2013     1     1         2        33
## 4   2013     1     1        -1       -18
## 5   2013     1     1        -6       -25
## 6   2013     1     1        -4        12
## 7   2013     1     1        -5        19
## 8   2013     1     1        -3       -14
## 9   2013     1     1        -3        -8
## 10  2013     1     1        -2         8
## # ... with 336,766 more rows
```

```r
# ^this works
# select(flights, vars)
# ^whereas this does not

# Ex 4
select(flights, contains("TIME"))
```

```
## # A tibble: 336,776 × 3
##    dep_time arr_time air_time
##       <int>    <int>    <dbl>
## 1       517      830      227
## 2       533      850      227
## 3       542      923      160
## 4       544     1004      183
## 5       554      812      116
## 6       554      740      150
## 7       555      913      158
## 8       557      709       53
## 9       557      838      140
## 10      558      753      138
## # ... with 336,766 more rows
```

```r
# not really, but I also just read the documentation. 
# Just set ignore.case = FALSE if you don't want case-insensitive matching.
```

## Exercise 5.5.1
I'm interested in more information on lead() and lag() functions.
I'm also interested in cumulative and rolling aggregates.

```r
# Ex 1
mutate(flights, 
       dep_time_min = dep_time %/% 100 * 60 + dep_time %% 100)
```

```
## # A tibble: 336,776 × 17
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      517         2      830        11      UA  N14228
## 2   2013     1     1      533         4      850        20      UA  N24211
## 3   2013     1     1      542         2      923        33      AA  N619AA
## 4   2013     1     1      544        -1     1004       -18      B6  N804JB
## 5   2013     1     1      554        -6      812       -25      DL  N668DN
## 6   2013     1     1      554        -4      740        12      UA  N39463
## 7   2013     1     1      555        -5      913        19      B6  N516JB
## 8   2013     1     1      557        -3      709       -14      EV  N829AS
## 9   2013     1     1      557        -3      838        -8      B6  N593JB
## 10  2013     1     1      558        -2      753         8      AA  N3ALAA
## # ... with 336,766 more rows, and 8 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>, dep_time_min <dbl>
```

```r
# Ex 2
mutate(flights,
       airtime = arr_time - dep_time)
```

```
## # A tibble: 336,776 × 17
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      517         2      830        11      UA  N14228
## 2   2013     1     1      533         4      850        20      UA  N24211
## 3   2013     1     1      542         2      923        33      AA  N619AA
## 4   2013     1     1      544        -1     1004       -18      B6  N804JB
## 5   2013     1     1      554        -6      812       -25      DL  N668DN
## 6   2013     1     1      554        -4      740        12      UA  N39463
## 7   2013     1     1      555        -5      913        19      B6  N516JB
## 8   2013     1     1      557        -3      709       -14      EV  N829AS
## 9   2013     1     1      557        -3      838        -8      B6  N593JB
## 10  2013     1     1      558        -2      753         8      AA  N3ALAA
## # ... with 336,766 more rows, and 8 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>, airtime <int>
```

```r
# The computed airtime and logged airtime are not the same. 
# They do not account for time zones and therefore can be skewed.
# That being said a lot of the flights are off by intervals of hours and some minutes so I'm not entirely sure how to account for this. 
# This could be in relation to taxi time, etc.

# Ex 3
# The dataset I loaded doesn't include sched_dep_time but I'd imagine dep_delay = dep_time - sched_dep_time

# departures <- mutate(flights,
#       dep_diff = dep_time - sched_dep_time)
# select(flights, dep_delay, dep_diff, dep_time, sched_dep_time)

# Ex 4
(delay <- mutate(flights,
        rank = min_rank(desc(dep_delay))))
```

```
## # A tibble: 336,776 × 17
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     1      517         2      830        11      UA  N14228
## 2   2013     1     1      533         4      850        20      UA  N24211
## 3   2013     1     1      542         2      923        33      AA  N619AA
## 4   2013     1     1      544        -1     1004       -18      B6  N804JB
## 5   2013     1     1      554        -6      812       -25      DL  N668DN
## 6   2013     1     1      554        -4      740        12      UA  N39463
## 7   2013     1     1      555        -5      913        19      B6  N516JB
## 8   2013     1     1      557        -3      709       -14      EV  N829AS
## 9   2013     1     1      557        -3      838        -8      B6  N593JB
## 10  2013     1     1      558        -2      753         8      AA  N3ALAA
## # ... with 336,766 more rows, and 8 more variables: flight <int>,
## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
## #   minute <dbl>, rank <int>
```

```r
rank_delay <- filter(delay, rank <= 10)
arrange(rank_delay, rank)
```

```
## # A tibble: 10 × 17
##     year month   day dep_time dep_delay arr_time arr_delay carrier tailnum
##    <int> <int> <int>    <int>     <dbl>    <int>     <dbl>   <chr>   <chr>
## 1   2013     1     9      641      1301     1242      1272      HA  N384HA
## 2   2013     6    15     1432      1137     1607      1127      MQ  N504MQ
## 3   2013     1    10     1121      1126     1239      1109      MQ  N517MQ
## 4   2013     9    20     1139      1014     1457      1007      AA  N338AA
## 5   2013     7    22      845      1005     1044       989      MQ  N665MQ
## 6   2013     4    10     1100       960     1342       931      DL  N959DL
## 7   2013     3    17     2321       911      135       915      DL  N927DA
## 8   2013     6    27      959       899     1236       850      DL  N3762Y
## 9   2013     7    22     2257       898      121       895      DL  N6716C
## 10  2013    12     5      756       896     1058       878      AA  N5DMAA
## # ... with 8 more variables: flight <int>, origin <chr>, dest <chr>,
## #   air_time <dbl>, distance <dbl>, hour <dbl>, minute <dbl>, rank <int>
```

```r
# Ex 5
1:3 + 1:10
```

```
## Warning in 1:3 + 1:10: longer object length is not a multiple of shorter
## object length
```

```
##  [1]  2  4  6  5  7  9  8 10 12 11
```

```r
# R uses recycling if two vectors are different lengths.
# The above function returns 1 + 1, 2 + 2, 3 + 3, 1 + 4, 2 + 5, etc.
# This is because the first vector is shorter than the second,
# so R starts over from the beginning whenever it runs out of numbers
# from the first vector to add to the second.
# We also get a warning because the first vector doesn't evenly split 
# into the second

# Ex 6
# cos(), sin(), tan(), acos(), asin(), acos(), atan(), atan2(),
# cospi(), sinpi() and tanpi()
```
