Building Table 1 from the `bradley.csv` data
================
Thomas E. Love
2022-01-11

This is a “live code” example that Dr. Love recorded for Class 01 of
432, which happens on 2022-01-11.

## Load Packages

``` r
library(tableone)
library(janitor)
library(tidyverse)
```

## Ingest the `bradley.csv` data

``` r
brad_raw <- read_csv("data/bradley.csv") %>% 
    clean_names()
```

    Rows: 1374 Columns: 7

    -- Column specification --------------------------------------------------------
    Delimiter: ","
    chr (4): status, sex, race_eth, location
    dbl (3): subject, age, married


    i Use `spec()` to retrieve the full column specification for this data.
    i Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
brad_raw
```

    # A tibble: 1,374 x 7
       subject status    age sex   race_eth married location
         <dbl> <chr>   <dbl> <chr> <chr>      <dbl> <chr>   
     1       1 Control    64 Male  white          1 Bed     
     2       2 Case       70 Male  white          1 ICU     
     3       3 Control    68 Male  white          0 Bed     
     4       4 Control    76 Male  white          1 Bed     
     5       5 Control    70 Male  white          1 Bed     
     6       6 Case       89 Male  white          1 Other   
     7       7 Control    75 Male  white          0 Bed     
     8       8 Control    84 Male  white          1 Bed     
     9       9 Control    80 Male  white          1 ICU     
    10      10 Control    89 Male  white          0 Bed     
    # ... with 1,364 more rows

## Attempt 1

``` r
vars <- c("age", "sex", "race_eth", "married", "location")
trt <- c("status")

attempt_1 <- CreateTableOne(data = brad_raw, 
                       vars = vars, 
                       strata = trt)
print(attempt_1)
```

                          Stratified by status
                           Case          Control       p      test
      n                      687           687                    
      age (mean (SD))      73.78 (10.24) 72.60 (10.50)  0.035     
      sex = Male (%)         677 (98.5)    666 (96.9)   0.069     
      race_eth = white (%)   546 (79.5)    527 (76.7)   0.240     
      married (mean (SD))   0.52 (0.50)   0.45 (0.50)   0.013     
      location (%)                                     <0.001     
         Bed                 446 (64.9)    580 (84.4)             
         ICU                 186 (27.1)     65 ( 9.5)             
         Other                55 ( 8.0)     42 ( 6.1)             

## What’s wrong here?

``` r
brad_new <- brad_raw %>%
    mutate(marital = fct_recode(factor(married), 
                                "yes" = "1", 
                                "no"  = "0")) %>%
    mutate(loc = fct_relevel(location, 
                             "ICU", "Bed", "Other"))
```

## Second Attempt

``` r
vars <- c("age", "sex", "race_eth", "marital", "loc")
factorvars <- c("sex", "race_eth", "marital", "loc")
trt <- c("status")

attempt_2 <- CreateTableOne(data = brad_new, 
                       vars = vars, 
                       factorVars = factorvars,
                       strata = trt)
print(attempt_2)
```

                          Stratified by status
                           Case          Control       p      test
      n                      687           687                    
      age (mean (SD))      73.78 (10.24) 72.60 (10.50)  0.035     
      sex = Male (%)         677 (98.5)    666 (96.9)   0.069     
      race_eth = white (%)   546 (79.5)    527 (76.7)   0.240     
      marital = yes (%)      356 (51.8)    310 (45.1)   0.015     
      loc (%)                                          <0.001     
         ICU                 186 (27.1)     65 ( 9.5)             
         Bed                 446 (64.9)    580 (84.4)             
         Other                55 ( 8.0)     42 ( 6.1)             

## Show alternative summaries?

``` r
print(attempt_2, 
      nonnormal = c("age"),
      exact = c("sex", "race_eth", "marital"))
```

                          Stratified by status
                           Case                 Control              p      test   
      n                      687                  687                              
      age (median [IQR])   74.00 [67.00, 81.00] 73.00 [65.00, 80.00]  0.035 nonnorm
      sex = Male (%)         677 (98.5)           666 (96.9)          0.068 exact  
      race_eth = white (%)   546 (79.5)           527 (76.7)          0.240 exact  
      marital = yes (%)      356 (51.8)           310 (45.1)          0.015 exact  
      loc (%)                                                        <0.001        
         ICU                 186 (27.1)            65 ( 9.5)                       
         Bed                 446 (64.9)           580 (84.4)                       
         Other                55 ( 8.0)            42 ( 6.1)                       

## A more detailed summary?

``` r
summary(attempt_2)
```


         ### Summary of continuous variables ###

    status: Case
          n miss p.miss mean sd median p25 p75 min max skew kurt
    age 687    0      0   74 10     74  67  81  38 106 0.02  0.2
    ------------------------------------------------------------ 
    status: Control
          n miss p.miss mean sd median p25 p75 min max skew kurt
    age 687    0      0   73 11     73  65  80  34 103 0.08 -0.1

    p-values
           pNormal pNonNormal
    age 0.03527177 0.03548289

    Standardize mean differences
           1 vs 2
    age 0.1137012

    =======================================================================================

         ### Summary of categorical variables ### 

    status: Case
          var   n miss p.miss     level freq percent cum.percent
          sex 687    0    0.0    Female   10     1.5         1.5
                                   Male  677    98.5       100.0
                                                                
     race_eth 687    0    0.0 non-white  141    20.5        20.5
                                  white  546    79.5       100.0
                                                                
      marital 687    0    0.0        no  331    48.2        48.2
                                    yes  356    51.8       100.0
                                                                
          loc 687    0    0.0       ICU  186    27.1        27.1
                                    Bed  446    64.9        92.0
                                  Other   55     8.0       100.0
                                                                
    ------------------------------------------------------------ 
    status: Control
          var   n miss p.miss     level freq percent cum.percent
          sex 687    0    0.0    Female   21     3.1         3.1
                                   Male  666    96.9       100.0
                                                                
     race_eth 687    0    0.0 non-white  160    23.3        23.3
                                  white  527    76.7       100.0
                                                                
      marital 687    0    0.0        no  377    54.9        54.9
                                    yes  310    45.1       100.0
                                                                
          loc 687    0    0.0       ICU   65     9.5         9.5
                                    Bed  580    84.4        93.9
                                  Other   42     6.1       100.0
                                                                

    p-values
                  pApprox       pExact
    sex      6.926864e-02 6.760400e-02
    race_eth 2.403791e-01 2.403489e-01
    marital  1.513478e-02 1.510454e-02
    loc      1.429017e-17 3.999616e-18

    Standardize mean differences
                 1 vs 2
    sex      0.10797814
    race_eth 0.06690265
    marital  0.13427981
    loc      0.48923102

## Send original attempt 2 to Excel for polish?

One option is to **save the Table 1** to a `.csv` file, which you can
then open directly in Excel. This is the approach I generally use. Note
the addition of some `quote`, `noSpaces` and `printToggle` selections
here.

``` r
brad_t1 <- print(attempt_2, 
      quote = FALSE, noSpaces = TRUE, printToggle = FALSE)

write.csv(brad_t1, file = "bradley_table1_result.csv")
```

You can then open the `bradley_table1_result.csv` file in Excel and edit
further.
