432 Lab 06 for Spring 2022
================

Version: 2022-02-01 09:59:35

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://thomaselove.github.io/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that responds to all questions.

Start a separate R Project for Lab 06, as your first step, and place the
data in that project’s directory or (if you want to match what we did)
in a data sub-directory under that project’s directory. We encourage you
to make use of one of the templates we’ve provided for a previous Lab,
or use an approach that works well for you.

# Question 1 (20 points)

In *The Signal and The Noise*, Silver writes (in several places prior to
Chapter 12, but especially there) that the goal of any predictive model
is to capture as much signal as possible and as little noise as
possible. What does this mean to you in your scientific and other
endeavours, going forward? Give a specific example.

## Specifications for the essay

In reading your essay, we will look for the following specifications to
be met:

1.  Length is between 200 and 400 words.
2.  English is correctly used throughout, and there are no
    typographical, grammatical or syntax errors.
3.  The example provided clearly addresses the issue discussed above and
    in *The Signal and the Noise*.
4.  Enough details are given about the example so that we can follow why
    this is important to you in your chosen field.
5.  The essay is clearly written, in general.
6.  The essay is interesting to read.

# Setup for Questions 2-4

The `umaru.csv` data file contains information for 575 subjects selected
from the UMARU IMPACT study collaborative project done by the University
of Massachusetts AIDS Research Unit over 5 years (1989-1994). Various
versions of this data set are frequently used in survival analysis
texts. I’ve tweaked your data set enough that you’ll see some different
results. The study included two concurrent randomized trials of
residential treatment for drug abuse. The key question is to compare
treatment programs of different planned durations in terms of their
ability to reduce drug abuse and prevent high-risk HIV behavior. Here’s
a codebook:

|  Variable | Description                                                                                                                                            |
|----------:|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| `subject` | Subject ID #, ranging from 1001 - 1575                                                                                                                 |
|     `age` | age at enrollment, in years                                                                                                                            |
|    `beck` | Beck Depression Score at admission                                                                                                                     |
|  `hercoc` | heroin or cocaine use during the 3 months prior to admission (1 = Heroin & Cocaine, 2 = Heroin only, 3 = Cocaine only, 4 = Neither Heroin nor Cocaine) |
|    `ivhx` | IV drug use history at admission (1 = never, 2 = previous but not recent, 3 = recent)                                                                  |
| `ndrugtx` | # of prior drug treatments                                                                                                                             |
|    `race` | subject’s race (0 = white, 1 = other)                                                                                                                  |
|   `treat` | treatment randomization assignment (Long, or Short)                                                                                                    |
|    `site` | treatment site (A or B)                                                                                                                                |
|     `lot` | Length of Treatment (Exit Date - Admission Date), in days                                                                                              |
|    `time` | Time to Return to Drug Use (measured from Admission Date), in days                                                                                     |
|  `censor` | Returned to Drug Use indicator (1 = returned to drug use, 0 = otherwise)                                                                               |

# Question 2 (20 points)

Build a Cox model, using `treat` as a predictor, and spending degrees of
freedom in any way you like with the rest of the available predictors
(i.e. *everything but* `subject`, `lot`, `time` and `censor`) in the
data set, so long as you do not exceed a total of 12 degrees of freedom,
predicting the time to return to drug use. You’ll probably want to use a
Spearman rho-squared plot to make your selection, in which case you
should stick with the model you develop using that tool, regardless of
its eventual performance. Specify your model carefully, and interpret
the hazard ratio for `treat` implied by your new model.

**Hint** When you build the Spearman rho-squared plot, use `time` but
not the entire survival object as the “outcome.”

# Question 3 (20 points)

Apply a Cox regression model to predict the time to return to drug use
(incorporating censoring appropriately) using the information in
`treat`, plus main effects of `age`, `beck`, `site`, `ivhx` and
`ndrugtx`. Interpret the meaning of the hazard ratio for `treat`, after
adjusting for the other five predictors.

# Question 4 (15 points)

Compare the two models you have fit in Questions 2 and 3, specifying
which one you prefer and why. Be sure to include both a comparison of
the quality of fit from each model (be sure to at least two ways to
assess that quality of fit), and an assessment of adherence to the
assumptions of a proportional hazards model for your final selection.
Validate the summary statistics describing your chosen model, and
explain what those results mean, too.

# Question 5 (25 points)

The `remission.csv` file contains contains initial remission times, in
days, for 44 leukemia patients who were randomly allocated to two
different treatments, labeled A and B. Some patients were right-censored
before their remission times could be fully determined, as indicated by
values of `censored` = 1 in the data set. Note that remission is a good
thing, so long times before remission are bad.

Your task is to plot and compare appropriate estimates of the survival
functions for the two treatments, including at least a Kaplan-Meier
estimate and a log rank test. Compare median and (restricted) mean
survival times appropriately. Write a complete sentence (or several) to
accompany each of your estimates and plots. Do not use a regression
model.

### Please add the session information.

Finally, at the end of this homework and all subsequent assignments
(including the projects), please add the session information. You can
either use the usual `sessioninfo::session_info()` approach, or else
use…

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
      base64enc_0.1.3     bit_4.0.4           bit64_4.0.5        
      blob_1.2.2          broom_0.7.12        callr_3.7.0        
      cellranger_1.1.0    cli_3.1.1           clipr_0.7.1        
      colorspace_2.0-2    compiler_4.1.2      cpp11_0.4.2        
      crayon_1.4.2        curl_4.3.2          data.table_1.14.2  
      DBI_1.1.2           dbplyr_2.1.1        digest_0.6.29      
      dplyr_1.0.7         dtplyr_1.2.1        ellipsis_0.3.2     
      evaluate_0.14       fansi_1.0.2         farver_2.1.0       
      fastmap_1.1.0       forcats_0.5.1       fs_1.5.2           
      gargle_1.2.0        generics_0.1.1      ggplot2_3.3.5      
      glue_1.6.1          googledrive_2.0.0   googlesheets4_1.0.0
      graphics_4.1.2      grDevices_4.1.2     grid_4.1.2         
      gtable_0.3.0        haven_2.4.3         here_1.0.1         
      highr_0.9           hms_1.1.1           htmltools_0.5.2    
      httr_1.4.2          ids_1.0.1           isoband_0.2.5      
      jquerylib_0.1.4     jsonlite_1.7.3      knitr_1.37         
      labeling_0.4.2      lattice_0.20.45     lifecycle_1.0.1    
      lubridate_1.8.0     magrittr_2.0.2      MASS_7.3.55        
      Matrix_1.3.4        methods_4.1.2       mgcv_1.8.38        
      mime_0.12           modelr_0.1.8        munsell_0.5.0      
      nlme_3.1.153        openssl_1.4.6       pillar_1.6.5       
      pkgconfig_2.0.3     prettyunits_1.1.1   processx_3.5.2     
      progress_1.2.2      ps_1.6.0            purrr_0.3.4        
      R6_2.5.1            rappdirs_0.3.3      RColorBrewer_1.1.2 
      Rcpp_1.0.8          readr_2.1.1         readxl_1.3.1       
      rematch_1.0.1       rematch2_2.1.2      reprex_2.0.1       
      rlang_1.0.0         rmarkdown_2.11      rprojroot_2.0.2    
      rstudioapi_0.13     rvest_1.0.2         scales_1.1.1       
      selectr_0.4.2       splines_4.1.2       stats_4.1.2        
      stringi_1.7.6       stringr_1.4.0       sys_3.4            
      tibble_3.1.6        tidyr_1.1.4         tidyselect_1.1.1   
      tidyverse_1.3.1     tinytex_0.36        tools_4.1.2        
      tzdb_0.2.0          utf8_1.2.2          utils_4.1.2        
      uuid_1.0.3          vctrs_0.3.8         viridisLite_0.4.0  
      vroom_1.5.7         withr_2.4.3         xfun_0.29          
      xml2_1.3.3          yaml_2.2.2         

### This is the end of Lab 06.
