432 Lab 04 for Spring 2022
================

Version: 2022-02-01 09:27:42

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://thomaselove.github.io/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that responds to all questions. that is the result of applying your R
Markdown file to the `oh_counties_2020.csv` data.

Start a separate R Project for Lab 04, as your first step, and place the
data in that project’s directory or (if you want to match what we did)
in a data sub-directory under that project’s directory. We encourage you
to make use of one of the templates we’ve provided for a previous Lab,
or use an approach that works well for you.

# Question 1 (20 points)

We have provided three essay prompts below. Select **one** of the three
available prompts and answer it. Start the essay by clearly identifying
the prompt you are using. We are looking for well-written, clear and
thoughtful responses. Going a little over the suggested length is OK.
Under is not OK.

## Prompt A

In the section on scientific blogging in Jeff Leek’s *How to Be A Modern
Scientist*, he remarks that “Everyone is an internet scientist now.” In
5-10 complete English sentences, we want you to specify, using your own
words, one or two different ways in which you anticipate your work
changing in light of this remark. What might you do differently, if you
thought of yourself as an internet scientist? Do you, already, feel this
way? Does this make being a scientist seem more or less appealing to
you, and why? Please feel encouraged to provide an example from your own
experiences that helps you explain your reactions to this idea.

## Prompt B

In 5-10 complete English sentences, we want you to specify, using your
own words, the **least** helpful piece of advice you took away from
reading Jeff Leek’s *How To Be A Modern Scientist*. Please provide a
reference to the section of the book that provides this problematic
advice. Please avoid selecting something because it does not apply to
your current situation, but instead identify something that might be
relevant to you, but that you are actually unwilling to do, and explain
why. Please feel encouraged to provide an example from your own
experiences that helps you explain why you are unwilling to take this
piece of advice.

## Prompt C

Reread the section of Jeff Leek’s *How To Be A Modern Scientist* on data
sharing, where, among other things, he states that “the reproducibility
debate is over.” In 5-10 complete English sentences, we want you to
specify how the “debate” over reproducibility has affected your field,
and what changes you have made (or intend to make) in light of what
you’ve learned in this course, from Leek’s book, and from your
experiences over the last year to make your work more reproducible. How
important is building reproducible science in your field? In your view,
what does “reproducible science” mean to you, and to the people you will
be working with as you complete your degree program? Please feel
encouraged to provide an example from your own experiences that helps
you explain your reactions to the notion of reproducible science.

# Data Set Description for Questions 2-4 (repeated from Lab 02)

The `oh_counties_2020.csv` data set we have provided describes a series
of variables, pulled from the data for the 88 counties of the the State
of Ohio from the [County Health
Rankings](http://www.countyhealthrankings.org/rankings/data/oh) report
for 2020.

-   We used these data back in Lab 02, also, and we remind you of the
    importance of cleaning the names and some other formatting issues
    that we ran into in that Lab.
-   Several detailed County Health Rankings files augment these 2020
    Ohio Rankings Data. Find [those items
    here](https://www.countyhealthrankings.org/app/ohio/2020/downloads)
    if you’re interested.

The available variables are listed below. Each variable describes data
at the **COUNTY** level.

|        Variable        | Description                                                                                                                        |
|:----------------------:|------------------------------------------------------------------------------------------------------------------------------------|
|         `fips`         | Federal Information Processing Standard code                                                                                       |
|        `county`        | name of County                                                                                                                     |
|   `years_lost_rate`    | age-adjusted years of potential life lost rate (per 100,000 population)                                                            |
|    `sroh_fairpoor`     | % of adults reporting fair or poor health (via BRFSS)                                                                              |
|      `phys_days`       | mean number of reported physically unhealthy days per month                                                                        |
|      `ment_days`       | mean number of reported mentally unhealthy days per mo                                                                             |
|       `lbw_pct`        | % of births with low birth weight (\< 2500 grams)                                                                                  |
|      `smoker_pct`      | % of adults that report currently smoking                                                                                          |
|      `obese_pct`       | % of adults that report body mass index of 30 or higher                                                                            |
|       `food_env`       | indicator of access to healthy foods, in points (0 is worst, 10 is best)                                                           |
|     `inactive_pct`     | % of adults that report no leisure-time physical activity                                                                          |
|     `exer_access`      | % of the population with access to places for physical activity                                                                    |
|      `exc_drink`       | % of adults that report excessive drinking                                                                                         |
|      `alc_drive`       | % of driving deaths with alcohol involvement                                                                                       |
|       `sti_rate`       | Chlamydia cases / Population x 100,000                                                                                             |
|     `teen_births`      | Teen births / females ages 15-19 x 1,000                                                                                           |
|      `uninsured`       | % of people under age 65 without insurance                                                                                         |
|      `pcp_ratio`       | Population to Primary Care Physicians ratio                                                                                        |
|      `prev_hosp`       | Discharges for Ambulatory Care Sensitive Conditions/Medicare Enrollees x 1,000                                                     |
|       `hsgrads`        | High School graduation rate                                                                                                        |
|      `unemployed`      | % of population age 16+ who are unemployed and looking for work                                                                    |
|      `poor_kids`       | % of children (under age 18) living in poverty                                                                                     |
|     `income_ratio`     | Ratio of household income at the 80th percentile to income at the 20th percentile                                                  |
|     `associations`     | # of social associations / population x 10,000                                                                                     |
|        `pm2.5`         | Average daily amount of fine particulate matter in micrograms per cubic meter                                                      |
|       `h2oviol`        | Presence of a water violation: Yes or No                                                                                           |
|     `sev_housing`      | % of households with at least 1 of 4 housing problems: overcrowding, high housing costs, or lack of kitchen or plumbing facilities |
|     `drive_alone`      | % of workers who drive alone to work                                                                                               |
|  `age.adj.mortality`   | premature age-adjusted mortality                                                                                                   |
|       `dm_prev`        | % with a diabetes diagnosis                                                                                                        |
|  `freq_phys_distress`  | % in frequent physical distress                                                                                                    |
| `freq_mental_distress` | % in frequent mental distress                                                                                                      |
|    `food_insecure`     | % who are food insecure                                                                                                            |
|     `insuff_sleep`     | % who get insufficient sleep                                                                                                       |
|    `median_income`     | estimated median income                                                                                                            |
|      `population`      | population size                                                                                                                    |
|      `age65plus`       | % of population who are 65 and over                                                                                                |
|      `african-am`      | % of population who are African-American                                                                                           |
|       `hispanic`       | % of population who are of Hispanic/Latino ethnicity                                                                               |
|        `white`         | % of population who are White                                                                                                      |
|        `female`        | % of population who are Female                                                                                                     |
|        `rural`         | % of people in the county who live in rural areas                                                                                  |

## Loading the Data

Here’s a listing of the resulting tibble.

``` r
library(here)
library(janitor)
library(tidyverse)

oh20 <- read_csv(here("data", "oh_counties_2020.csv")) 

oh20 <- oh20 %>%
    clean_names() %>%
    type.convert(as.is = FALSE) %>%
    mutate(fips = as.character(fips))

oh20
```

    # A tibble: 88 x 43
       fips  state county  years_lost_rate sroh_fairpoor phys_days ment_days lbw_pct
       <chr> <fct> <fct>             <int>         <dbl>     <dbl>     <dbl>   <dbl>
     1 39001 Ohio  Adams             12223          22.3      4.94      4.83    9.05
     2 39003 Ohio  Allen              9037          16.5      4.12      4.4     9.35
     3 39005 Ohio  Ashland            7483          16.8      4.09      4.47    5.96
     4 39007 Ohio  Ashtab~           10013          16.8      4.18      4.57    8.16
     5 39009 Ohio  Athens             7014          20.6      4.66      4.92    8.55
     6 39011 Ohio  Auglai~            6454          14.6      3.73      4.27    7.32
     7 39013 Ohio  Belmont            8289          18.0      3.87      4.46    8.34
     8 39015 Ohio  Brown             10748          17.3      4.19      4.58    7.39
     9 39017 Ohio  Butler             9429          16.5      4         4.14    7.99
    10 39019 Ohio  Carroll            8073          16.2      4.08      4.39    7.61
    # ... with 78 more rows, and 35 more variables: smoker_pct <dbl>,
    #   obese_pct <dbl>, food_env <dbl>, inactive_pct <dbl>, exer_access <dbl>,
    #   exc_drink <dbl>, alc_drive <dbl>, sti_rate <dbl>, teen_births <dbl>,
    #   uninsured <dbl>, pcp_ratio <int>, prev_hosp <dbl>, hsgrads <dbl>,
    #   unemployed <dbl>, poor_kids <dbl>, income_ratio <dbl>, associations <dbl>,
    #   pm2_5 <dbl>, h2oviol <fct>, sev_housing <int>, drive_alone <int>,
    #   age_adj_mortality <dbl>, dm_prev <dbl>, freq_phys_distress <dbl>, ...

## Important Note for Questions 2-4

For Questions 2-4, you’re going to develop a series of models using
**86** of the counties (every county other than Cuyahoga County and
Monroe County). In each case, you will fit and select a model using that
sample of 86 counties, and then be asked to use that model to make
predictions of the outcome of interest for Cuyahoga County and for
Monroe County and to assess the quality of those predictions.

# Question 2 (20 points)

Build a reasonable linear or generalized linear model in your
development sample (86 counties) to predict one of the outcomes in the
`oh_counties_2020.csv` data set that describes a percentage (that must
fall between 0 and 100) effectively using at least three and no more
than 6 other variables from the list above. Demonstrate how well the
model fits as well as the conclusions you draw from the model carefully.
Be sure to discuss model assumptions. Then use the model to predict
Cuyahoga County and Monroe County results, and assess the quality of
those predictions. Note well that the goal here is to fit and evaluate a
single model. There’s no reason to be using an automated variable
selection procedure in this setting.

# Question 3 (30 points)

Divide the 86 counties in your development sample into three groups
(low, middle and high) in a rational way in terms of the
`years_lost_rate` outcome. Make that new grouping your outcome for an
ordinal logistic regression model. Fit a model (using a carefully
selected group of no more than 5 predictor variables) and assess its
performance carefully. Do not include the `age65plus` variable as a
predictor, as the `years_lost_rate` data are age-adjusted already.
Demonstrate how well the model fits as well as the conclusions you draw
from the model carefully. Then use the model to predict Cuyahoga County
and Monroe County results, and assess the quality of those predictions.

## A Hint (for Questions 3 and 4, in particular)

`polr` and several of the other modeling approaches we’ve worked on
recently are finicky, at least in comparison to OLS. Sometimes, you’ll
get to the point where it seems like the model won’t run, or won’t
summarize properly, or you have some extremely large or extremely small
coefficient estimates or standard errors. Should this happen to you, the
first thing we would do is try to identify which of your predictors is
causing this problem, by running the model first with one predictor,
then two, etc. until you figure out which predictors cause problems.
Reasons why you could be having a problem include:

1.  a predictor has values that completely identify the category of your
    outcome variable, perfectly (e.g., one category’s predictor values
    are inevitably lower than all of another category’s predictor
    values, with no overlap)
2.  the scales of the predictors are wildly different, for instance one
    predictor has extremely large or extremely small values, causing the
    estimated standard errors to explode, which should cause you to
    think about reducing the impact of that, perhaps by changing the
    units, say from $s to $1000s or by normalizing the predictors
3.  intense collinearity between two or more of your predictors
4.  coding issues in setting up one or more of the variables.

For example, some people in the past have tried to use `median_income`
in their models along with other variables that have much smaller scales
(ranges). we would try rescaling those predictors with large ranges to
have similar magnitudes to the other predictors, perhaps simply by
expressing the median income in thousands of dollars (by dividing the
raw data by 1000) rather than on its original scale, or perhaps by
normalizing all of the coefficients by subtracting their means and
dividing by their standard deviations.

As another example, some people in the past tried using age-adjusted
mortality to predict years lost rate, but if you divide the years lost
rate into several ordinal categories, it’s not hard to wind up in a
situation where age-adjusted mortality is perfectly separated, so that
if you know the mortality, it automatically specifies the years lost
rate category in these data.

# Question 4 (30 points)

Build a new outcome variable that is a count (possible values = 0-4) of
whether the county meets each of the following standards:

-   the county has a `sroh_fairpoor` value **below** the Ohio-wide mean
    of 17.15
-   the county has an `obese_pct` value **below** the Ohio-wide average
    of 34.32
-   the county has an `exer_access` value **above** the Ohio-wide
    average of 67.76
-   the county has **NOT** had a water violation in the past year (as
    shown by `h2oviol` = No)

Among the 86 counties (excluding Cuyahoga and Monroe) you should find 5
counties which meet 0 of these standards, 16 which meet 1, 31 which meet
2, 19 which meet 3 and 15 which meet all 4.

To illustrate, consider these five counties:

|     County | `sroh_fairpoor` | `obese_pct` | `exer_access` | `h2oviol` | Standards Met |
|-----------:|----------------:|------------:|--------------:|----------:|--------------:|
| *Standard* |        \< 17.15 |    \< 34.32 |      \> 67.76 |        No |             – |
|   Guernsey |           18.66 |        36.4 |          50.7 |       Yes |             0 |
|    Belmont |           18.02 |          35 |          47.4 |    **No** |             1 |
|      Adams |            22.3 |    **32.2** |          41.7 |    **No** |             2 |
|    Ashland |       **16.79** |    **33.3** |            60 |    **No** |             3 |
|      Allen |        **16.5** |      **34** |      **75.8** |    **No** |             4 |

Your job is to fit **two** possible regression models in your
development sample to predict this count, using the same predictors (at
least 3 and no more than 6 of those not used in the calculation of
standards) available in the data set. Demonstrate how well each model
fits the counts by developing a rootogram and other summaries that you
deem useful, then select the model you prefer, specifying your reasons.
Next, use your preferred model to predict Cuyahoga County and Monroe
County results, and assess the quality of those predictions.

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
      janitor_2.1.0       jquerylib_0.1.4     jsonlite_1.7.3     
      knitr_1.37          labeling_0.4.2      lattice_0.20.45    
      lifecycle_1.0.1     lubridate_1.8.0     magrittr_2.0.2     
      MASS_7.3.55         Matrix_1.3.4        methods_4.1.2      
      mgcv_1.8.38         mime_0.12           modelr_0.1.8       
      munsell_0.5.0       nlme_3.1.153        openssl_1.4.6      
      parallel_4.1.2      pillar_1.6.5        pkgconfig_2.0.3    
      prettyunits_1.1.1   processx_3.5.2      progress_1.2.2     
      ps_1.6.0            purrr_0.3.4         R6_2.5.1           
      rappdirs_0.3.3      RColorBrewer_1.1.2  Rcpp_1.0.8         
      readr_2.1.1         readxl_1.3.1        rematch_1.0.1      
      rematch2_2.1.2      reprex_2.0.1        rlang_1.0.0        
      rmarkdown_2.11      rprojroot_2.0.2     rstudioapi_0.13    
      rvest_1.0.2         scales_1.1.1        selectr_0.4.2      
      snakecase_0.11.0    splines_4.1.2       stats_4.1.2        
      stringi_1.7.6       stringr_1.4.0       sys_3.4            
      tibble_3.1.6        tidyr_1.1.4         tidyselect_1.1.1   
      tidyverse_1.3.1     tinytex_0.36        tools_4.1.2        
      tzdb_0.2.0          utf8_1.2.2          utils_4.1.2        
      uuid_1.0.3          vctrs_0.3.8         viridisLite_0.4.0  
      vroom_1.5.7         withr_2.4.3         xfun_0.29          
      xml2_1.3.3          yaml_2.2.2         

### This is the end of Lab 04.
