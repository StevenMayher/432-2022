432 Lab 03 for Spring 2022
================

Version: 2022-02-09 19:24:45. Note that Part B was substantially revised
on 2022-02-06.

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

# Part A (40 points)

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

# Part B (45 points)

Here, we will walk through the process of fitting and evaluating linear
regression fits to predict a subject’s estimated (neighborhood) median
income on the basis of the following five predictors:

-   the subject’s neighborhood high school graduation rate,
-   the subject’s race category
-   the subject’s Hispanic/Latinx ethnicity category,
-   the subject’s age, and
-   the subject’s current tobacco status.

## Preliminary work

Start your work by completing the following tasks to create a tibble
that we’ll call `hbp_b` in the answer sketch:

1.  Exclude the 25 subjects in `hbp3456` who have missing values of
    either `hsgrad` or `income`.
2.  Restrict your data to the variables we’ll use in our models for Part
    B (the five predictors listed above, and the estimated neighborhood
    income) and the subject identifying code (the `record`).
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

    # A tibble: 1,000 x 8
       record income hsgrad race     eth_hisp   age tobacco sqrtinc
       <chr>   <int>  <dbl> <fct>    <fct>    <int> <fct>     <dbl>
     1 903574  34800   94.9 White    No          48 Current    187.
     2 926837  24700   74.2 AA_Black No          55 Current    157.
     3 929198  14700   40   AA_Black No          35 Never      121.
     4 932367  24700   74.2 AA_Black No          41 Never      157.
     5 925592  65600   92.2 <NA>     <NA>        61 Never      256.
     6 932404  18500   67.8 AA_Black No          67 Never      136.
     7 933953  21500   84.4 White    No          72 Never      147.
     8 911527  23000   83.6 White    No          62 Never      152.
     9 918228  13400   70.3 AA_Black No          52 Current    116.
    10 930262  48300   90   <NA>     <NA>        73 Never      220.
    # ... with 990 more rows

## Question 5. (5 points)

How many missing values do you have in each of the important variables
in your `hbp_b` tibble? The important variables are your outcome (square
root of estimated neighborhood income) and the five predictors.

## Question 6. (10 points)

Using the entire sample in `hbp_b`, obtain an appropriate Spearman
*ρ*<sup>2</sup> plot and use it to identify a good choice of a single
non-linear term that adds exactly two degrees of freedom to the main
effects model using all five predictors for `sqrtinc`. Specify your
choice of non-linear term.

## Question 7. (10 points)

Fit the main effects model for `sqrtinc` using `ols` in the `hbp_b`
sample, and call that model `m1`. Plot the effect summary (using
`plot(summary(m1))`) for model `m1` and carefully explain the meaning of
the `hsgrad` coefficient shown in that plot in a complete English
sentence.

-   Hint 1: you are permitted to also fit the model using `lm`, if that
    is useful to you.
-   Hint 2: If you use `anova()` on model `m1` you should have 8 total
    degrees of freedom in your model.

## Question 8. (10 points)

Fit a new model using `ols`, for `sqrtinc` using all five main effects,
plus the non-linear term you identified in Question 7 in the `hbp_b`
sample, and call that model `m2`. Plot the effect summary (using
`plot(summary(m2))`) for model `m2`, and explain the meaning of the
`tobacco` coefficient shown in the plot in a complete English sentence.

-   Hint 1: you are permitted to also fit the model using `lm`, if that
    is useful to you.
-   Hint 2: If you use `anova()` on model `m2` you should have 2
    non-linear degrees of freedom, and 10 total degrees of freedom in
    your model.

## Question 9. (10 points)

You’ve now fit models `m1` and `m2`. For each model, obtain the
following summary statistics: the uncorrected raw *R*<sup>2</sup> value,
the AIC and BIC. Then validate the model’s *R*<sup>2</sup> and MSE
values using `set.seed(2022)` and 40 bootstrap replications.

Now, report the five results you obtained for each model in an
attractive, well-formatted table. Then write a sentence or two
explaining what your findings mean about the performance of the two
models.

# Part C. Reaction to Silver’s *The Signal and the Noise* (15 points)

## Question 10. (15 points)

Identify an important thing that you learned about prediction from your
reading of Nate Silver’s *The Signal and the Noise* either in Chapter 2
(about political predictions) or in chapters 3 (baseball), 4 (weather)
or 5 (earthquakes). What does this thing you learned suggest to you
about the way you build prediction models, and how can you adopt this
new way of thinking to improve the models you’ll generate in this Lab
and elsewhere in your scientific life?

Write a short essay (between 150 and 250 words is appropriate: there are
170 words in the Question 11 instructions) using clearly constructed and
complete sentences to respond to this. The essay should be composed
using R Markdown.

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
