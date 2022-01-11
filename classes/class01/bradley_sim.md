
Creating the `bradley` data set, working from the top part of Table 1 of
Bradley SM et al. (2019) “Incidence, Risk Factors, and Outcomes
Associated With In-Hospital Acute Myocardial Infarction” *JAMA Network
Open* 2(1): e187348. <doi:10.1001/jamanetworkopen.2018.7348>

``` r
library(tidyverse)
```

    -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    v ggplot2 3.3.5     v purrr   0.3.4
    v tibble  3.1.5     v dplyr   1.0.7
    v tidyr   1.1.4     v stringr 1.4.0
    v readr   2.1.0     v forcats 0.5.1

    -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    x dplyr::filter() masks stats::filter()
    x dplyr::lag()    masks stats::lag()

## Simulating Cases

``` r
set.seed(20200114)
status <- rep("Case", 687)
age0 <- round(rnorm(687, mean = 73.3, sd = 10.1))
sex0 <- c(rep("Male", 677), rep("Female", 10))
race_eth0 <- c(rep("white", 546), rep("non-white", 141))
married0 <- c(rep(1, 356), rep(0, 331))
location0 <- c(rep("ICU", 186), rep("Bed", 446), 
               rep("Other", 55))

dat_cases <- tibble(
    status, age = sample(age0), sex = sample(sex0),
    race_eth = sample(race_eth0), married = sample(married0),
    location = sample(location0)
)
```

## Simulating Controls

``` r
status <- rep("Control", 687)
age0 <- round(rnorm(687, mean = 73.4, sd = 10.3))
sex0 <- c(rep("Male", 666), rep("Female", 21))
race_eth0 <- c(rep("white", 527), rep("non-white", 160))
married0 <- c(rep(1, 310), rep(0, 377))
location0 <- c(rep("ICU", 65), rep("Bed", 580), 
               rep("Other", 42))

dat_controls <- tibble(
    status, age = sample(age0), sex = sample(sex0), 
    race_eth = sample(race_eth0), married = sample(married0), 
    location = sample(location0)
)
```

## Combining the Data

``` r
bradley_raw <- bind_rows(dat_cases, dat_controls)
bradley_raw$subject <- sample(1:nrow(bradley_raw))

bradley <- bradley_raw %>%
    select(subject, everything()) %>%
    arrange(subject)

bradley
```

    # A tibble: 1,374 x 7
       subject status    age sex   race_eth married location
         <int> <chr>   <dbl> <chr> <chr>      <dbl> <chr>   
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

``` r
write_csv(bradley, "data/bradley.csv")
```
