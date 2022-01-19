432 Lab 03 for Spring 2022
================

Version: 2022-01-19 17:51:13

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://github.com/THOMASELOVE/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that is the result of applying your R Markdown file to the `hbp3456.csv`
data, available on [our Data and Code
page](https://github.com/THOMASELOVE/432-data), as well as [in the data
subfolder](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab03/data)
for this Lab.

Start a separate R Project for Lab 03, as your first step, and place the
data in that project’s directory or (if you want to match what I did) in
a data sub-directory under that project’s directory.

There is no template for Lab 03. Please feel free to make use of one of
the templates we’ve provided for a previous Lab, or use an approach that
works well for you.

# The Data

This lab again uses the `hbp3456` data, from Lab 01. See [the Lab 01
materials](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab01)
for details on that data set.

# Part A (40 points, 10 points for each question)

Begin with the `hbp3456` data restricted to the following four
practices: Center, Elm, Plympton and Walnut, and to subjects with
complete data on the `ldl` variable. Now, build a logistic regression
model to predict whether the subject has a statin prescription based on:

-   the subject’s current LDL cholesterol level
-   which of the four practices they receive care from, along with
-   the subject’s age.

## Question 1. (10 points)

Fit two models: one with and one without an interaction term between the
practice and the LDL level. Include the `age` variable in each model
using a restricted cubic spline with 4 knots, but without any
interaction with the other predictors. Display the coefficients of your
two models.

## Question 2. (10 points)

For the “no interaction” model from Question 1, interpret the odds ratio
associated with the `ldl` main effect carefully, specifying a 90%
uncertainty interval and what we can conclude from the results.

-   To obtain a 90% confidence (uncertainty) interval with a fit using
    one of the `rms` fitting functions rather than the default 95%
    interval, the appropriate code would be
    `summary(modelname, conf.int = 0.9)`.
-   Note that in Questions 2 and 3, we assume you will describe the
    `ldl` main effect by considering the case of Harry and Sally. Harry
    has an `ldl` value of 142, equal to the 75th percentile `ldl` value
    in the data. Sally has an `ldl` value of 85, equal to the 25th
    percentile `ldl` value in the data. Assume Harry and Sally are the
    same `age` and receive care at the same `practice`. So the odds
    ratio of interest here compares the odds of `statin` prescription
    for Harry to the odds of `statin` prescription for Sally.

## Question 3. (10 points)

Now using the “interaction” model from Question 1, please interpret the
effect of `ldl` on the odds of a statin prescription appropriately,
specifying again what we can conclude from the results. A detailed
description of the point estimate(s) will be sufficient here.

-   In Question 3, we want you to describe the `ldl` main effect by
    considering the case of Harry and Sally. Harry has an `ldl` value of
    142, equal to the 75th percentile `ldl` value in the data. Sally has
    an `ldl` value of 85, equal to the 25th percentile `ldl` value in
    the data. Assume Harry and Sally are the same `age` and receive care
    at the same `practice`. So the odds ratio of interest here compares
    the odds of `statin` prescription for Harry to the odds of `statin`
    prescription for Sally. But now, you need to be able to do this
    separately for each individual level of `practice`, since `practice`
    interacts with `ldl`. There are at least two ways to accomplish
    this.
    -   In one approach, you would create predicted odds values for
        Harry and Sally, assuming a common age (40 would be a reasonable
        choice, and it’s the one used in the answer sketch) with `ldl`
        set to 142 for Harry and 85 for Sally, but creating four
        different versions of Harry and Sally (one for each practice.)
        Then use those predicted odds within each practice to obtain
        practice-specific odds ratios.
    -   In the other approach, you could convince the `rms` package to
        use a different practice as the choice for which adjustments are
        made. By default, `datadist` chooses the modal practice. To
        change this, you’d need to convince `datadist` instead to choose
        its practice based on which practice is the first one, and
        relevel the practice factor accordingly. So, if you’d releveled
        the practice data so that Elm was first and placed that into a
        tibble called `dataelm`, you could use the following adjustment
        to the `datadist` call to ensure that the adjustments made by
        `datadist` used Elm instead of the modal practice.

<!-- -->

    d_elm <- datadist(dataelm, adjto.cat = "first")
    options(datadist = "d_elm")

## Question 4. (10 points)

Now, compare the effectiveness of your two fitted models (the
“interaction” and “no interaction” models) from Question 1 and draw a
reasoned conclusion about which of those two models is more effective in
describing the available set of observations (after those without
`statin` data are removed) from these four practices. An appropriate
response will make use of at least two different validated assessments
of fit quality. Be sure to justify your eventual selection (between the
“interaction” or “no interaction” model) with complete sentences.

-   The natural choices for validated assessments of fit quality in
    Question 4 are a bootstrap-validated C statistic and a
    bootstrap-validated Nagelkerke *R*<sup>2</sup>. In the answer
    sketch, we will use `2022` as our random seed for this work, and
    we’ll do the default amount of bootstrap replications.

# Part B (40 points, 4 points per question)

Here, we will walk through the process of fitting and evaluating two
linear regression fits (one fit with `lm` and the other with `stan`) to
predict **the square root** of a subject’s estimated (neighborhood)
median income on the basis of the main effects of the following four
predictors:

-   the subject’s neighborhood high school graduation rate,
-   the subject’s race category
-   the subject’s Hispanic/Latinx ethnicity category, and
-   the subject’s current tobacco status.

## Preliminary work

Start your work by completing the following tasks to create a tibble
that we’ll call `hbp_b` in the answer sketch:

1.  Exclude the 25 subjects in `hbp3456` who have missing values of
    either `hsgrad` or `income`.
2.  Restrict your data to the variables we’ll use in our models for
    Question 2 (the four predictors listed above, and the estimated
    neighborhood income) and the subject identifying code (the
    `record`).
3.  Ensure that all character variables (other than `record`) in your
    tibble are recognized as factors.
4.  Create a new variable called `sqrtinc` which will serve as your
    response (outcome) for your regression modeling, within your tibble.
5.  Use `set.seed(432)` and `slice_sample()` to select a random sample
    of 1000 subjects from the tibble.

Your resulting `hbp_b` tibble should look like this:

``` r
hbp_b
```

    # A tibble: 1,000 x 7
       record income hsgrad race     eth_hisp tobacco sqrtinc
       <chr>   <int>  <dbl> <fct>    <fct>    <fct>     <dbl>
     1 903574  34800   94.9 White    No       Current    187.
     2 926837  24700   74.2 AA_Black No       Current    157.
     3 929198  14700   40   AA_Black No       Never      121.
     4 932367  24700   74.2 AA_Black No       Never      157.
     5 925592  65600   92.2 <NA>     <NA>     Never      256.
     6 932404  18500   67.8 AA_Black No       Never      136.
     7 933953  21500   84.4 White    No       Never      147.
     8 911527  23000   83.6 White    No       Never      152.
     9 918228  13400   70.3 AA_Black No       Current    116.
    10 930262  48300   90   <NA>     <NA>     Never      220.
    # ... with 990 more rows

The ten questions (Questions 5 - 14) below will walk you through the
process of comparing models fit with the `lm` and `stan` engines for
these data. The steps are meant to be completed in the specified order.

## Question 5. (4 points)

How many missing values do you have in each of the important variables
in your `hbp_b` tibble? The important variables are your outcome (square
root of estimated neighborhood income) and the four predictors.

## Question 6. (4 points)

Use an appropriate method from `tidymodels` to split the data into
training and testing samples, with 70% of the data in the training
sample. Use `set.seed(2022)` to create your split. We’ll call the
training sample `b_train` in the sketch, and the testing sample
`b_test`.

## Question 7. (4 points)

Build a recipe for your model, which we’ll call `b_rec` in the sketch.
This recipe should work for either of the models you fit and include all
necessary pre-processing, which includes the following four elements:

-   specifying the roles of the outcome and the predictors,
-   using imputation via bagged tree models for all predictors with
    missing data,
-   creating dummy (indicator) variables for all categorical predictors,
-   normalizing all quantitative predictors

## Question 8. (4 points)

Specify modeling engines, separately, for the `lm` and `stan` fits you
will create. For the Bayesian fit using `stan`, use as a prior Student’s
t distribution with one degree of freedom for all parameters.

## Question 9. (4 points)

Create a workflow for the `lm` fit, and then use it to fit the `lm`
model to the training data. Summarize the fit with `tidy`.

## Question 10. (4 points)

Create a workflow for the `stan` fit, and then use it to fit the `stan`
model to the training data. Summarize the fit with `tidy`. If you get an
error message, use `broom.mixed::tidy()` to do the tidying.

## Question 11. (4 points)

Graph the tidied point estimates and 95% confidence intervals for the
coefficients (excluding the intercept) in the two models in an
attractive `ggplot` for comparison.

## Question 12. (4 points)

Interpret the results from the tidied summaries you generated in
Question 10, and the graph you generated in Question 11. Which
coefficients change substantially between the two fits (and in what
direction do they change), and which do not?

## Question 13. (4 points)

Assess performance in the training sample using the two fits and three
performance measures, specifically the root mean squared error, the
R-squared, and the mean absolute error. Which model appears to perform
better within the training sample? Is there a substantial difference
between the models in terms of performance on these metrics?

## Question 14. (4 points)

Finally, make predictions into the test sample using the two fits and
the same three performance measures discussed in Question 13. Now, which
model appears to perform better within the test sample? Is there a
substantial difference between the models in terms of performance on
these metrics?

# Part C. Reaction to Silver’s *The Signal and the Noise* (20 points)

## Question 15. (20 points)

Identify an important thing that you learned about prediction from your
reading of Nate Silver’s *The Signal and the Noise* either in Chapter 2
(about political predictions) or in chapters 3 (baseball), 4 (weather)
or 5 (earthquakes). What does this thing you learned suggest to you
about the way you build prediction models, and how can you adopt this
new way of thinking to improve the models you’ll generate in this Lab
and elsewhere in your scientific life?

Write a short essay (between 150 and 250 words is appropriate) using
clearly constructed and complete sentences to respond to this. The essay
should be composed using R Markdown.

-   We encourage you to provide brief citations or quotes from Silver
    and elsewhere as needed.
-   In citing *The Signal and the Noise* a quotation with (Silver,
    Chapter X) is sufficient.
-   In citing another work, a more detailed citation is appropriate.
    Citations and quotations do not count towards the suggested word
    limit.

### Please add the session information.

``` r
xfun::session_info()
```

### This is the end of Lab 03.
