Task 2 (Analyses and Presentation)
================

-   [Your Proposal is Approved. Now
    What?](#your-proposal-is-approved-now-what)
-   [The Portfolio](#the-portfolio)
    -   [Section 8: Linear Regression
        Analyses](#section-8-linear-regression-analyses)
    -   [Section 9: Logistic Regression](#section-9-logistic-regression)
    -   [Section 10: The Discussion](#section-10-the-discussion)
-   [The Presentation](#the-presentation)
    -   [Your Audience](#your-audience)
    -   [Outline of the Presentation](#outline-of-the-presentation)
-   [Submission Requirements](#submission-requirements)
-   [Evaluating Your Final Materials](#evaluating-your-final-materials)
    -   [Evaluating the Portfolios](#evaluating-the-portfolios)
    -   [Evaluating the Presentations /
        Slides](#evaluating-the-presentations--slides)
-   [Links](#links)

Last Update: 2022-01-19 23:19:24

# Your Proposal is Approved. Now What?

You have two tasks yet to complete.

1.  Complete the portfolio for Project A by adding in your linear
    regression modeling and logistic regression modeling, and a
    discussion section to the Proposal we’ve approved.
2.  Produce a no more than 5 minute summary video of (a small part of)
    your Project A results.

# The Portfolio

The portfolio submission for Project A consists of 13 sections, 10 of
which come straight from the proposal. The three new sections are
described in what follows.

So the final portfolio should include the following:

-   Sections 1-7 are essentially the same as what you prepared for the
    proposal. You should nail down any details that were not yet
    specified in your original submissions of the proposal. Sections
    6-7, in particular, should now be adjusted as necessary to reflect
    the actual analyses you wound up doing, and if you had to do some
    additional cleaning or create new variables, those elements should
    be developed in sections 3-5.
-   A **new** Section 8 should be labeled “Linear Regression Modeling”
    and is dedicated to that work.
-   A **new** Section 9 should be labeled “Logistic Regression Modeling”
    and is dedicated to that work.
-   A **new** Section 10 should be labeled “Discussion” and is a roughly
    200 word discussion of your thoughts on the process of producing
    this project.
-   Section 11 is where the **Affirmation** goes. You built that in your
    Proposal.
-   Section 12 becomes the **References** section.
-   Section 13 is the session information material, labeled **Session
    Information**, and again you had that in the proposal.

## Section 8: Linear Regression Analyses

In Section 8, we expect you to present all relevant code used to produce
your final results. No output should be presented in this section (or in
Section 9) without commentary. This should describe the fitting and
evaluation of two models: a “main effects” model (model A), and an
“augmented” model (model B). We’re primarily interested in a clear
presentation. The following 8 elements should be presented, in properly
labeled subsections of section 8, using the labels in bold below.

1.  **Missingness** your approach to dealing with missing data, if
    applicable
    -   we prefer imputation (simple or multiple) to complete case
        analysis
    -   if you have a sample with no missing data, specify that (again)
        here
2.  **Outcome Transformation** your approach to transforming the outcome
    variable, including an appropriate Box-Cox assessment
3.  **Scatterplot Matrix and Collinearity** a scatterplot matrix
    including the (possibly transformed) outcome and all predictors that
    make it into your “main effects” model
    -   be sure to evaluate collinearity between predictors, either
        through perusing and discussing the correlations in the
        scatterplot matrix, or with variance inflation factors
4.  **Model A**: your initial “main effects” model
    -   remember that your model must include at least four predictors,
        of which at least one must be quantitative and one must be
        multi-categorical.
    -   we discourage the use of stepwise or other model selection
        strategies, instead please use your problem-based understanding
        to select variables and use them all.
    -   in presenting your main effects model you should show:
        -   a tidied table of regression coefficients
        -   key fit summary statistics like R-square, AIC and BIC, and
            we also suggest you develop and display a validated R-square
            statistic using the `validate` function in `ols` here.
        -   the four key diagnostic plots of residuals, with an
            appropriate interpretation of what you see
5.  **Non-Linearity** your process for making decisions about how to
    capture potential non-linearity
    -   what did the Spearman rho-squared plot suggest and how did you
        spend your degrees of freedom - If the (apparently strongest -
        furthest to the right) predictor in the rho-square plot is
        quantitative, you should be thinking first about a restricted
        cubic spline with 4 or 5 knots,
        -   If the largest rho-square is associated with a binary or a
            multi-categorical predictor, create an interaction term with
            the second-largest rho-squared predictor.
        -   If you still have degrees of freedom you’re willing to spend
            after this, proceed down to the second largest predictor in
            terms of rho-squared, and proceed similarly to the third
            largest after that.
    -   Regardless of your sample size, please use about 6 additional
        degrees of freedom beyond the main effects model to account for
        non-linearity, and add at most 3 non-linear terms to your model.
6.  **Model B**: fitting your “augmented model” incorporating non-linear
    terms
    -   unless you’re doing multiple imputation you’ll want to be sure
        you demonstrate that you can fit this using either `ols` or
        `lm`, since you might need either approach for a complete
        assessment of the model (if you’re doing multiple imputation,
        you can stick with `ols`)
    -   you’ll need at a minimum to present a nomogram and plot of the
        effects from `plot(summary(modelname))` for this augmented
        model, using `ols`.
    -   you’ll want to look at an ANOVA comparison of Model B to Model A
        in order to understand whether the changes you’ve made led to
        statistically detectable improvements in prediction.
    -   you’ll also need to present the residual plots for the model
        you’ve fit, which is easiest to do if you fit the model with
        `lm`.
        -   if you’ve used multiple imputation, prepare a residuals
            vs. fitted values plot and evaluate it using `ols`.
7.  **Validating the Models** the results of a validation comparison of
    the “augmented model” B to the “main effects” model A which should
    help you select a “final model” from the two possibilities. Feasible
    ways to do this include:
    -   an initial partition into training and test samples,
    -   or a k-fold cross-validation strategy,
    -   you may also want to produce validated R-square statistics for
        Model B within `ols` through the `validate` function and present
        a comparison of results across the two models
8.  **Final Model** This section should end with a clear statement of
    the model you prefer (the “main effects model A” or the “augmented
    model B”) based on your overall assessment of fit quality, adherence
    to assumptions as seen in residuals, and whether adding the terms in
    the augmented model yields an improvement that is worth the
    complication of adding the non-linear terms.
    -   You should land on a single, final model, using both statistical
        and non-statistical considerations to make a decision between
        model A and model B.
    -   An appropriate summary of the final model you landed on should
        start with a listing of the model parameters for a model fit to
        the entire data set (after imputation as needed) with
        appropriate confidence intervals, and a table or (better) plot
        of the effect sizes.
        -   Specify the effect sizes for all elements of your final
            model numerically (with both a point estimate and a
            confidence interval), and graphically (with a plot of those
            effects (probably through `plot(summary(yourmodel)`).
        -   Then write a detailed and correct description of the effect
            of **at least one** predictor on your outcome for your
            linear regression model, providing all necessary elements of
            such a description, and link this directly to what the plot
            is telling you.
        -   We prefer you discuss a scientifically meaningful effect,
            should one exist. Pick an effect to describe that is
            interesting to you.
    -   You should display an appropriate (corrected through validation)
        estimate of R-square for your final model
    -   The final part of your summary of the final model should be a
        nomogram with a demonstration of a prediction (and appropriate
        prediction interval) for a new subject of interest.
        -   Your prediction (and its prediction interval) should be back
            transformed to the original scale of your outcome, if you
            transformed your outcome before building your model.

## Section 9: Logistic Regression

In Section 9, we expect you to present all relevant code used to produce
your final results. As in Section 8, no output should be presented in
this section without commentary. Also as in Section 8, this section will
describe the fitting and evaluation of two models: a “main effects”
model (model Y), and an “augmented” model (model Z). We’re primarily
interested in a clear presentation. The following 6 elements should be
presented, in properly labeled subsections of section 9, using the
labels in bold below.

1.  **Missingness** your approach to dealing with missing data, if
    applicable
    -   we prefer imputation (simple or multiple) to complete case
        analysis, but it’s not mandatory
    -   if you have a sample with no missing data, specify that (again)
        here
    -   you can use the same approach as in Section 8, or a different
        one, if you prefer
2.  **Model Y**: your initial “main effects” model
    -   remember that your model must include at least four predictors,
        of which at least one must be quantitative and one must be
        multi-categorical.
    -   we discourage the use of stepwise or other model selection
        strategies here, instead please use your problem-based
        understanding to select variables and use them all.
    -   in presenting your main effects model you should show:
        -   a tidied table of regression coefficients
        -   key fit summary statistics like the Nagelkerke R-square and
            the area under the ROC curve as they are presented in the
            `lrm` output
        -   a confusion matrix based on an explicitly specified
            prediction rule (perhaps `.fitted` >= 0.5, but something
            else if you prefer) and you’ll need to specify the
            specificity, sensitivity and positive predictive value for
            this model.
        -   a nomogram describing the model.
3.  **Non-Linearity** your process for making decisions about how to
    capture potential non-linearity
    -   what did the Spearman rho-squared plot suggest and how did you
        spend your degrees of freedom
        -   If the (apparently strongest - furthest to the right)
            predictor in the rho-square plot is quantitative, you should
            be thinking first about a restricted cubic spline with 4
            knots, maybe 5,
        -   If the largest rho-square is associated with a binary or a
            multi-categorical predictor, create an interaction term with
            the second-largest rho-squared predictor.
        -   If you still have degrees of freedom you’re willing to spend
            after this, proceed down to the second largest predictor in
            terms of rho-squared, and proceed similarly to the third
            largest after that.
    -   Regardless of your sample size, please use between 3 and 6
        additional degrees of freedom beyond the main effects model to
        account for non-linearity, and add no more than 3 non-linear
        terms to your model.
4.  **Model Z**: fitting your “augmented model” incorporating non-linear
    terms
    -   most of you will choose to use `lrm` to do most of this work,
        I’d expect, and that’s fine, but you’ll want to fit the model
        with `glm`, too, to help with building the confusion matrix.
    -   you’ll need at a minimum to present a nomogram and plot of the
        effects from `plot(summary(modelname))` for this augmented
        model, using `lrm`.
    -   you’ll want to look at an ANOVA comparison of Model Z to Model Y
        in order to understand whether the changes you’ve made led to
        statistically detectable improvements in prediction, but don’t
        use this to do model selection.
    -   again, we’ll want you to produce an appropriate confusion matrix
        using the same prediction rule that you used in Model Y, and
        you’ll need to provide (and compare to Model Y) the specificity,
        sensitivity and PPV for Model Z using that prediction rule.
    -   you’ll also need to show the Nagelkerke R-square and C statistic
        from the `lrm` output.
5.  **Validating the Models** the results of a validation comparison of
    the Nagelkerke R-square and the C statistic for the “augmented
    model” Z to the “main effects” model Y through the `validate`
    function in `lrm` fits.
6.  **Final Model** This section should end with a clear statement of
    the model you prefer (the “main effects” model Y or the “augmented”
    model Z) based on your overall assessment of fit quality, and
    whether adding the terms in the augmented model yields an
    improvement that is worth the complication of adding the non-linear
    terms.
    -   You should land on a single, final model, using both statistical
        and non-statistical considerations to make a decision between
        models Y and Z.
    -   An appropriate summary of the final model you landed on should
        start with a listing of the model parameters for a model fit to
        the entire data set (after imputation as needed) in terms of
        odds ratios, with appropriate confidence intervals, and a table
        or (better) plot of the effect sizes.
        -   Specify the effect sizes for all elements of your final
            model numerically (with both an odds ratio point estimate
            and a confidence interval), and graphically (with a plot of
            those effects (probably through `plot(summary(yourmodel)`),
            properly interpreted.
        -   Then write a detailed and correct description of the effect
            of **at least one** predictor on your outcome for your
            chosen logistic regression model, providing all necessary
            elements of such a description, and link this directly to
            what the plot is telling you.
        -   We prefer you discuss a meaningful effect, should one exist.
            Pick an effect to describe that is interesting to you.
    -   Next, we want you to provide a plot of the ROC curve for the
        “final model” in the entire data set.
    -   You should display an appropriate (corrected through validation)
        estimate of Nagelkerke R-square and the C statistic for your
        final model, using the entire data set.
    -   The final part of your summary of the final model should be a
        nomogram with a demonstration of a predicted probability
        associated with two new subjects of interest that differ in
        terms of some of the parameters in your model.
        -   Your predictions in Section 9 should describe two different
            subjects. You don’t have to call them Harry and Sally, but
            it is helpful to give them actual names.

## Section 10: The Discussion

Begin the discussion section by clearly stating the two questions you
posed at the start of Sections 6 and 7 of the Proposal, and then
answering them based on the results of your modeling in Sections 8 and
9.

Next, provide a short (somewhere in the neighborhood of 200 words)
discussion of your thoughts on the entire Project A process. Be sure
that your response here explicitly addresses at least two of the
following four questions:

-   What was substantially harder or easier than you expected, and why?
-   What do you wish you’d known at the start of this process that you
    know now, and why?
-   What was the most confusing part of doing the project, and how did
    you get past it?
-   What was the most useful thing you learned while doing the project,
    and why?

# The Presentation

You (with your partner, if you have one) will build and record a single
slide presentation (not to exceed 5 minutes) of what you feel is **the
single most** important finding from your Project A.

-   If you have a partner, you should record a single presentation with
    both of your voices included for about an equal amount of time, and
    the total time should not exceed 5 minutes.

## Your Audience

Your audience for this presentation includes Dr. Love, the TAs and your
fellow students. Prepare your presentation with that audience in mind.
What will they need to know to understand what you’ve done, and get
excited about it?

## Outline of the Presentation

Your presentation should include fewer than 10 slides.

Your “most important finding” is just going to be one of many
potentially interesting findings in your proposal. Your job in the
presentation is **not** to prove to me that you did a lot of work - I’ll
see that in the portfolio.

Instead, your job in the presentation is to interest your audience in
something you found that is (at least relatively) important. You are
expected to help us understand the following things related to your most
important finding, based on either a linear or logistic model.

You will not be developing any new material for the slides (just
restating and rearranging things you’ve already done and perhaps
constructing a short narrative to help us retain your key findings) once
you have the portfolio. As a result, we encourage you to complete the
portfolio first.

I suggest you develop about 8 slides. This should include…

1.  A title slide
2.  A couple of slides to describe the Subjects, Outcome and Predictors
    -   Make sure we understand who the subjects are, how they were
        selected, what the outcome is and why we should care about it,
        and what predictors are involved in the model you’ll show.
3.  Several slides showing meaningful statistical findings (What should
    we learn from your model?)
    -   What does the model (don’t show us details of multiple models in
        the presentation) say about the relationship between the outcome
        and the predictors?
    -   You’re only showing us one model (of models A, B, Y and Z) in
        the presentation.
    -   How well does this model fit the data you have, and how well
        might it fit in new data?
4.  A couple of slides discussing next steps
    -   It is unlikely that you’ll have a model that is truly
        satisfactory all on its own, so what could be done to improve it
        that you cannot already do with the data you have? What other
        data could be collected, how could the measures be refined,
        could you design a study to get to a more convincing answer?

Make sure that you introduce yourself when you start to speak, over your
title slide if you are working alone. I’m happy to see your face during
the presentation, but this isn’t mandatory. If you are working with a
partner, each of you should introduce yourself at the beginning, and let
me know who’s speaking first.

(Essentially) **every word and every image/table/chart** in your slides
can and should come directly from the materials contained in your HTML
portfolio.

-   The development of the presentation is mostly about selecting useful
    information to present and then arranging it in a way that sticks
    for your audience.
-   Your presentation should include no R code but instead will provide
    nicely formatted figures and tables along with text. Some figures
    don’t work well on slides, like nomograms, without a lot of work.
    Pick something that is both useful and easy to see.
-   Each slide should have a title, indicating the message you want us
    to get from the slide (don’t use generic titles like “Results” or
    “Table 1”).
-   You’ll have to cut out around 95% of your portfolio to create your
    slides, and you should follow your instincts regarding your audience
    (Dr. Love, the TAs and your fellow students are your audience.)
-   Developing the presentation is where **you** have to make decisions
    about what’s most important to show an audience to get them
    interested in your work. That’s a critically important skill.

# Submission Requirements

Submit Task 2 materials to [Canvas](https://canvas.case.edu) in the
“Project A Final Materials” section.

Your submission should include:

1.  Everything you submitted for the Proposal (updated as necessary).
    That includes the raw data, the cleaned (`.Rds`) data, the R
    Markdown file for the complete portfolio including the three new
    sections for Task 2 and all of the materials originally included in
    Task 1, as well as the HTML result from that R Markdown file.

2.  The slides you used in your 5-minute Presentation, so if we cannot
    see something well in your recording (which is a problem), we can
    look at it more closely.

3.  Your video recording (we prefer `.mp4` format) of your 5-minute
    presentation

Again, if you’re working with a partner, one of you should submit all of
this material, and the partner submits a one-page note (Word is fine)
saying who will be responsible for submitting the Project A materials.

# Evaluating Your Final Materials

The TAs and Dr. Love will evaluate the presentations and portfolios
together. Some of the questions we will ask ourselves in doing that work
are listed below.

## Evaluating the Portfolios

We do not promise to address all 20 of these questions in our
evaluations.

1.  Are all elements of the Portfolio submitted to meet specifications?
2.  Is the HTML from the Portfolio generally free of typographical and
    compositional errors (meaning in particular that there is sufficient
    white space between elements, that the table of contents functions
    nicely with materials found where expected and there are no
    avoidable scrolling windows of code or results.)
3.  Are all the things on the Task 1 rubric still in good shape? Have
    any lingering issues from the proposal process been addressed?
4.  Are sufficient details provided for you to understand where the data
    come from?
5.  Is a question is posed for the Linear Model that you understand and
    that relates to the models that were fit?
6.  Is a question is posed for the Logistic Model that you understand
    and that relates to the models that were fit?
7.  Do you have a clear understanding of who the subjects in the study
    are?
8.  Do you have a clear understanding of what variables are available
    and the roles they play in the modeling?
9.  Do you have a clear understanding about why the final linear
    regression model was selected?
10. Is there at least one useful table or graph in the linear regression
    modeling?
11. Is there a clear and correct description of an effect size for at
    least one predictor?
12. Did the project author(s) make good decisions about what to include
    or exclude in the presentation of the linear models?
13. Do you have a clear understanding about why the final logistic
    regression model was selected?
14. Is there at least one useful table or graph in the logistic
    regression modeling?
15. Is there a clear and correct description of an effect size for at
    least one predictor?
16. Did the project author(s) make good decisions about what to include
    or exclude in the presentation of the logistic models?
17. Does the Discussion section clearly answer the Question about Linear
    Regression?
18. Does the Discussion section clearly answer the Question about
    Logistic Regression?
19. Does the discussion section clearly address at least two of the four
    posed questions, which are:
    -   What was substantially harder or easier than you expected, and
        why?
    -   What do you wish you’d known at the start of this process that
        you know now, and why?
    -   What was the most confusing part of doing the project, and how
        did you get past it?
    -   What was the most useful thing you learned while doing the
        project, and why?
20. Is the Portfolio generally attractive and well-organized, and thus
    easy to review?

## Evaluating the Presentations / Slides

We do not promise to address all 10 of these questions in our
evaluations.

1.  Are the slides attractive and easy to follow?
2.  Are there spelling, grammatical or typographical errors in the
    slides?
3.  Did the author make good decisions about what to include and not
    include in terms of explaining the subjects, outcome and predictors?
4.  Did the author make good decisions about what to include and not
    include in terms of explaining the statistical findings?
5.  Did the author make good decisions about including tables, charts
    and graphs?
6.  Are the presented graphical elements clear, well-labeled, and do
    they stand on their own?
7.  Is the presenter speaking clearly, and loudly enough to be heard?
8.  Did the presenter peak your interest in the topic and their
    findings?
9.  Does the presentation provide at least one potential next step to
    improve the modeling or the data?
10. Did the presenter claim any findings that cannot be supported well
    by the presentation?

# Links

-   [General Project A
    Instructions](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/00_projectA_general.md)
-   Detailed [Instructions for Project A Task 1 (The
    Proposal)](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/01_projectA_proposal.md)
-   [Templates for Project
    A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/templates)
    also posted to our Shared Drive.
-   [Main Page for Project
    A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA)
