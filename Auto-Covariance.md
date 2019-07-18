The Autocorrelation Function
================

## Creating a purely random time series with a normal distribution

  - with the use of the rnorm()
routine

<!-- end list -->

``` r
purely_random_process=ts(rnorm(100)) # 100 data points from std normal distribution that is a ts objecct
(acf(purely_random_process, type='covariance'))
```

![](Auto-Covariance_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

    ## 
    ## Autocovariances of series 'purely_random_process', by lag
    ## 
    ##        0        1        2        3        4        5        6        7 
    ##  0.98692  0.03322 -0.05615 -0.09353 -0.05729 -0.00305  0.07398 -0.01353 
    ##        8        9       10       11       12       13       14       15 
    ## -0.00674  0.02048  0.10801  0.06150 -0.12378 -0.17878  0.06097  0.07885 
    ##       16       17       18       19       20 
    ##  0.14879  0.00156  0.01401 -0.14123 -0.06745

  - We assume weak stattionarity
      - No systematic change in mean or variation
      - No periodic fluctuations

The acf() routine plots autocorrelation cofficients at differnt lags:
correlogram since it starts at 1 r0 = c0/c0 = 1

The resulting plot is the autocorrelation cofficients at different
lags.

``` r
( acf(purely_random_process, main='Correlogram of a Purely Random Porcess') )
```

![](Auto-Covariance_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

    ## 
    ## Autocorrelations of series 'purely_random_process', by lag
    ## 
    ##      0      1      2      3      4      5      6      7      8      9 
    ##  1.000  0.034 -0.057 -0.095 -0.058 -0.003  0.075 -0.014 -0.007  0.021 
    ##     10     11     12     13     14     15     16     17     18     19 
    ##  0.109  0.062 -0.125 -0.181  0.062  0.080  0.151  0.002  0.014 -0.143 
    ##     20 
    ## -0.068

R0 always starts at 1 and then we see that, then we see there isnt much
correlation between the other lags, and based on our selection of a
normal distribution and therefore we dont expect any correlation between
the lags.

The dashed lines show the significance leves and none of the lag spikes
crossing the dashed lines indiciate that there isnt any correlation
between our lags.
