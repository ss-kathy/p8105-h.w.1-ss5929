p8105\_hw1\_ss5929
================
ss5929
9/19/2019

# problem1

## part1

``` r
library(tidyverse)
```

    ## ─ Attaching packages ───────────────────────────────────── tidyverse 1.2.1 ─

    ## ✔ ggplot2 3.2.1     ✔ purrr   0.3.2
    ## ✔ tibble  2.1.3     ✔ dplyr   0.8.3
    ## ✔ tidyr   1.0.0     ✔ stringr 1.4.0
    ## ✔ readr   1.3.1     ✔ forcats 0.4.0

    ## ─ Conflicts ─────────────────────────────────────── tidyverse_conflicts() ─
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(ggplot2)

# create a dataframe
samp        <- rnorm(8)
logical_greater_th_0 <- c(samp>0)
chara_vec   <- c("a","b","c","d","e","f","g","h")
taste_vec   <- factor(c("bad","bad","good","amazing","good","bad","good","amazing"),
                      c("bad","good","amazing"),
                      ordered =  TRUE)
data_f      <- data.frame(samp,logical_greater_th_0,chara_vec,taste_vec)

# take the mean of each variable and the character and logical variable do not work 
mean_samp   <- mean(samp)
mean_logical<- mean(logical_greater_th_0)
mean_chara  <- mean(chara_vec) #the result is NA
```

    ## Warning in mean.default(chara_vec): argument is not numeric or logical:
    ## returning NA

``` r
mean_factor <- mean(taste_vec) #the result is NA
```

    ## Warning in mean.default(taste_vec): argument is not numeric or logical:
    ## returning NA

## part2

``` r
#convert the logical vector to numeric
logical_c_nu     <- as.numeric(logical_greater_th_0)
mutiple_lo_nu_sa <- logical_c_nu*samp

#convert the logical vector to a factor
logical_c_fa     <- as.factor(logical_greater_th_0)
mutiple_lo_fa_sa <- logical_c_fa*samp
```

    ## Warning in Ops.factor(logical_c_fa, samp): '*' not meaningful for factors

``` r
#convert the factor to numeric
logical_c_re     <- as.numeric(logical_c_fa)
mutiple_re       <- logical_c_re*samp
```
