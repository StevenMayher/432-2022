432 Lab 05 for Spring 2022
================

Version: 2022-02-01 11:43:27

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://thomaselove.github.io/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that responds to all questions. that is the result of knitting your R
Markdown file. Start a separate R Project for Lab 05, as your first
step, and place the data in that project’s directory or (if you want to
match what we did) in a data sub-directory under that project’s
directory. We encourage you to make use of one of the templates we’ve
provided for a previous Lab, or use an approach that works well for you.

# The Data

You will use the `countyhealthrankings_2017.csv` data set provided on
our [course data
page](https://github.com/THOMASELOVE/432-data/tree/master/data).
Detailed descriptions of the variables in that data set are available in
the 2017 section on [this page at County Health
Rankings](https://www.countyhealthrankings.org/explore-health-rankings/rankings-data-documentation/national-data-documentation-2010-2019).

Note that in this `countyhealthrankings_2017.csv` file, I have created
two multi-categorical variables, as follows:

-   `rural_cat` = Rural if `pct_rural` exceeds 50.00%
-   `rural_cat` = Suburban if `pct_rural` is between 20 and 50%
-   `rural_cat` = Urban if `pct_rural` is below 20.00%

and

-   `race_cat` = Very Low if `pct_nhwhite` exceeds 95.00%
-   `race_cat` = Low if `pct_nhwhite` is between 90 and 95%
-   `race_cat` = Middle if `pct_nhwhite` is between 80 and 90%
-   `race_cat` = High if `pct_nhwhite` is below 80%

Your data set should consist of 3,136 observations on 34 variables, and
the table of the two multi-categorical variables should match that shown
below (note that we have hidden some details of importing and managing
the data.)

``` r
chr17 %>% tabyl(rural_cat, race_cat) %>% 
    adorn_totals(where = c("row", "col")) %>%
    adorn_title(placement = "combined")
```

     rural_cat/race_cat High Middle Low Very Low Total
                  Rural  641    319 519      400  1879
               Suburban  362    259 163       20   804
                  Urban  358     85  10        0   453
                  Total 1361    663 692      420  3136

In questions 1-9, you will use a tidymodels approach to fit and compare
the performance a pair of models for the quantitative outcome `inactive`
contained in the `countyhealthrankings_2017.csv` data set provided in
our [course data
page](https://github.com/THOMASELOVE/432-data/tree/master/data).

In model 1, you will use the following two predictors to predict
`inactive`:

-   `pct_smokers`
-   `rural_cat`

In model 2, you will use the following four predictors to predict
`inactive`:

-   `pct_65plus`
-   `sroh_fairpoor`
-   `some_college`
-   `race_cat`

# Question 1. (10 points)

Import the `countyhealthrankings_2017.csv` data into a tibble called
`chr17` in R, being sure to clean the names and to ensure that all
categorical variables are listed as factors (other than those which
identify the counties, like their name.) Next, demonstrate that the
two-way table of `rural_cat` and `race_cat` shown above matches your
results, including the correct ordering of the categorical variables.
Finally, demonstrate that there are no missing data in the variables you
will include in models 1 or 2. Don’t forget to check the outcome for
missingness, as well as the predictors.

# Question 2. (10 points)

Use `set.seed(2022)` and the `rsample` package to split the data into a
training sample (called `chr_train`) consisting of essentially 70% of
the counties, and a testing sample (called `chr_test`) of the remaining
30% of the counties, while requiring a very similar distribution of
`race_cat` across the training and test samples.

Your resulting `chr_train` and `chr_test` samples should have 2194 and
942 counties, respectively.

# Question 3. (10 points)

Use a Spearman *ρ*<sup>2</sup> plot on your training data set to
identify a predictor in model 2 for which you will consider a non-linear
term.

# Question 4. (10 points)

Build recipes for pre-processing the predictors and establishing the
roles of your variables in your Model 1, and then again in your Model 2.
For each model, be sure that your recipe normalizes all predictors and
uses indicator variables for all factors. Use the training set of data
here.

-   In model 1, use a recipe to generate a simple Box-Cox transformation
    on the `pct_smokers` variable.
-   In your model 2, use an orthogonal quadratic polynomial for the
    predictor you identified in Question 3.

# Question 5. (10 points)

Create a workflow that uses the `lm` modeling engine for model 1 and for
model 2, then fit each model to the training sample, and display tidied
coefficients (with standard errors) for each model in an attractive
table, or pair of tables. Then use `glance` to summarize the in-sample
performance for each model in terms of the number of observations used
in each fit, as well as *R*<sup>2</sup>, AIC and BIC, again making the
result look attractive in your HTML output. Which model looks better by
these standards (model 1 or model 2), and why?

# Question 6. (10 points)

Assess the out-of-sample performance of model 1 and model 2 from
Question 5 in the testing data using three measures of predictive
quality: the correlation-based R-square statistic, the root mean squared
error and the mean absolute error. Produce an attractive display of the
results. Which model performs better on each of these metrics, and why?

# Question 7. (10 points)

Now create a workflow that instead uses a Bayesian approach with `stan`
to fit Model 2, using a seed of `2022` again, as well as a Student t
distribution with 1 degree of freedom for the intercept term, and a
Normal distribution with mean 0 and variance 5 for the predictors.

Produce a tidied and attractive table of the coefficients from this
`stan` fit for Model 2, including the estimate, standard error, and 95%
confidence interval for each coefficient. Then compare the coefficients
you obtain for model 2 from the `stan` fit to the `lm` fit (from
Question 5) for model 2 in a plot of the coefficients, with a 95%
confidence interval for each. What do you see in the plot, and what
conclusions can you draw from it in this case?

# Question 8. (10 points)

Now comparing the `lm` vs. the `stan` fits for Model 2 you built
earlier, use `glance` to summarize the in-sample performance for each
model in terms of the number of observations used in each fit, as well
as *R*<sup>2</sup>, AIC and BIC, in an attractive and clear table or
pair of them. Which model looks better by these standards, and why?

# Question 9. (10 points)

Again comparing the `lm` vs. the `stan` fit for Model 2 that you built
earlier, use the approach taken in Question 6 to assess out-of-sample
performance, in an attractive and clear table or pair of them. What do
you conclude?

# Question 10. (10 points)

Now, refit models 1 and 2 using `lm`, this time without including any
non-linear terms, in a tidy workflow. Summarize the resulting comparison
the two models using attractive and clear tables in terms of:

-   1.  in-sample performance (use `glance` to summarize the in-sample
        performance for each model in terms of the number of
        observations used in each fit, as well as *R*<sup>2</sup>, AIC
        and BIC) and

-   2.  out-of-sample performance (with the correlation-based R-square
        statistic, the root mean squared error and the mean absolute
        error.)

What do you conclude?

### Please add the session information.

Finally, at the end of this Lab and all subsequent assignments
(including the projects), please add the session information, as we have
done below.

``` r
xfun::session_info()
```

    R version 4.1.2 (2021-11-01)
    Platform: x86_64-w64-mingw32/x64 (64-bit)
    Running under: Windows 10 x64 (build 19043)

    Locale:
      LC_COLLATE=English_United States.1252 
      LC_CTYPE=English_United States.1252   
      LC_MONETARY=English_United States.1252
      LC_NUMERIC=C                          
      LC_TIME=English_United States.1252    

    Package version:
      askpass_1.1         assertthat_0.2.1    backports_1.4.1    
      base64enc_0.1-3     bit_4.0.4           bit64_4.0.5        
      blob_1.2.2          broom_0.7.12        cachem_1.0.6       
      callr_3.7.0         cellranger_1.1.0    checkmate_2.0.0    
      class_7.3-19        cli_3.1.1           clipr_0.7.1        
      cluster_2.1.2       codetools_0.2-18    colorspace_2.0-2   
      compiler_4.1.2      conflicted_1.1.0    cpp11_0.4.2        
      crayon_1.4.2        curl_4.3.2          data.table_1.14.2  
      DBI_1.1.2           dbplyr_2.1.1        dials_0.1.0        
      DiceDesign_1.9      digest_0.6.29       dplyr_1.0.7        
      dtplyr_1.2.1        ellipsis_0.3.2      evaluate_0.14      
      fansi_1.0.2         farver_2.1.0        fastmap_1.1.0      
      forcats_0.5.1       foreach_1.5.1       foreign_0.8-82     
      Formula_1.2-4       fs_1.5.2            furrr_0.2.3        
      future_1.23.0       future.apply_1.8.1  gargle_1.2.0       
      generics_0.1.1      ggplot2_3.3.5       globals_0.14.0     
      glue_1.6.1          googledrive_2.0.0   googlesheets4_1.0.0
      gower_0.2.2         GPfit_1.0-8         graphics_4.1.2     
      grDevices_4.1.2     grid_4.1.2          gridExtra_2.3      
      gtable_0.3.0        hardhat_0.2.0       haven_2.4.3        
      here_1.0.1          highr_0.9           Hmisc_4.6-0        
      hms_1.1.1           htmlTable_2.4.0     htmltools_0.5.2    
      htmlwidgets_1.5.4   httr_1.4.2          ids_1.0.1          
      infer_1.0.0         ipred_0.9-12        isoband_0.2.5      
      iterators_1.0.13    janitor_2.1.0       jpeg_0.1-9         
      jquerylib_0.1.4     jsonlite_1.7.3      KernSmooth_2.23.20 
      knitr_1.37          labeling_0.4.2      lattice_0.20-45    
      latticeExtra_0.6-29 lava_1.6.10         lhs_1.1.3          
      lifecycle_1.0.1     listenv_0.8.0       lubridate_1.8.0    
      magrittr_2.0.2      MASS_7.3-55         Matrix_1.3-4       
      MatrixModels_0.5-0  memoise_2.0.1       methods_4.1.2      
      mgcv_1.8.38         mime_0.12           modeldata_0.1.1    
      modelr_0.1.8        multcomp_1.4-18     munsell_0.5.0      
      mvtnorm_1.1-3       nlme_3.1-153        nnet_7.3-17        
      numDeriv_2016.8.1.1 openssl_1.4.6       parallel_4.1.2     
      parallelly_1.30.0   parsnip_0.1.7       patchwork_1.1.1    
      pillar_1.6.5        pkgconfig_2.0.3     plyr_1.8.6         
      png_0.1-7           polspline_1.1.19    prettyunits_1.1.1  
      pROC_1.18.0         processx_3.5.2      prodlim_2019.11.13 
      progress_1.2.2      progressr_0.10.0    ps_1.6.0           
      purrr_0.3.4         quantreg_5.87       R6_2.5.1           
      rappdirs_0.3.3      RColorBrewer_1.1-2  Rcpp_1.0.8         
      readr_2.1.1         readxl_1.3.1        recipes_0.1.17     
      rematch_1.0.1       rematch2_2.1.2      reprex_2.0.1       
      rlang_1.0.0         rmarkdown_2.11      rms_6.2-0          
      rpart_4.1-15        rprojroot_2.0.2     rsample_0.1.1      
      rstudioapi_0.13     rvest_1.0.2         sandwich_3.0-1     
      scales_1.1.1        selectr_0.4.2       slider_0.2.2       
      snakecase_0.11.0    SparseM_1.81        splines_4.1.2      
      SQUAREM_2021.1      stats_4.1.2         stringi_1.7.6      
      stringr_1.4.0       survival_3.2-13     sys_3.4            
      TH.data_1.1-0       tibble_3.1.6        tidymodels_0.1.4   
      tidyr_1.1.4         tidyselect_1.1.1    tidyverse_1.3.1    
      timeDate_3043.102   tinytex_0.36        tools_4.1.2        
      tune_0.1.6          tzdb_0.2.0          utf8_1.2.2         
      utils_4.1.2         uuid_1.0.3          vctrs_0.3.8        
      viridis_0.6.2       viridisLite_0.4.0   vroom_1.5.7        
      warp_0.2.0          withr_2.4.3         workflows_0.2.4    
      workflowsets_0.1.0  xfun_0.29           xml2_1.3.3         
      yaml_2.2.2          yardstick_0.0.9     zoo_1.8-9          

### This is the end of Lab 04.
