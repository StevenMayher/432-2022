432 Lab 06 for Spring 2022
================

Version: 2022-02-01 09:46:04

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

# Question 1 (25 points)

Tell us about the most useful thing (an insight, example or key idea)
that you learned from reading Nate Silver’s *The Signal and the Noise*.
Be sure to specify **in detail** how this insight/example/idea connects
to your own life, or work. Specify at least one quote from the book that
discusses this issue, and explain the context.

Be sure that when we finish your essay we have a clear understanding of
how reading this book has changed the way you think about the thing you
describe or things related to it.

## Specifications for the essay

In reading your essay, we will look for the following specifications to
be met:

1.  Length is between 200 and 400 words.
2.  English is correctly used throughout, and there are no
    typographical, grammatical or syntax errors.
3.  A key idea is identified and clearly stated that actually appears in
    *The Signal and the Noise*.
4.  An accurate and properly cited quote from the book is provided that
    is relevant to the identified key idea.
5.  The context for the quote within Silver’s book is described in the
    essay.
6.  The essay clearly specifies how the idea in the book has changed
    their way of thinking about something which is explained in the
    essay.
7.  The essay is clearly written, in general.
8.  The essay is interesting to read.

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

# Question 5 (20 points)

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

### This is the end of Lab 05.
