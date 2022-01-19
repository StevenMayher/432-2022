432 Lab 01 for Spring 2022
================

Version: 2022-01-19 14:26:38

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://github.com/THOMASELOVE/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that is the result of applying your R Markdown file to the `hbp3456.csv`
data, available on [our Data and Code
page](https://github.com/THOMASELOVE/432-data), as well as [in the data
subfolder](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab01/data)
for this Lab.

Start a separate R Project for Lab 1, as your first step, and place the
data in that project’s directory or (if you want to match what I did) in
a data sub-directory under that project’s directory.

-   There is an R Markdown **template** for Lab 01, which [you can find
    here](https://github.com/THOMASELOVE/432-2022/blob/main/labs/lab01/lab01_template.Rmd),
    or in our Shared Drive in the Lab 01 Materials folder. Please feel
    encouraged to use the template as it is, or modify it to produce
    something that you like better.
-   If you want to see how this template looks as a knitted HTML file,
    you can find the HTML version posted to our Shared Drive in the Lab
    01 Materials folder.

## The `hbp3456` data

The (simulated) data in the `hbp3456` file describe a total of 3456
people living with hypertension (high blood pressure) diagnoses who
receive primary care in one of eight practices.

-   In each of the eight practices, 432 (different) individuals (who
    I’ll call subjects in what follows) were sampled at random from all
    eligible subjects.
-   The data are based on real electronic health record (EHR) data, but
    with some noise added.
    -   The practices are named after streets that appear in *The
        Simpsons*.
    -   There are 62 (fictional) providers identified across the eight
        practices, and each provider cares for subjects within a single
        practice.

### Eligibility Criteria

The data are cross-sectional and describe results from a one-year
reporting window. To be eligible for the study, a subject had to meet
all of the following criteria:

-   have an EHR-documented hypertension diagnosis which applied during
    the one-year reporting window,
-   cared for at one of the eight practices in this study, and by one of
    the 62 participating providers in this study
-   age 25 or older at the start of the one-year reporting period (note
    that all subjects with ages 80 and higher are listed as age 80 in
    the data)
-   between 1 and 12 primary care office visits in the one-year
    reporting period
-   between 2 and 24 primary care office visits combined across the
    reporting period and the previous year
-   fall into one of two biological sex categories (female or male)
-   fall into one of four primary insurance categories, specifically
    Medicare, Commercial, Medicaid or Uninsured.
-   have a most recent systolic BP between 80 and 220 mm Hg and most
    recent diastolic BP between 40 and 140 mm Hg, where the systolic BP
    is at least 15 and no more than 130 mm Hg larger than the diastolic
    BP.

### Codebook

|    Variable | Description                                                                                                                                                                     |
|------------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `record` | unique code for each subject (six digits, first digit is 9, last indicates practice)                                                                                            |
|  `practice` | primary care practice, of which there are eight in the data                                                                                                                     |
|  `provider` | primary care provider (each practice has multiple providers)                                                                                                                    |
|       `age` | subject’s age as of the start of the reporting period                                                                                                                           |
|      `race` | subject’s race (4 levels: Asian, AA_Black, White, Other)                                                                                                                        |
|  `eth_hisp` | is subject of Hispanic/Latino ethnicity? Yes or No                                                                                                                              |
|       `sex` | subject’s sex (F or M)                                                                                                                                                          |
| `insurance` | subject’s primary insurance (Medicare, Commercial, Medicaid, Uninsured)                                                                                                         |
|    `income` | estimated median income of subject’s home neighborhood (via American Community Survey, to nearest $100)                                                                         |
|    `hsgrad` | estimated percentage of adults living in the subject’s home neighborhood who have graduated from high school (via American Community Survey, to the nearest tenth of a percent) |
|   `tobacco` | tobacco use status (Current, Former, or Never)                                                                                                                                  |
| `depr_diag` | does subject have depression diagnosis? Yes or No                                                                                                                               |
|    `height` | subject’s height in meters, rounded to two decimal places                                                                                                                       |
|    `weight` | subject’s weight in kilograms, rounded to one decimal place                                                                                                                     |
|       `ldl` | subject’s LDL cholesterol level, in mg/dl                                                                                                                                       |
|    `statin` | does subject have a current prescription for a statin medication? Yes or No                                                                                                     |
|    `bp_med` | does subject have a current prescription for a blood pressure control medication? Yes or No                                                                                     |
|       `sbp` | subject’s most recently obtained systolic blood pressure, in mm Hg                                                                                                              |
|       `dbp` | subject’s most recently obtained diastolic blood pressure, in mm Hg                                                                                                             |
|  `visits_1` | subject’s number of visits for primary care in reporting period (one year)                                                                                                      |
|  `visits_2` | subject’s visits for primary care in the past two years                                                                                                                         |
|    `acearb` | does subject have a current prescription for an ACE-inhibitor or ARB? Yes or No                                                                                                 |
|     `betab` | does subject have a current prescription for a beta-blocker? Yes or No                                                                                                          |

### Notes on Specific Variables

-   The list of medications included in `bp_med` is: ACE-inhibitor, ARB,
    Diuretic, Calcium-Channel Blocker, Beta-Blocker, Alpha-1 Blocker,
    Centrally acting Alpha-2 Agonist, Vasodilator or other
    antihypertensive agents. A subject with a current prescription for
    any of these will have a Yes in `bp_med`.
-   For the `acearb`, `betab`, `bpmed`, `statin` and `depr_diag`
    variables, a No response includes all subjects where there’s no
    evidence in the EHR of meeting the Yes criterion, so that there are
    no missing values (a missing value is interpreted there as No.)
-   For the `height`, `weight` and `ldl` results, implausible values
    were treated as missing in preparing the data for you.
-   The `race` and `eth_hisp` values are self-reported, and some
    subjects refused to answer one or both of the relevant questions.
-   The `income` and `hsgrad` values are imputed from the subject’s home
    address, usually at the census block level, but occasionally at the
    level of the zip code.
    -   When a subject’s home address could not be geocoded, these
        values are noted as missing.
    -   Geocoded estimates of `income` below 6500 are reported as 6500,
        and estimates above 130000 are reported as 130000.
    -   For `hsgrad`, geocoded estimates below 40 are reported as 40,
        and estimates above 99.9 are reported as 99.9.

## Summarizing the Complete Data

Here’s a summary of the data using the `describe` function in the
`Hmisc` package.

``` r
lab1 <- read_csv(here("data", "hbp3456.csv")) 
         # reads the hbp3456.csv file
         # from the data subfolder

lab1 <- lab1 %>%
    mutate(record = as.character(record))

describe(lab1) # from the Hmisc package
```

    lab1 

     23  Variables      3456  Observations
    --------------------------------------------------------------------------------
    record 
           n  missing distinct 
        3456        0     3456 

    lowest : 900018 900024 900037 900043 900057, highest: 934527 934532 934542 934552 934568
    --------------------------------------------------------------------------------
    practice 
           n  missing distinct 
        3456        0        8 

    lowest : Center   Elm      Highland King     North   
    highest: King     North    Plympton Sycamore Walnut  
                                                                             
    Value        Center      Elm Highland     King    North Plympton Sycamore
    Frequency       432      432      432      432      432      432      432
    Proportion    0.125    0.125    0.125    0.125    0.125    0.125    0.125
                       
    Value        Walnut
    Frequency       432
    Proportion    0.125
    --------------------------------------------------------------------------------
    provider 
           n  missing distinct 
        3456        0       62 

    lowest : C_01 C_02 C_03 C_04 C_05, highest: W_06 W_07 W_08 W_09 W_10
    --------------------------------------------------------------------------------
    age 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3456        0       56    0.999    59.19    14.24       37       43 
         .25      .50      .75      .90      .95 
          51       59       68       77       80 

    lowest : 25 26 27 28 29, highest: 76 77 78 79 80
    --------------------------------------------------------------------------------
    race 
           n  missing distinct 
        3364       92        4 
                                                  
    Value      AA_Black    Asian    Other    White
    Frequency      1460       53      109     1742
    Proportion    0.434    0.016    0.032    0.518
    --------------------------------------------------------------------------------
    eth_hisp 
           n  missing distinct 
        3345      111        2 
                          
    Value         No   Yes
    Frequency   3130   215
    Proportion 0.936 0.064
    --------------------------------------------------------------------------------
    sex 
           n  missing distinct 
        3456        0        2 
                          
    Value          F     M
    Frequency   2064  1392
    Proportion 0.597 0.403
    --------------------------------------------------------------------------------
    insurance 
           n  missing distinct 
        3456        0        4 
                                                          
    Value      Commercial   Medicaid   Medicare  Uninsured
    Frequency        1033        907       1382        134
    Proportion      0.299      0.262      0.400      0.039
    --------------------------------------------------------------------------------
    income 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3431       25      637        1    38627    20548    14700    17400 
         .25      .50      .75      .90      .95 
       23900    35800    52100    64200    67700 

    lowest :   6500   6600   7000   7300   7400, highest: 120400 121100 122100 126000 130000
    --------------------------------------------------------------------------------
    hsgrad 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3431       25      477        1    82.15    11.81    61.60    68.60 
         .25      .50      .75      .90      .95 
       75.35    84.30    90.05    93.90    95.30 

    lowest : 40.0 40.4 41.0 41.3 41.9, highest: 99.4 99.6 99.7 99.8 99.9
    --------------------------------------------------------------------------------
    tobacco 
           n  missing distinct 
        3451        5        3 
                                      
    Value      Current  Former   Never
    Frequency      784    1047    1620
    Proportion   0.227   0.303   0.469
    --------------------------------------------------------------------------------
    depr_diag 
           n  missing distinct 
        3456        0        2 
                          
    Value         No   Yes
    Frequency   2519   937
    Proportion 0.729 0.271
    --------------------------------------------------------------------------------
    height 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3438       18       59    0.997    1.675   0.1169     1.52     1.55 
         .25      .50      .75      .90      .95 
        1.60     1.68     1.75     1.82     1.85 

    lowest : 1.35 1.37 1.40 1.42 1.44, highest: 1.94 1.96 1.98 2.01 2.03
    --------------------------------------------------------------------------------
    weight 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3437       19      907        1    92.29    27.44    57.70    63.56 
         .25      .50      .75      .90      .95 
       74.80    88.90   105.70   125.20   137.32 

    lowest :  40.9  42.6  43.0  43.5  44.0, highest: 209.3 213.5 213.7 213.8 231.3
    --------------------------------------------------------------------------------
    ldl 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3025      431      205        1    111.2    44.29       55       65 
         .25      .50      .75      .90      .95 
          82      106      135      166      186 

    lowest :  30  31  32  33  34, highest: 236 238 240 244 246
    --------------------------------------------------------------------------------
    statin 
           n  missing distinct 
        3456        0        2 
                          
    Value         No   Yes
    Frequency   1689  1767
    Proportion 0.489 0.511
    --------------------------------------------------------------------------------
    bp_med 
           n  missing distinct 
        3456        0        2 
                          
    Value         No   Yes
    Frequency    196  3260
    Proportion 0.057 0.943
    --------------------------------------------------------------------------------
    sbp 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3456        0      106    0.999    132.5    18.29      107      112 
         .25      .50      .75      .90      .95 
         122      132      142      154      160 

    lowest :  84  88  90  91  92, highest: 191 197 198 199 214
    --------------------------------------------------------------------------------
    dbp 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3456        0       82    0.998    76.87    12.39       60       62 
         .25      .50      .75      .90      .95 
          70       78       84       90       96 

    lowest :  42  43  44  45  46, highest: 122 123 124 127 136
    --------------------------------------------------------------------------------
    visits_1 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3456        0       12     0.96    3.056    1.953        1        1 
         .25      .50      .75      .90      .95 
           2        3        4        5        7 

    lowest :  1  2  3  4  5, highest:  8  9 10 11 12
                                                                                
    Value          1     2     3     4     5     6     7     8     9    10    11
    Frequency    687   917   741   478   289   167    75    40    28    21     5
    Proportion 0.199 0.265 0.214 0.138 0.084 0.048 0.022 0.012 0.008 0.006 0.001
                    
    Value         12
    Frequency      8
    Proportion 0.002
    --------------------------------------------------------------------------------
    visits_2 
           n  missing distinct     Info     Mean      Gmd      .05      .10 
        3456        0       23    0.983    5.346    3.233        2        2 
         .25      .50      .75      .90      .95 
           3        5        7        9       11 

    lowest :  2  3  4  5  6, highest: 20 21 22 23 24
    --------------------------------------------------------------------------------
    acearb 
           n  missing distinct 
        3456        0        2 
                          
    Value         No   Yes
    Frequency   1356  2100
    Proportion 0.392 0.608
    --------------------------------------------------------------------------------
    betab 
           n  missing distinct 
        3456        0        2 
                          
    Value         No   Yes
    Frequency   2238  1218
    Proportion 0.648 0.352
    --------------------------------------------------------------------------------

## Question 1. (40 points)

Build a Table 1 to compare the subjects in the **Highland** practice to
the subjects in the **Sycamore** practice on the following nine
variables:

-   age,
-   race,
-   Hispanic ethnicity,
-   sex,
-   primary insurance,
-   body mass index,
-   BMI category,
-   systolic blood pressure, and
-   diastolic blood pressure.

Make the Table as well as you can within R Markdown, and display the
result as part of your HTML file. All code must be visible to us.
**Include a description of the important results from your Table 1 that
does not exceed 100 words, using complete English sentences**.

1.  Be sure that your table specifies the number of subjects in each
    practice. **Note that you’ll have to do something so that your work
    focuses on the comparison of Highland to Sycamore, leaving out (for
    this question only) the other practices.**
2.  You’ll have to deal with some missing values in the data. All
    missing values are indicated in the .csv file with NA. It’s not
    usually appropriate to report results that include imputation in a
    Table 1, so build a note specifying the amount of missing data in a
    footnote to the table. An appropriate approach would be to list
    these notes as a bulleted list in the Markdown file just below your
    Table.
3.  Some variables will present as characters in the data, but you’d
    instead prefer them to appear as **factors**. Be sure to include
    code in your response to make these changes (the `forcats` package
    is your friend here) and then (perhaps using the `fct_relevel`
    function in the `forcats` package) be sure to move the levels of
    those factors into an order that facilitates interpretation.
4.  Be sure, too, to make reasoned choices about whether means and
    standard deviations or instead medians and quartiles are more
    appropriate displays for the quantitative variables. Include your
    reasons in your bulleted list of footnotes at the end of your table.
    Note that the `record` information is just a code (even though it is
    numerical) and should be treated as a character variable in using
    these data, as I did above.
5.  Note that body mass index (BMI) and BMI category are not supplied in
    the data, although you do have height and weight. **So, you’ll have
    to calculate the BMI and add it to the data set.** If you don’t know
    the formula for BMI, you have Google to help you figure it out.
6.  For BMI categories, use the four groups specified in the [How is BMI
    interpreted for Adults section of this
    description](https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html)
    of Adult BMI by the Centers for Disease Control. **Again, you’ll
    need to use your calculated BMI values and then create the
    categories in your data set, and you’ll need to figure out a way to
    accurately get each subject into the correct category.**
7.  Do not include R output without complete sentences describing what
    you are doing in each step, and what you conclude from that work.

## Question 2. (30 points)

Now, look at the complete data, describing all eight practices (the
names are Center, Elm, Highland, King, North, Plympton, Sycamore and
Walnut.)

Does which **insurance** status a person has seem to have a meaningful
impact on their **systolic blood pressure**, adjusting for whether or
not they have a prescription for a **beta-blocker**? Decide whether your
model should include an interaction term in a sensible way (providing a
graph to help us understand your reasoning), and then fit your choice of
model using the `lm` function in R.

**Be sure to provide a written explanation of your findings, in complete
sentences**. In that explanation, you should address both the overall
quality of fit and the interpretation of the coefficients of your chosen
model.

1.  As a hint, one graph you might use would be one to assess the need
    for an interaction term, probably via a plot of means. Another graph
    (or perhaps table) to consider for insight would look at the
    relationship between **insurance** and **beta-blocker** status in
    these subjects.
2.  Do not include R output without complete sentences describing what
    you are doing in each step, and what you conclude from that work.

## Question 3. (20 points)

Identify an important idea which resonates for you from your reading of
the Jeff Leek’s *How To Be a Modern Scientist*. Please identify a
specific example of how this idea has helped or might help you deal with
an issue that comes up in your life as a scientist.

Write a short essay (between 150 and 250 words is appropriate) using
clearly constructed and complete sentences to respond to this. The essay
should be composed using R Markdown.

-   We encourage you to provide brief citations or quotes from Leek and
    elsewhere as needed.

## Question 4. (10 points)

Please tell us your Github user name.

-   To sign up for a (free) Github account, visit github.com and click
    on the Sign up button (usually, it’s on the top right.)
-   To learn more about Git and Github, we recommend
    <https://happygitwithr.com/>.

## Please add the session information.

Finally, at the end of this lab and all subsequent assignments
(including the projects), please add the session information. My
preferred way for you to do this for 432 is…

``` r
xfun::session_info()
```

the results of which are shown below.

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
      askpass_1.1         assertthat_0.2.1    backports_1.3.0    
      base64enc_0.1-3     bit_4.0.4           bit64_4.0.5        
      blob_1.2.2          broom_0.7.10        callr_3.7.0        
      cellranger_1.1.0    checkmate_2.0.0     cli_3.1.0          
      clipr_0.7.1         cluster_2.1.2       colorspace_2.0-2   
      compiler_4.1.2      cpp11_0.4.2         crayon_1.4.2       
      curl_4.3.2          data.table_1.14.2   DBI_1.1.1          
      dbplyr_2.1.1        digest_0.6.28       dplyr_1.0.7        
      dtplyr_1.1.0        ellipsis_0.3.2      evaluate_0.14      
      fansi_0.5.0         farver_2.1.0        fastmap_1.1.0      
      forcats_0.5.1       foreign_0.8-81      Formula_1.2-4      
      fs_1.5.0            gargle_1.2.0        generics_0.1.1     
      ggplot2_3.3.5       glue_1.4.2          googledrive_2.0.0  
      googlesheets4_1.0.0 graphics_4.1.2      grDevices_4.1.2    
      grid_4.1.2          gridExtra_2.3       gtable_0.3.0       
      haven_2.4.3         here_1.0.1          highr_0.9          
      Hmisc_4.6-0         hms_1.1.1           htmlTable_2.3.0    
      htmltools_0.5.2     htmlwidgets_1.5.4   httr_1.4.2         
      ids_1.0.1           isoband_0.2.5       jpeg_0.1-9         
      jquerylib_0.1.4     jsonlite_1.7.2      knitr_1.36         
      labeling_0.4.2      lattice_0.20-45     latticeExtra_0.6-29
      lifecycle_1.0.1     lubridate_1.8.0     magrittr_2.0.1     
      MASS_7.3.54         Matrix_1.3-4        methods_4.1.2      
      mgcv_1.8.38         mime_0.12           modelr_0.1.8       
      munsell_0.5.0       nlme_3.1.153        nnet_7.3-16        
      openssl_1.4.5       parallel_4.1.2      pillar_1.6.4       
      pkgconfig_2.0.3     png_0.1-7           prettyunits_1.1.1  
      processx_3.5.2      progress_1.2.2      ps_1.6.0           
      purrr_0.3.4         R6_2.5.1            rappdirs_0.3.3     
      RColorBrewer_1.1-2  Rcpp_1.0.7          readr_2.1.0        
      readxl_1.3.1        rematch_1.0.1       rematch2_2.1.2     
      reprex_2.0.1        rlang_0.4.12        rmarkdown_2.11     
      rpart_4.1-15        rprojroot_2.0.2     rstudioapi_0.13    
      rvest_1.0.2         scales_1.1.1        selectr_0.4.2      
      splines_4.1.2       stats_4.1.2         stringi_1.7.5      
      stringr_1.4.0       survival_3.2-13     sys_3.4            
      tibble_3.1.5        tidyr_1.1.4         tidyselect_1.1.1   
      tidyverse_1.3.1     tinytex_0.35        tools_4.1.2        
      tzdb_0.2.0          utf8_1.2.2          utils_4.1.2        
      uuid_1.0.3          vctrs_0.3.8         viridis_0.6.2      
      viridisLite_0.4.0   vroom_1.5.6         withr_2.4.3        
      xfun_0.27           xml2_1.3.2          yaml_2.2.1         

### End of Lab 01
