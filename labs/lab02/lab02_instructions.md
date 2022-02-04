432 Lab 02 for Spring 2022
================

Version: 2022-02-04 10:58:37

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://github.com/THOMASELOVE/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that is the result of applying your R Markdown file to the
`oh_counties_2020.csv` data, available on [our Data and Code
page](https://github.com/THOMASELOVE/432-data), as well as [in the data
subfolder](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab02/data)
for this Lab.

Start a separate R Project for Lab 02, as your first step, and place the
data in that project’s directory or (if you want to match what I did) in
a data sub-directory under that project’s directory.

-   There is an R Markdown **template** for Lab 02, which [you can find
    here](https://github.com/THOMASELOVE/432-2022/blob/main/labs/lab02/lab02_template.Rmd).
    Please feel encouraged to use the template as it is, or modify it to
    produce something that you like better. This template uses the
    `downcute` approach from the `rmdformats` package.
-   If you want to see how this template looks as a knitted HTML file,
    visit the Lab 02 sub-folder in our Shared Drive, download the HTML
    file to your machine, and then view it using your favorite browser.

## The `oh_counties_2020.csv` data

The `oh_counties_2020.csv` data set I have provided describes a series
of variables, pulled from the data for the 88 counties of the the State
of Ohio from the [County Health
Rankings](http://www.countyhealthrankings.org/rankings/data/oh) report
for **2020**.

-   Several detailed County Health Rankings files augment these 2020
    Ohio Rankings Data. Find [those items
    here](https://www.countyhealthrankings.org/app/ohio/2020/downloads)
    if you’re interested. Remember to use the **2020** files.

## A Hint About Ingesting These Data

In the oh20 data set, some of the variables include dashes in their
names rather than what we usually use (underscores.) When you ingest
these variables into R and then try to use them, for example, in
building a model, you will perhaps have some trouble using those
variables. We’re hoping that you will interact with the data, within R,
to resolve this issue.

The `clean_names()` function in the janitor package, for instance, might
be worth thinking about. Applying the clean_names() function as part of
the initial oh20 creation step would be a reasonable strategy here. We
hope you’ll adopt it when ingesting almost any data you ever try to pull
into R.

## The Variables

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

Here’s a listing of the resulting tibble, again, without the use of
`clean_names()` which we think you should be using.

``` r
library(here)
library(tidyverse)

oh20 <- read_csv(here("data", "oh_counties_2020.csv")) 

oh20 <- oh20 %>%
    mutate(fips = as.character(fips))

oh20
```

    # A tibble: 88 x 43
       fips  state county  years_lost_rate sroh_fairpoor phys_days ment_days lbw_pct
       <chr> <chr> <chr>             <dbl>         <dbl>     <dbl>     <dbl>   <dbl>
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
    #   uninsured <dbl>, pcp_ratio <dbl>, prev_hosp <dbl>, hsgrads <dbl>,
    #   unemployed <dbl>, poor_kids <dbl>, income_ratio <dbl>, associations <dbl>,
    #   pm2.5 <dbl>, h2oviol <chr>, sev_housing <dbl>, drive_alone <dbl>,
    #   `age-adj-mortality` <dbl>, dm_prev <dbl>, freq_phys_distress <dbl>, ...

## Question 1 (40 points)

Create a visualization (using R) based on some part of the
`oh_counties_2020.csv` data set, and share it (the visualization and the
R code you used to build it) with us.

The visualization should:

-   be of a professional quality,
-   describe information from at least three different variables listed
    above (you are welcome to transform or re-express the variables if
    that is of interest),
-   include proper labels and a meaningful title,
-   include a *caption* of no more than 75 words that highlights the key
    result. Your caption can be placed within the visualization, or in a
    note below.

In developing your caption, I find it helpful to think about what
question this visualization is meant to answer, and then provide a
caption which makes it clear what the question (and answer) is.

-   You are welcome to find useful tools for visualizing data in R that
    we have seen in either 431 or 432 or elsewhere. Don’t neglect ideas
    you’ve read about (in 431 in Spiegelhalter) or in Leek, for
    instance.
-   Although you may fit a model to help show patterns, your primary
    task is to show **the data** in a meaningful way, rather than to
    simply highlight the results of a model.

We will evaluate Question 1 based on the quality of the visualization,
its title and caption, in terms of being attractive, well-labeled and
useful for representing the County Health Rankings data for Ohio, and
how well it adheres to general principles for good visualizations we’ve
seen in 431 and 432.

## Question 2 (20 points)

Create a linear regression model to predict `obese_pct` as a function of
`food_env` adjusting for `median_income`, and treating all three
variables as quantitative. Specify and then carefully interpret the
estimated coefficient of `food_env` and a 90% uncertainty interval
around that estimate in context using nothing but complete English
sentences. A model using main effects only, entered as linear
predictors, will be sufficient.

## Question 3 (10 points)

Evaluate the quality of the model you fit in Question 2 in terms of
adherence to regression modeling assumptions, through the specification
and written evaluation of residual plots. What might be done to improve
the fit of the model you’ve developed in Question 2? Identify by name
any outlying counties and explain why they are flagged as outliers.

## Question 4 (10 points)

Use the `glance` function in the `broom` package to help you create an
attractive table which compares the model you fit in Question 2 to a
simple linear model which uses only the `food_env` variable as a
predictor. Your comparisons should include assessments of raw and
adjusted R-squared, AIC, BIC and residual standard error within the
complete sample of all 88 Ohio counties. Based on these metrics, which
model looks like it fits the Ohio 2020 data more effectively, and why?

## Question 5 (20 points)

Create a logistic regression model to predict the presence of a water
violation (as contained in `h2oviol`) on the basis of `sev_housing` and
`pm2.5`. Specify and then carefully interpret the estimated odds ratio
associated with the `sev_housing` effect and a 90% uncertainty interval
around that estimate in context using nothing but complete English
sentences. Use a model with main effects only.

## Please add the session information.

Finally, at the end of this lab and all subsequent assignments
(including the projects), please add the session information. My
preferred way for you to do this for 432 is…

``` r
xfun::session_info()
```

### End of Lab 02
