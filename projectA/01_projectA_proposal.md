Task 1 (The Project Proposal)
================

-   [Use a template, please!](#use-a-template-please)
    -   [Tips for using the Templates](#tips-for-using-the-templates)
-   [Getting Started](#getting-started)
    -   [Title and Authors](#title-and-authors)
    -   [R Packages and Setup](#r-packages-and-setup)
-   [There are 10 sections to the proposal. Here they
    are…](#there-are-10-sections-to-the-proposal-here-they-are)
-   [1 Data Source](#data-source)
-   [2 The Subjects](#the-subjects)
-   [3 Loading and Tidying the Data](#loading-and-tidying-the-data)
    -   [3.1 Loading the Raw Data](#loading-the-raw-data)
    -   [3.2 Cleaning the data (will be multiple
        subsections)](#cleaning-the-data-will-be-multiple-subsections)
-   [4 The Tidy Tibble](#the-tidy-tibble)
    -   [4.1 Listing the Tibble](#listing-the-tibble)
    -   [4.2 Size and Identifiers](#size-and-identifiers)
    -   [4.3 Save the tidied tibble as an .Rds
        file](#save-the-tidied-tibble-as-an-rds-file)
-   [5 The Code Book](#the-code-book)
    -   [5.1 Defining the Variables](#defining-the-variables)
    -   [5.2 Numerical Description](#numerical-description)
-   [6 Linear Regression Plans](#linear-regression-plans)
    -   [6.1 My Quantitative Outcome](#my-quantitative-outcome)
    -   [6.2 My Planned Predictors (Linear
        Model)](#my-planned-predictors-linear-model)
-   [7 Logistic Regression Plans](#logistic-regression-plans)
    -   [7.1 My Binary Outcome](#my-binary-outcome)
    -   [7.2 My Planned Predictors (Logistic
        Model)](#my-planned-predictors-logistic-model)
-   [8 Affirmation](#affirmation)
-   [9 References](#references)
-   [10 Session Information](#session-information)
-   [Submission Requirements](#submission-requirements)
-   [How Will We Evaluate the
    Proposal?](#how-will-we-evaluate-the-proposal)
-   [Links](#links)

Last Update: 2022-01-19 23:07:23

# Use a template, please!

We built two different templates to make it easier to meet the
requirements specified here. We really want you to use one of them, to
avoid problems with missing or hard-to-find information.

The two templates contain the same information, but use different
formatting styles. Pick the one that pleases you.

You’ll find [the templates
here](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/templates)
and these are also available in our Shared Drive. Note that the
templates for the Final Submission simply add three sections to the
templates for the Proposal.

## Tips for using the Templates

-   Follow the guidance in the YAML code at the top of the template
    you’ve chosen to insert your title and author information.
-   Unless you really know what you’re doing, I would leave the rest of
    the YAML code alone.
-   Do not use `echo = FALSE` anywhere in your R Markdown code.
-   As in the templates, use `knitr::opts_chunk$set(comment=NA)` in the
    setup chunk to avoid R output being preceded by hashtags.
-   Do use the ENTER key sufficiently to prevent any code chunks in the
    HTML file from requiring a scrolling window in order to be seen
    (note that this is a particularly common problem when people list
    many, many packages on the same line, separated by semicolons.)
-   Please use the headings and subheadings for materials supplied in
    this document and in each of the templates, and place an ENTER
    before and after each new section heading, subheading, code chunk or
    paragraph of text.

# Getting Started

## Title and Authors

Your project should have a meaningful title (not containing the words
“432” or “Project” or “Proposal”) but rather something describing your
actual data and plans.

-   Please keep the title to no more than 80 characters, including
    spaces.

## R Packages and Setup

You’ll load necessary packages at the start in an unnumbered section of
your work (follow the approach in the templates.)

-   Do not use `source("Love-boost.R")` or any other R script or package
    unless you actually need something it provides.
-   Do not load core elements of `tidyverse` or `tidymodels` (like
    `dplyr` or `ggplot2`) separately. instead just load the
    meta-packages, and do so last.
-   Use `message = FALSE` in the code chunk where the packages are
    listed to eliminate the messages in the HTML showing warnings about
    when packages were built or how objects were masked.

# There are 10 sections to the proposal. Here they are…

# 1 Data Source

Provide complete information on the source of the data: how did you get
it, how was it gathered, by whom, in what setting, for what purpose, and
using what sampling strategy.

# 2 The Subjects

A description (one or two sentences should be sufficient) of who or what
the subjects (rows) are in your data set.

# 3 Loading and Tidying the Data

## 3.1 Loading the Raw Data

Provide code to ingest the raw data.

## 3.2 Cleaning the data (will be multiple subsections)

Tidy and clean up the data to meet all necessary requirements for your
modeling work. This is likely to require multiple sub-sections as you
tackle different tasks for different sets of variables. Use the
tidyverse for data management whenever possible. Some of things you need
to do here…

-   Eliminate all variables that are not going to be used (either as
    identifiers, outcomes or inputs) in your planned analyses.
-   Change variable names to more meaningful ones, although it’s helpful
    to keep them at 10 characters or less. Use `clean_names()` from the
    `janitor` package as necessary to clean up and standardize variable
    names.
-   Sample the data as needed to ensure that you meet the data set size
    specifications (no more than 1200 rows, for instance.)
-   Convert all variables to appropriate types (factors, etc.) as
    needed, and complete appropriate checks of the values for all
    variables.
-   If you have prospective inputs (predictors) that are
    multi-categorical with more than 6 categories, collapse them to six
    or fewer categories in a rational way at this stage.
-   Ensure that all categorical variables have at least 30 observations
    at each level.
-   Your tidied data set at the end of this section should be arranged
    to adhere to the requirements for minimum and maximum number of rows
    and columns, with a row (subject) identifier at the far left. That
    identifier should have a unique value for each row, and should be
    saved as a character variable in R.
-   We expect your final tibble to have some missing values. Do not
    impute or delete these, but do be sure they are correctly identified
    as missing values by R.

**Note** Do not list the entire tibble or print out large strands of R
output (like summaries of the entire tibble) in this section.

# 4 The Tidy Tibble

## 4.1 Listing the Tibble

In this section, you should start by listing the tibble you created with
your work in Proposal Section 3, with all variables correctly imported
(via your code) as the types of variables (factor/integer/numeric, etc.)
that you need for modeling.

-   This should be a listing, not a glimpse or anything else. Just type
    in the name of your tibble.
-   The resulting list should be limited to the first 10 rows of your
    data.

## 4.2 Size and Identifiers

Write a sentence specifying the number of rows and the number of columns
in your tibble, and this should match the R output.

Then identify the name of the variable that provides the identifier for
each row in your tidy tibble, and demonstrate that each row has a unique
value for that variable, and that the variable is represented as a
character in R.

-   One way to do this is to run the `n_distinct` function from the
    `dplyr` package on this particular variable.
-   Do not present summary or descriptive results on every variable in
    the whole tibble here - you’ll do that in Proposal Section 5.

## 4.3 Save the tidied tibble as an .Rds file

Now, please save the tidied data set as an .Rds file (using saveRDS or
the equivalent), which you’ll need to submit to us.

# 5 The Code Book

## 5.1 Defining the Variables

In this section, provide a beautiful codebook which tells us (at a
minimum) the following information for each variable in the tibble you
printed and saved in Section 4.

1.  The name of the variable in your tibble.
2.  The role of the variable in your planned analyses (options include
    identifier, outcome, or input)
3.  The type of variable for each outcome or input (options are
    categorical, in which case tell us how many categories, or
    quantitative)
4.  A short description of the meaning of the variable.
    -   This should include the units of measurement if the variable is
        quantitative, and a list of the possible values if the variable
        is categorical.

As an example, here’s a part of a simple table:

| Variable    | Role       | Type  | Description                                    |
|-------------|------------|-------|------------------------------------------------|
| `subjectID` | identifier | \-    | character code for subjects                    |
| `sysbp`     | outcome    | quant | Most Recent Systolic Blood Pressure, in mm Hg  |
| `statin`    | input      | 2-cat | Has a current statin prescription? (Yes or No) |

## 5.2 Numerical Description

Here, run the `describe` command from the `Hmisc` package on your entire
tibble. Be sure that the results match up with what you’ve described in
defining the variables, and that the same variables appear, in the same
order, in the codebook and in these results.

# 6 Linear Regression Plans

Begin this section by specifying a question that you hope to answer with
the linear model you are proposing. Eventually, you will need to answer
this question (in Task 2).

## 6.1 My Quantitative Outcome

This subsection tells us what you will use your linear regression model
to explain or predict.

-   Tell us the name in the tibble of the linear regression outcome you
    will use (this should one of the outcomes you identified earlier)
    and state why you are interested in predicting this variable.
-   Provide a count of the number of rows in your data with complete
    information on this outcome.
-   Provide a nicely labeled histogram or other graphical summary of
    your outcome to supplement the numerical description you provided in
    Proposal Section 5.2.
-   Comment briefly on the characteristics of the outcome’s
    distribution. Is your outcome skewed or symmetric, is it discrete or
    fairly continuous, is there a natural transformation to consider?
-   Ensure that the variable you have selected meets the standard for a
    quantitative variable used in this Project, specifically that it has
    at least 10 different, ordered, observed values.

## 6.2 My Planned Predictors (Linear Model)

Now, tell us precisely which four (or more) candidate predictors
(inputs) you intend to use for your linear regression model.

-   Please use the variable names that appear in your code book and
    tibble.
-   Demonstrate to us that you have at least one input which is
    quantitative, specifically that it has at least 10 different,
    ordered, observed values.
-   Demonstrate to us that you have at least one categorical input which
    has between 3 and 6 categories, that will be used as a factor in
    your modeling, and that has at least 30 observations in each level
    of the factor.
-   Demonstrate that the total number of candidate predictors you
    suggest is no more than 4 + (N-100)/100 candidate regression inputs,
    rounding down, where N is the sample size for your tibble.

# 7 Logistic Regression Plans

Begin this section by specifying a question that you hope to answer with
the logistic model you are proposing. Eventually, you will need to
answer this question (in Task 2).

## 7.1 My Binary Outcome

This subsection tells us what you will use your logistic regression
model to explain or predict.

-   Tell us the name in the tibble of the logistic regression outcome
    you will use (this should one of the outcomes you identified
    earlier) and state why you are interested in predicting this
    variable.
-   Provide a count of the number of rows in your data with each of the
    two possible values of this outcome. Indicate whether you have any
    missing values.

## 7.2 My Planned Predictors (Logistic Model)

Now, tell us precisely which four (or more) candidate predictors you
intend to use for your logistic regression model.

-   If you are using some of the same predictors as in your linear
    regression model, there’s no need to repeat yourself. Simply tell us
    which variables you’ll use again, and then provide descriptions for
    any new predictors that did not appear in your plans for the linear
    model.

# 8 Affirmation

Next you need to affirm that the data set meets all of the project
requirements, especially that the data can be shared freely over the
internet, and that there is no protected information of any kind
involved.

The text we want to see here is “I am certain that it is completely
appropriate for these data to be shared with anyone, without any
conditions. There are no concerns about privacy or security.”

If you are unsure as to whether this is true, select a different data
set.

# 9 References

References (you’ll need one to describe the source of your data, at
least) go here.

# 10 Session Information

Please provide session information by running `xfun::session_info()`.
This will produce something like this…

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
      base64enc_0.1.3 compiler_4.1.2  digest_0.6.28   evaluate_0.14  
      fastmap_1.1.0   glue_1.4.2      graphics_4.1.2  grDevices_4.1.2
      highr_0.9       htmltools_0.5.2 jquerylib_0.1.4 jsonlite_1.7.2 
      knitr_1.36      magrittr_2.0.1  methods_4.1.2   rlang_0.4.12   
      rmarkdown_2.11  stats_4.1.2     stringi_1.7.5   stringr_1.4.0  
      tinytex_0.35    tools_4.1.2     utils_4.1.2     xfun_0.27      
      yaml_2.2.1     

# Submission Requirements

The proposal is to be submitted via file uploads to
[Canvas](https://canvas.case.edu). Your submitted proposal will include
the following:

1.  A raw data file (we prefer a `.csv` file) containing your raw data
    prior to any cleaning or tidying. This should be the file you load
    at the beginning of Proposal Section 3.1.
    -   Do not submit a raw data file with more than 5000 rows or with
        more than 25 columns. Should the original raw data available to
        you contain more than 5000 rows or more than 25 columns, reduce
        it in scope prior to building your Proposal document, and treat
        the “reduced” version as your “raw” version in what you include
        in your proposal and what you submit to us.
    -   Remember that your final “clean” data set is restricted in size
        even further, to no more than 1200 rows and also in terms of the
        number of columns.
    -   Should the original raw source of the data come in some other
        format besides `.csv`, you can either convert it to `.csv` or
        submit it in its original form, but if you take the latter
        course, you will need to provide complete code in your proposal
        to ingest the data into R.
    -   If your project uses an R package to extract raw data from the
        internet (for example, data from NHANES) then you will not
        submit a raw file here.
2.  A “tidied” R data set (saved in the .Rds format in Proposal Section
    4.3) containing your cleaned, tidy data obtained using the code you
    develop in the proposal.
    -   This tidied data set must include a subject identifier as the
        far left column saved as a character variable in R, followed by
        the outcomes you will use for the linear and logistic regression
        models, followed by your regression inputs in their final form,
        and then any other necessary variables.
    -   All variables which you plan to treat as factors should be saved
        as factors with appropriately ordered levels in your submitted R
        data set.
3.  An R Markdown file, built using one of our two available templates,
    which contains the information required in the proposal as described
    above.
    -   If you decide to modify these templates, please retain the order
        of items in the table of contents to facilitate our finding what
        you did quickly.
4.  An HTML document which is the unedited result of knitting your
    submitted R Markdown file. This is the main document we will
    interact with in reviewing your proposal, so be sure to proofread it
    closely.

# How Will We Evaluate the Proposal?

To evaluate your work, we will have to receive all necessary materials
(raw data if needed, clean data as .Rds, .Rmd and HTML) successfully.

-   If you are working with a partner, one of you must submit the
    proposal, and the other must submit a single-page text document
    (Word is fine) which states that their partner will submit the joint
    proposal, before we will evaluate your work.
-   There are 10 elements we will assess, worth one point each.
-   If you receive a grade lower than 10, we will specify the
    problematic elements and then you will have to redo the work
    (quickly) to fix the problems until we are satisfied.
-   One you have successfully completed all tasks, you will receive full
    credit for the proposal and can then move on to Task 2 (Analysis and
    Presentation).

# Links

-   [General Project A
    Instructions](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/00_projectA_general.md)
-   [Templates for Project
    A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/templates)
    also posted to our Shared Drive.
-   Detailed [Instructions for Project A Task 2 (Analyses and
    Presentation)](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/02_projectA_analyses.md)
-   [Main Page for Project
    A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA)
