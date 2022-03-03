432 Project B Instructions for Spring 2022
================
Thomas E. Love
Last Updated: 2022-03-04 08:42:20

-   [1. Overview of Project B](#1-overview-of-project-b)
-   [2. Deliverables and Deadlines](#2-deliverables-and-deadlines)
-   [3. Your Project Title](#3-your-project-title)
-   [4. Your Research Questions](#4-your-research-questions)
-   [5. Your Data Set](#5-your-data-set)
    -   [Requirements and Restrictions](#requirements-and-restrictions)
    -   [Please don’t use multi-level (hierarchical)
        data](#please-dont-use-multi-level-hierarchical-data)
    -   [Good Data Sources](#good-data-sources)
    -   [Using multiple data bases](#using-multiple-data-bases)
    -   [Submitting Your Data](#submitting-your-data)
-   [6. The Outline and Scheduling Google
    Form](#6-the-outline-and-scheduling-google-form)
    -   [What information do I need about my data for this
        form?](#what-information-do-i-need-about-my-data-for-this-form)
    -   [Signing Up for Presentation
        Times](#signing-up-for-presentation-times)
    -   [How Will Dr. Love respond to the
        form?](#how-will-dr-love-respond-to-the-form)
    -   [Making Changes after Your Project B plan is
        approved](#making-changes-after-your-project-b-plan-is-approved)
-   [7. The Project B Presentation](#7-the-project-b-presentation)
    -   [Additional Details on
        Presentations](#additional-details-on-presentations)
    -   [P values and “statistical
        significance”](#p-values-and-statistical-significance)
    -   [What kinds of questions will Dr. Love ask at the
        presentation?](#what-kinds-of-questions-will-dr-love-ask-at-the-presentation)
-   [8. Project Portfolio Template](#8-project-portfolio-template)
-   [9. What Should Be in the
    Portfolio?](#9-what-should-be-in-the-portfolio)
    -   [Can Dr. Love provide an idea of what our data cleaning might
        look
        like?](#can-dr-love-provide-an-idea-of-what-our-data-cleaning-might-look-like)
    -   [What are the main section headings in the
        Portfolio?](#what-are-the-main-section-headings-in-the-portfolio)
-   [10. Modeling Restrictions (meant to be
    helpful)](#10-modeling-restrictions-meant-to-be-helpful)
    -   [Model Size](#model-size)
    -   [Transformations](#transformations)
    -   [Predictors](#predictors)
    -   [Validation](#validation)
    -   [Missing Data](#missing-data)
-   [11. Questions and Answers](#11-questions-and-answers)
-   [12. Twelve Things We Want To See in Your
    Work](#12-twelve-things-we-want-to-see-in-your-work)
-   [Need Help?](#need-help)

This document will be updated as issues arise and new questions emerge.

# 1. Overview of Project B

Here’s what you’ll do in Project B. All deadlines are on the [Course
Calendar](https://thomaselove.github.io/432/calendar.html). In Project
B, you can work individually or in a group of two people.

1.  Create two research questions that can be addressed with data you
    can conveniently obtain that can be used to address each of your
    questions, with models that you learned in the 431-432 sequence.

2.  You will fit one regression model for each research question.

    -   Each of your models must include 2-8 predictors.
    -   Each model must include at least one predictor that is not
        included in the other model.
    -   Each model will need to describe observations from the same pool
        of “subjects”, so that a single tibble services the whole
        Project.

3.  The model for your first outcome must be either:

    -   A model for a multi-categorical outcome
    -   A model for a count outcome
    -   A Cox model for a time-to-event outcome with censoring, or
    -   A linear or binary logistic model fit using a Bayesian engine

4.  The model for your second outcome must use a different approach than
    you used for Outcome 1.

    -   In addition to the options listed above, in Model 2, you can
        also consider using a weighted linear regression model, or a
        linear model fit with ordinary least squares or a binary
        logistic model, subject to these exceptions.
        -   If you fit a Bayesian linear model for outcome 1, you cannot
            use an ordinary least squares model for outcome 2.
        -   If you fit a Bayesian logistic model for outcome 1, you
            cannot use a binary logistic model for outcome 2.

5.  In late March, you will submit a Google Form, which Dr. Love will
    post after Spring Break.

    -   In this form, you will specify your title, your research
        questions, your data source and you will provide a brief
        description of each of your outcomes, and the type of models you
        plan to fit for each.
    -   You will also specify the times that work for you (and your
        partner) to give your Project B presentation to Dr. Love in late
        April.
    -   Dr. Love will need to approve your Google Form before you
        proceed further.

6.  After receiving Dr. Love’s approval, you will prepare a portfolio of
    your results with R Markdown and HTML, and give a 15-minute
    presentation (if no one asked any questions) of your work to
    Dr. Love in late April.

7.  You will then make changes (as needed) in response to Dr. Love’s
    comments during your presentation and submit the final version of
    the portfolio (Rmd and HTML and some data) to Canvas at the start of
    May.

# 2. Deliverables and Deadlines

All deadlines appear on the [Course
Calendar](https://thomaselove.github.io/432/calendar.html).

There are three Project B deliverables:

1.  A [Project B Outline and Scheduling Google
    Form](http://bit.ly/432-2022-projectB-register) to register your
    project and schedule your presentation.
    -   The form will open for responses on 2022-03-15.
    -   If you are working with a partner, exactly one of you will fill
        out the form, representing the team.
2.  Your **presentation** to Dr. Love in late April, which is
    then followed by you revising your work in light of that
    conversation to produce …
3.  Your **final version** of your portfolio and presentation materials.
    -   After your project presentation, you will submit your portfolio
        (R Markdown and HTML) and data (see below for data submission
        details) to Canvas.
    -   The Canvas link for these submissions will go live on
        2022-04-25.

# 3. Your Project Title

Your Project Title cannot include the words “Project”, “Title”, or “432”
or “Project B” or anything generic like that.

-   Your Project Title is restricted to 80 characters, including spaces.
-   Make your title as interesting as possible within the 80-character
    limit. Impress me with a good title.
-   Don’t use a lengthy sub-title to try to squeeze in lots of
    information about the project.
-   Feel free to focus on one of your two research questions (rather
    than both) if that’s what’s needed to keep to the 80-character
    limit.

# 4. Your Research Questions

Project B requires you to answer two research questions with data you
obtain. You can study any question you like, although I’d steer clear of
anything that you think Dr. Love might find inappropriate.

-   Jeff Leek in *How to be a Modern Scientist* has some excellent
    advice in his section on “How Do You Start a Paper.” In particular,
    you want to identify research questions that:
    -   are concrete, (and for which you can find useful data), and that
    -   solve a real problem, and that
    -   give you an opportunity to do something new,
    -   that you will feel ownership of, and
    -   that you want to work on.
-   We recommend you use the FINER criteria (or, if relevant, the PICOT
    criteria) to help you refine a vague notion of a research question
    into something appropriate for this project.
    -   FINER = Feasible, Interesting, Novel, Ethical and Relevant.
    -   PICOT is often used in medical studies assessing or evaluating
        patients and includes Patient (or Problem), Intervention (or
        Indicator), Comparison group, Outcomes and Time.
    -   The [Wikipedia entry on research
        questions](https://en.wikipedia.org/wiki/Research_question)
        provides some helpful links to these ideas.
-   Your research questions must be written as questions, ending with
    question marks.

Each of your research questions needs to lead clearly to a modeling
strategy, where you’ll fit an appropriate regression model.

# 5. Your Data Set

## Requirements and Restrictions

1.  You must completely identify the source of the data, so that
    Dr. Love understands what data you are using very well, but you will
    not be required to share the data with him, or anyone else, if the
    data you use are not already available to the public. You must
    ensure that you have all necessary permission(s) to use the data for
    this course project.
2.  Each of your models must work with data drawn from the same tibble,
    and describe observations from the same pool of “subjects”.
3.  We prefer that data sets contain between 150 and 1500 complete
    observations on each outcome, but you can use more than 1500 or as
    few as 100, if it’s important to do so.
4.  We don’t want you to use hierarchical data (multi-level data), if
    that can possibly be avoided, since we won’t discuss models for such
    data in enough detail to make them a good Project B choice.
5.  Your tibble will need a subject identifying code, and each model
    must have a separate outcome, and at least one predictor not used in
    the other model and each model must have 2-8 predictors, we
    anticipate that your clean, tidied tibble will include between 6 and
    19 variables.
6.  We suggest that you collapse multiple categories as necessary to
    ensure that you have at least 25 observations in every category you
    plan to use for every predictor or outcome studied in Project B.

There are only a few restrictions on your choice of data.

-   You are not allowed to use data stored as a data set in any R
    package other than NHANES or Tidy Tuesday data.
-   You are not allowed to use data Dr. Love or anyone else has provided
    to you for teaching purposes.
-   You cannot reuse the data you used in Project A for 432, although
    you can use a different data set to answer related questions. You
    are welcome to reuse data you used in your 431 project work if it is
    suitable and you haven’t used it in Project A for 432.
-   You are not allowed to use data from a textbook or other educational
    resource for learning statistics, data science or related methods
    (online or otherwise). Examples of these repositories (that are
    sadly out-of-bounds for this project) include the [Cleveland Clinic
    Statistical Education dataset
    repository](https://www.lerner.ccf.org/qhs/datasets/), the
    [Vanderbilt University Biostatistics
    Datasets](https://hbiostat.org/data/), or the [UCI Machine Learning
    Repository](https://archive.ics.uci.edu/ml/index.php).

## Please don’t use multi-level (hierarchical) data

We want to powerfully discourage you from working with data that really
require the use of multi-level models.

-   One example would be a model of patient results that contains
    measures not just for individual patients but also measures for the
    providers within which patients are grouped, and also for health
    systems in which providers are grouped.
-   Another example would be a model of individual people’s outcomes
    where the covariates are gathered at the state or county level, as
    well as at the level of individuals.
-   If your proposed research questions involve the analysis of data
    that are *nested* like those above, Dr. Love is likely to reject the
    project, as there simply isn’t time to learn the best approaches for
    that stuff in time, and we want you to demonstrate your skills
    gained during the 432 course.

## Good Data Sources

I hope that most people will find datasets of interest to them and use
those. If you do not have any strong ideas for data to use, then I
encourage you to consider the options provided in 432 Project A. The
best projects from my perspective use interesting and appropriate data
that I have never seen before.

In terms of data I am more comfortable with, I encourage those needing
guidance to use either NHANES data or County Health Rankings data. The
primary advantage here is that these data sources are familiar to both
Dr. Love and most of the teaching assistants, so we can be helpful,
they’re updated regularly, and they’re well documented.

**Note**: We have had some difficulty identifying data set suggestions
(outside of educational repositories like the [UCI Machine Learning
Repository](https://archive.ics.uci.edu/ml/index.php)) that are both
messy enough to be interesting for this project and which also provide
time-to-event outcomes with right censoring that are suitable for the
survival analysis work we discuss in 432. If you have suggestions along
these lines, Dr. Love would be eager to hear them.

## Using multiple data bases

Dr. Love will be more impressed with a data collection effort that puts
together at least two different data bases, than he will be with an
effort that uses only a single data file.

-   This may require you to learn something about the various joining
    commands, like `left_join` and `inner_join` that are highlighted in
    the Combine Data Sets section on the [Data Transformation Cheat
    Sheet](https://www.rstudio.com/resources/cheatsheets/) at the R
    Studio web site.
    -   We heartily recommend Garret Grolemund’s YouTube materials on
        Data Wrangling, for instance [this Introduction to Data
        Manipulation](https://www.youtube.com/watch?v=AuBgYDCg1Cg) which
        is about combining multiple data sets.
    -   Another great resource for combining data sets (and most of your
        other R questions) is [R for Data
        Science](http://r4ds.had.co.nz/), by Wickham and Grolemund.

## Submitting Your Data

If your data are available to the public, including Dr. Love, then
submit (along with your portfolio) in May:

-   whatever Dr. Love needs to provide to the R Markdown file to ingest
    your data (this is most commonly a .csv file or series of them, but
    you might instead pull directly from the internet, which is also
    fine.)
-   a tidied version of the data set, saved as .Rds, and matching
    precisely what you describe in your codebook.
-   if the data are available online, you must provide within your HTML
    file a working URL with instructions to access the data.

If your data are not available to the public, then submit (again, with
your portfolio after the presentation) in May:

-   an .Rds or .csv file consisting of five rows of your data, with all
    variables included in your codebook provided, and with different
    values of each of the variables displayed.
-   The five rows can be five actual rows from your data set, or each
    row can take parts of several different actual rows in your data to
    hide details and prevent re-identification.
-   No protected health information may be included in the five rows of
    data you submit, nor can any protected information be contained in
    the actual analytic data set(s) you use in your work.

# 6. The Outline and Scheduling Google Form

The [Project B Outline and Scheduling
Form](http://bit.ly/432-2022-projectB-register) is a Google Form you
will be able to access (after logging into Google via CWRU) at
<http://bit.ly/432-2022-projectB-register>.

This form allows you to register a brief description of your project for
Dr. Love’s approval, *and* specify presentation times when you (and your
partner if applicable) are available.

-   Before you complete the form, please read this entire document,
    settle on your research questions and obtain and ingest your data
    into R, although you needn’t complete all data management activities
    prior to filling out the form.

## What information do I need about my data for this form?

-   You’ll need to assert that you have already successfully ingested
    the data into R.
-   You’ll need to tell us the two types of models you plan to fit.
-   You’ll need to describe the variables you intend to use as outcomes
    in your models.
    -   These two outcomes need to be clearly linked to your research
        questions, and you’ll need to tell us something about each of
        their distributions.
-   You’ll need to specify how many cases are in your data with complete
    data on each of your study’s two outcomes.

## Signing Up for Presentation Times

Dr. Love will make a series of time slots available.

-   You will specify a certain number of these time slots as times when
    you (and your partner, if any) are available to give your project.
-   The time slots are scheduled on April 25, 26 and 28.

Some people will have special circumstances that make it difficult for
them to meet during some of these times. There will be an opportunity on
the form for you to provide those details to Dr. Love.

## How Will Dr. Love respond to the form?

On the basis of your responses to the form, Dr. Love will either approve
or reject your Project B plan, and once he approves it, you can proceed.

-   If he cannot approve your project, he’ll tell you why, and tell you
    how to try again. You’ll need to iterate until he approves your
    project, but we hope this won’t require more than two tries for
    anyone.
-   The main reason why Dr. Love doesn’t approve projects is that he
    doesn’t understand the description of your data set or its outcomes,
    your planned modeling approaches, or how the research questions link
    to the available data, so focus on making those connections as clear
    as possible.
-   TAs are available during their office hours to review your planned
    research questions, data set and planned variables with you to make
    suggestions.

Once all forms are in, Dr. Love will also schedule the presentations,
and this information will be announced in class and posted to GitHub as
quickly as possible after the registration deadline.

## Making Changes after Your Project B plan is approved

No plan survives first contact with the data unscathed. You will wind up
making changes as your work on the Project progresses. Once Dr. Love
approves your proposed research questions, you should feel to free to
make any change you like, so long as you are not materially changing the
general topic of your work. If you feel that you need to change the
title of your project, that’s the time to get Dr. Love’s approval again,
but if the original title still works, you’ll be fine.

-   If you do need to change a title, request a re-approval via email by
    submitting both the initial title and research questions as well as
    the new ones you now propose, accompanied by a brief description of
    what needs to change and why you need to make the change.
-   Dr. Love will consider changes of this sort via email he receives
    more than 72 hours prior to your scheduled project presentation.
    After that, your title is locked in.
-   You do not need permission to adjust your choice of variables, or
    your strategy for including subjects or anything else that wouldn’t
    change the main goals of your project or your title.

# 7. The Project B Presentation

After you register your project and obtain a presentation time, your
remaining job is to build a very well-designed and well-analyzed study
then present it to Dr. Love (orally and in a written HTML file)
beautifully.

Dr. Love will soon decide (and announce in class 2022-03-15) whether
presentations will be given in person or via Zoom. In either case, your
presentation is based on results contained in your portfolio, hitting on
these four key points.

1.  What your research questions were and why they are important.
2.  What data you used and why it was relevant to addressing your
    questions.
    -   You should present at least two effective visualizations of your
        data that help Dr. Love understand what can be said about your
        research questions, at least one of which should help Dr. Love
        explore your data, and at least one of which should help
        Dr. Love evaluate the success of a particular model. Build the
        presentation around the figures!
3.  What statistical methods you used to analyze and model the data and
    why they were appropriate.
    -   In particular, you are required to present at least one result
        that is derived from one of your regression models. Your
        model(s) should be clearly linked to your eventual conclusions
        about your research questions.
4.  What the results say about your research questions - what you have
    learned by doing this project?
    -   Be as clear as possible in your speaking about how you address
        each of the four main issues specified above.

Jeff Leek’s best piece of advice in my opinion is to make the
**FIGURES** the focus of your writing and your presentation.

-   Another good piece of advice is to acknowledge the work of others
    appropriately (especially in highlighting where the data come from.)
    Be gracious.

## Additional Details on Presentations

Your presentation should be focused on your demonstration of your
understanding of key ideas from the course. Do not spend more than the
minimum possible time discussing the background of your data or your
data cleaning. Focus on your research questions, your analytic work, and
your discussion of conclusions, effect sizes and limitations.

-   If we do this via zoom, each time slot will be one hour long. You
    will be placed in a group with (in most cases) two other projects
    during that hour, and will listen to their presentation(s) as well
    as your own during that hour.
-   If we do this “in person”, each presentation will happen with just
    the investigators and Dr. Love in the room, for 20 minutes.
-   You should think of this as a 15 minute presentation if no one asked
    any questions, but the time slots are 20 minutes each because
    Dr. Love will ask questions of you, during and after your
    presentation.
    -   Your ability to address those questions effectively, using the
        results from your portfolio of work, is the thing that will
        separate mediocre grades from excellent ones, in most cases.
    -   You will need to be agile in responding to me. Anticipate tough
        questions. Dr. Love will be looking for clear answers, motivated
        by your results.
    -   Rehearse your presentation so that it takes somewhere between 12
        and 15 minutes if no one asks you any questions.
-   If you work as a team, Dr. Love will pick one of you at random, on
    the spot, to deliver the first half of the presentation, and the
    other will do the second half. Dr. Love will address questions to
    each of you.
    -   Dr. Love will address questions to each of you during the
        session.
    -   Pre-plan a place where whoever Dr. Love chooses to speak first
        will switch off to the second person so that the time is about
        even, and you’ll both need to be prepared to give either half of
        the presentation.
    -   If you’re on Zoom, one of you should plan to be the one who will
        share their screen for both halves of the presentation, so we
        don’t have to switch back and forth.
-   You can give your presentation using just your knitted HTML results
    from R Markdown, or a set of slides you’ve prepared or any other
    tools that allow you to show your mastery of 432 material most
    effectively in the available time.
-   Do not plan to run R code during the session. Your HTML file, for
    example, must be completely knitted.
-   Structure your presentation so you can find things very easily.
    Useful names in the headers help, certainly, but thoughtful
    construction of an argument and good NAMES for things in your code,
    and in the headings of your presentation is really the most
    important thing.

## P values and “statistical significance”

You are welcome to include p values in your analyses in either the
portfolio or the presentation, but you should demonstrate good
statistical practice by not comparing them to *α* levels to declare
things to be important, meaningful, or significant.

**You should not use the words “statistically significant” or any
synonyms (like statistically detectable) in any of your materials or in
your presentation.**

## What kinds of questions will Dr. Love ask at the presentation?

Dr. Love will ask all kinds of things in an effort to allow you to show
your best thinking and to make sure you understand and can explain the
things you’re presenting.

At the end, if time permits, he usually tries to ask these two
questions:

1.  What percentage of your time did you spend on gathering and cleaning
    the data, as compared to working with the data once it was clean and
    tidy?
2.  What’s the most important thing you learned by doing the project,
    that you didn’t know at the start, and that you’d like to remember
    several years down the road?

# 8. Project Portfolio Template

You will build a **written portfolio** created using R Markdown of
Project B materials. Your portfolio should present your work in a way
that allows you to demonstrate to Dr. Love your mastery of several
important ideas you learned during the 432 class.

-   Your portfolio will include some background, leading into your
    research question or questions, your data management work and
    codebook, and then your analytic work, data descriptions, results
    and conclusions.
-   Your portfolio should demonstrate your commitment to replicable
    research by presenting a description of your work that allows you
    (or anyone else with access to the raw data) to review and repeat
    and (potentially) modify all of your important work by following
    your presentation.
-   Your goal in the portfolio should be to ensure that you, two years
    from now, can use your portfolio and the data to replicate your work
    and make changes in light of new information easily.

Dr. Love built a sample template for the Project Portfolio, using the
`rmdformats` package. We recommend you use it.

-   The Project B Template is built on the `readthedown` template.
    -   The Project B Template, entitled
        `projectB-template-432-2022.Rmd` is now posted to our shared
        Google Drive in the Project B materials section.
    -   You can view [the HTML result at
        RPUbs](https://rpubs.com/TELOVE/projectB-template-432-2022).
-   The `cardiac.csv` file (also found in our Shared Google Drive) is
    used in the template to help fix ideas.

Any alternate template or formatting style is acceptable if it

-   contains all of the content in Dr. Love’s template
-   and uses a **dynamic** (or at least floating) and attractive table
    of contents.
    -   A dynamic table of contents adjusts to account for the section
        of the work you’re working with, and is not merely a floating
        table of contents, but either is acceptable.

# 9. What Should Be in the Portfolio?

Make your portfolio gorgeous, thoughtful and incredibly easy for
Dr. Love to use in evaluating your work.

-   Jeff Leek’s material in *How To Be a Modern Scientist* is very
    useful here, in particular the material on Scientific Talks and on
    Paper Writing. We especially like the advice to write clearly and
    simply.
-   Include all R code and output that you need to help Dr. Love
    understand the important issues in your study.
    -   Adding **more** material, just for the sake of demonstrating
        that you can, is a good way for me to be **unimpressed** with
        your project. If you cannot think of anything to say about a
        piece of output easily, why are you including it?
-   Cleaning the data is a vitally important step. Dr. Love will assume
    that you have done it perfectly. The TAs can help you, but this is
    your responsibility.
-   Your cleaning should use tools from the tidyverse when possible, and
    you should do all analytic work on tibbles, whenever possible.
-   Don’t include warnings or messages from R that we don’t need to know
    about. Use and trust your judgment.
-   Never show long versions of output when short ones will do. A
    particularly good idea is to print a tibble rather than showing an
    entire data set.
-   Review your HTML output file carefully before submission for
    copy-editing issues (spelling, grammar and syntax.) Even with
    spell-check in RStudio (just hit F7), it’s hard to find errors with
    these issues in your Markdown file so long as it is running. You
    really need to look at the resulting HTML output, closely.

## Can Dr. Love provide an idea of what our data cleaning might look like?

You’ll find an R Markdown version on our Shared Drive in the Project B
section, called `toy-nhanes-example.Rmd` and an HTML version that is the
result of that code at <https://rpubs.com/TELOVE/toy-nhanes-432>.

This document shows how to:

-   pull data from NHANES for both the 2015-16 and 2017-18 cycles
-   clean up what you’ve pulled in, merging multiple databases from each
    cycle with `inner_join()`
-   merge the 2015-16 and 2017-18 data together with `full_join()`
-   check and clean the variables
-   save a tidy tibble
-   build a codebook
-   split the data into testing and training samples

I hope you’ll find it useful even if you’re not cleaning NHANES data. I
know you’ll find it useful if you are cleaning NHANES data.

## What are the main section headings in the Portfolio?

We suggest that you begin with an unnumbered section for R
Preliminaries. The numbered sections (as exemplified in the Template
below) are:

1.  Background
2.  Research Questions
3.  My Data
4.  Tidy Data Code Book and Description
5.  Analyses
6.  Conclusions
7.  References and Acknowledgments
8.  Session Information

# 10. Modeling Restrictions (meant to be helpful)

The purpose of providing these restrictions is to reduce your stress and
reduce the scope of the project a bit. Take these as useful suggestions
that will help you avoid some common problems. Most students attempt to
take on too much in doing the project. These restrictions are meant to
stop you from doing that.

If you decide that one or more of the restrictions in this section
shouldn’t apply in your project, you have our permission to do something
else, as long as you **identify the issue, and describe and defend your
decision** in **both** your portfolio and presentation.

## Model Size

1.  While you can fit a larger model, we strongly recommend you restrain
    yourself to **no more than 8 predictors** in a final model
    regardless of your sample size. Anything more than that will be
    difficult to interpret at best.
2.  If your number of main effects (predictors) that you want to include
    in your final model exceeds the number of degrees of freedom
    specified below, then don’t add any non-linear terms. If you do
    decide to include non-linear terms as determined based on a Spearman
    rho-squared plot, then adhere closely to the maximum degrees of
    freedom specified in the table below. These df limits include the
    intercept term(s).

-   If you are fitting a regression to a **quantitative or count**
    outcome, let *n* = sample size. For this count and all of the counts
    here, do not include any data points where the outcome is missing.
-   If you are fitting a regression to a **categorical** outcome, let
    *n* = # of observations in the category with the smallest sample
    size.
-   If you are fitting a regression to a **time-to-event** outcome, let
    *n* = # of observations where the event occurred (was not censored).

| Value of *n* | 20-100 | 101-250 | 251-500 | 501-999 | 1000+ |
|-------------:|-------:|--------:|--------:|--------:|------:|
| Maximum *df* |      6 |       9 |      12 |      16 |    20 |

For Project B, don’t worry about penalizing yourself for “peeking” at
the data by running automated selection procedures (although we don’t
generally recommend these) or scatterplot matrices.

## Transformations

In Project B, restrict yourself to understandable outcome
transformations, and don’t be a slave to the Box-Cox approach, which
after all is only designed to help with some very particular issues.

The reasonable transformations to consider are 1/*y*, a logarithm of
*y*, the square root of *y*, or *y*<sup>2</sup>.

-   Anything more complicated than that should suggest that you consider
    a different modeling approach or revision to your outcome.
-   There is no point in demonstrating all possible transformations in
    your final work. Describe the transformation you make and your
    reason for it, then move on.
-   If you use a transformation of an outcome, please feel encouraged to
    back-transform out of that in presenting final prediction results
    where convenient, perhaps in a nomogram or a demonstration of what
    the model predicts for a pair of fictional subjects like “Harry and
    Sally.”

## Predictors

1.  Collapse multi-categorical predictors sufficiently that you don’t
    have problems fitting or interpreting the model. In most cases, it
    is very difficult to describe what’s happening with predictors
    containing more than five levels.
2.  If you choose to use a spline or polynomial function with a
    quantitative predictor and want also to use an interaction term for
    that predictor, be sure to restrict the interaction to a linear term
    only with `%ia%`.
3.  Make sure that the coefficients and standard errors in your models
    don’t explode, which can happen when a predictor overwhelms the
    regression model. It’s your job to identify that there is a problem
    and do something to address it appropriately, rather than presenting
    a clearly inappropriate model.

## Validation

1.  We expect a validation, properly executed, to be an important part
    of every project.
2.  This will most commonly include a split into training and testing
    samples, and an evaluation of key results in a held-out sample.
3.  Bootstrap validation of summary statistics via the tools available
    in the `rms` package is also welcome, if you are fitting models
    using those tools.

## Missing Data

1.  Drop all cases without complete outcome data, but otherwise, your
    goal should be to preserve as much of the data collection effort as
    possible.
2.  Use multiple imputation to deal with missing values in presenting a
    final model for either a linear or logistic regression. Be sure to
    explicitly state the assumptions you make about the missing data
    mechanism.
3.  You may use single imputation in the process of developing your
    models, in presenting residual plots for linear models, or in
    presenting final models for regression approaches for count,
    multi-categorical or time-to-event with censoring outcomes.
4.  Do not use a complete-case analysis or sampling strategy except to
    ensure that all of your cases have complete outcome data.

# 11. Questions and Answers

> Does Project B have to include everything that we did in Project A?

No. You’ll want to have some of that information at your fingertips in a
presentation, so think carefully about what to keep and what to drop.
Clearly, there is meaningful overlap (you need to describe your research
questions, your data, provide a codebook, etc.)

> Should I specify, prior to analyses, my guess as to the expected
> direction of relationships between outcomes and predictors?

Sure, especially for any key predictors.

> Am I allowed to use `echo=FALSE` in Project B?

The use of `echo = FALSE` is prohibited in Project B, except in the very
first code chunk where you set options, as in the template. If your
output is in a form that allows it, please use code-folding, so that we
can show or hide code as the reader desires. Default to showing the
code, please. The template also includes code downloading turned on, and
we prefer that, as well.

> Should I add a session information command at the end of my
> presentation?

Yes, definitely. You can use `xfun::session_info()` or
`sessioninfo::session_info()` or even just `sessionInfo()` from base R.

> What should I name my models, and variables?

Something memorable and consistent. If you want to avoid creativity,
then call things `model_01` and `model_02`, by all means, but do that in
both the text descriptions and in your code. Don’t call the same thing
Model 1 (or my first model) in your text, but `mod_1` in your code, as
an example.

> Is it critical to actually answer my research questions in the
> conclusions section?

Yes. Good research questions for this Project can be addressed, for
example, with an effect size estimate, or a summary of how effectively
an outcome can be modeled. Not all data sets lead to conclusive answers
to research questions, and that’s OK, but you must tell us what you’ve
learned.

> Should I include sanity checks in my portfolio?

Sanity checks are an important part of your programming, but they don’t
belong in your final portfolio or presentation. Neither do false starts,
and explorations that don’t lead anywhere.

> How should I describe a restricted cubic spline that I’ve fit in a
> model? Do I write out that equation with the variablename’ and
> variablename’’ in it, or … ?

Tell me how many knots were involved and show me a graph that depicts
the impact of the spline. No one explains splines without a graph. Make
a graph and use it is excellent advice for many aspects of your
presentation. Sensible graphs to accomplish this task in a multivariate
regression model include the `ggplot` with `Predict` combination, the
`plot(summary())` approach, and/or a nomogram.

> If I have two models that aren’t very far apart in terms of
> validation, where Model 1 is much simpler but less good in terms of
> validation than Model 2, which model would you focus on?

If the validation results are at all comparable, then I’d definitely
focus on the simpler model.

> If I have a C statistic, do I need to also plot the ROC curve?

We can’t usually think of a compelling reason to do so. This is one of
the few places where the plot isn’t much additional help.

> Do I need to use `equatiomatic` to show the equations I’ve fit?

If you find that to be a useful thing, go ahead.

> Do my project data have to be health-related?

No. I love projects and research questions about any subject.

> Is there an advantage to choosing a public (open, sharable) data set
> over a private one for this Project?

You are permitted to do either. A substantial advantage of public data
is that you can share the details with us (including the data) if you
encounter a coding problem. This improves the chances that we can be
helpful.

> Should I consider using a data set with substantially more than 2,500
> observations for Project B?

I wouldn’t, no. If you want to work with a huge data set, then I
encourage you to sample it down to at most 1,500 observations in a model
development sample first (and perhaps as many as another 1,500
observations in a model testing sample.) There are three main reasons
for this:

1.  this is a project about what you learned in (431 and) 432, which is
    most definitely NOT a course in analyzing data with tens of
    thousands of observations,  
2.  avoid long waits while your data are processed in R, and 2000 is a
    good limit from this perspective.
3.  be sure that things like a scatterplot are still of some value in
    terms of letting you understand your data. Scatterplots of more than
    about 1000 observations tend to be very difficult to interpret, even
    if they are quite large.

Some of you want to work with data sets with more than 1,500 observations and
that’s certainly fine, but if you propose a project where your analyses
will involve more than 2,000 observations in total, I will be very
likely to require you to take a sample from your current proposed data
to proceed. It’s just not worth boiling the ocean in this project. Of
course, after the course is over, you can always ramp back up to a
bigger version of the data set to expand the project.

> What is the best way to select an appropriate set of predictors?

It depends in part on the kind of question you are trying to answer. For
most projects, I recommend a question that is explicitly about
prediction, rather than either (a) trying to explain a phenomenon in
existing data without reference to external prediction or (b) trying to
make some sort of causal inference, which requires methods beyond the
scope of this class.

What I would always try to do is start with a question I want to answer,
which should motivate specific predictors. A combination of logic,
theory and prior empirical evidence is always preferable. A scan of the
literature is always useful. A conceptual model of the relationship
which makes predictions about what “should” happen under current
understanding can be very helpful. I strongly urge you to pick a project
where you have some prior understanding of how the data will behave and
where you can express that pre-modeling belief as part of your
presentation of your work.

What I would definitely not do is scan a list of correlations in the
current data to see which ones look promising, and then forget that I
did that when it came time to evaluate the models I developed. It’s fine
to go on a fishing expedition in Project B, but then you have to
severely temper your claims, and in particular you have to give up on
drawing any substantial conclusions about causation or explanation and
focus instead on a question about prediction, and (of course) validation
of your model becomes essential.

> Does Dr. Love have a strong working understanding of genomics data?

No.

> In mentioning that combining data sets would be preferable or more
> impressive in Project B, what are you referring to, exactly?

What I had in mind were the following scenarios:

1.  Multiple data sets describing different variables for the same
    subjects that can be linked, so that you can build a combined data
    set with the same subjects but pulling together multiple sources of
    data, as, for example, the County Health Rankings do each year.

2.  Multiple data sets describing different subjects but the same
    variables, such as different years of a survey, combining, for
    instance, multiple iterations of NHANES so as to increase the
    available sample size.

If your project research questions and available data lead to one of
these approaches, great. If not, don’t force it.

**Thanks**

Thanks to those of you who’ve read all the way down to the bottom of
these instructions. If you send an email to Dr. Love before the Project
B Schedule and Outline Form is due, telling him the name of your
favorite R function (please use the subject: *Favorite R function*), he
will be grateful, and will give you some bonus class participation
credit.

# 12. Twelve Things We Want To See in Your Work

1.  a clear statement of each of your research questions, preceded by an
    appropriate (but not at all lengthy) background section motivating
    those questions
2.  a clear description of the data to be used, with careful attention
    to cleaning the data to make the follow-up analyses as
    straightforward as possible
3.  the use of techniques from the 431-432 sequence for every stage of
    the data science process, from data ingest and tidying through the
    cycle of transformation, visualization and modeling, and then
    finally a careful communication of the end result
4.  the use of regression methods that are directly applicable to the
    research questions you pose
5.  the use of appropriate tools for diagnosing the quality of those
    models, including useful and well-presented visualizations and
    summary statistics
6.  identification and comparison of candidate models to address your
    research questions if there are real choices to be made (if you have
    a clear model in mind at the start, there’s no need to artificially
    create a competitor)
7.  validation of your model’s predictions and/or model summary
    statistics in an appropriate way
8.  clear evidence that you have thought hard, and well, about what
    output to present. In particular, we want you to think in terms of
    creating meaningful annotations for every single scrap of output
    that you generate and present: if you cannot think of anything to
    say about a piece of output easily, why are you including it?
9.  a clear re-statement of the research questions you asked at the
    start, now with conclusions that answer those questions
10. a clear statement of the limitations of your approach, and
11. a clear statement about useful next steps that you would like to try
    on the data, moving forward, as well as
12. a clear statement about what you learned as a result of doing the
    project.

All of this should appear in an extremely well-organized presentation
and portfolio that work together well. Evidence of strong organization
includes the use of effective labels, useful annotations for your code,
and (in particular) meaningful headings and a helpful table of contents
which make good use of the available technology.

# Need Help?

Questions about Project B may be directed to the TAs and to Dr. Love at
any time **after** class on 2022-03-15. If you’re asking a question on
Piazza, please use the `projectb` label, and feel encouraged to ask your
questions in public rather than privately, so as to get help from other
students, and provide help to them.
