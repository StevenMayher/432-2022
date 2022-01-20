432 Project A: General Instructions and Data
================

-   [1 Introduction](#introduction)
-   [2 Project A involves two tasks](#project-a-involves-two-tasks)
-   [3 Submission Information and
    Deadlines](#submission-information-and-deadlines)
-   [4 Can I work with a partner?](#can-i-work-with-a-partner)
-   [5 Getting Help](#getting-help)
-   [6 Good Data Sets to Use](#good-data-sets-to-use)
-   [7 What Makes an Acceptable Data
    Set?](#what-makes-an-acceptable-data-set)
-   [8 Running a Data Set Past Us for Project
    A](#running-a-data-set-past-us-for-project-a)
-   [Links](#links)

Last Update: 2022-01-19 23:28:44

# 1 Introduction

It is hard to learn statistics (or anything else) passively; concurrent
theory and application are essential. Expert clinical researchers and
statisticians repeatedly emphasize how important it is that people be
able to write well, present clearly, work to solve problems, and show
initiative. This project assignment is designed to help you develop your
abilities and have a memorable experience.

In Project A, you will be analyzing, presenting and discussing a pair of
regression models, specifically a linear regression and a logistic
regression, describing a data set you identify.

# 2 Project A involves two tasks

In Task 1, you will develop a **project proposal**, due at the end of
January.

-   This part of the project involves selecting data, ingesting it into
    R and cleaning it, then describing the data.
-   We have [provided two templates](#links) for this work, either of
    which you should use to facilitate your interactions with R
    Markdown.

In Task 2 (which you’ll do in February), you will **develop analyses and
present your results**, and this is due in early March.

-   The work you’ll do here will involve analyzing the data, fitting and
    displaying models, and putting together your materials
-   Task 2 builds on Task 1 considerably, and an expanded version of the
    same [templates](#links) will be used here.

[Detailed Instructions for each Task](#links) are linked at the bottom
of this page.

# 3 Submission Information and Deadlines

All Project A work is to be submitted [via
Canvas](https://canvas.case.edu/). Details on what you need to submit
are specified in the [detailed instructions for each Task](#links).
Deadlines are found on the [Course
Calendar](https://thomaselove.github.io/432/calendar.html).

# 4 Can I work with a partner?

You can choose either to work alone, or with one other person, to
complete Project A. If you work in a group for Project A, you may be
asked to work alone for Project B later in the term.

-   You will need to identify your Project A partner as part of your
    proposal submission.
-   If you are working with a partner, all work must be submitted by
    exactly one of you to [Canvas](https::/canvas.case.edu) while the
    non-reporting partner submits a one-page note to Canvas indicating
    the members of the partnership and that the partner will submit the
    work.

# 5 Getting Help

If you have a question about Project A, please feel free to ask it:

1.  [via Piazza](https://piazza.com/case/spring2022/pqhs432) using the
    **project1** label.
2.  at TA office hours
3.  directly of Professor Love before or after class (or, if necessary,
    via email, although we prefer Piazza)

# 6 Good Data Sets to Use

Some sources of data we’d like to see people use include:

1.  [CDC WONDER](https://wonder.cdc.gov/) data, which could (at the
    county level) be combined with data from [County Health Rankings
    2021](https://www.countyhealthrankings.org/) to do something very
    interesting.
2.  The data sets described in the American Statistical Associations
    [Data Challenge Expo](https://community.amstat.org/dataexpo/home)
    for 2022, which include five very interesting data sets selected
    from the Urban Institute Data Catalog
3.  A data set from the [Tidy Tuesday
    archive](https://github.com/rfordatascience/tidytuesday) or from the
    [Data is Plural archive](https://dataset-finder.netlify.app/) might
    be a good candidate.
4.  The [Health and Retirement
    Study](https://hrsdata.isr.umich.edu/data-products/public-survey-data?_ga=2.79574685.849210420.1612760982-241136149.1612760982)
5.  The [General Social Survey](https://gssdataexplorer.norc.org/)
6.  The many many public use data sets available at
    [ICSPR](https://www.icpsr.umich.edu/icpsrweb/ICPSR/)
7.  The [500 Cities and PLACES data
    portal](https://chronicdata.cdc.gov/browse?category=500+Cities+%26+Places&sortBy=newest&utf8),
    most probably I would focus on the [County-level
    data](https://chronicdata.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-County-Data-20/swc5-untb).
8.  [National Center on Health
    Statistics](https://www.cdc.gov/nchs/data_access/ftp_data.htm)
    including NHANES
9.  [Behavioral Risk Factor Surveillance
    System](https://www.cdc.gov/brfss/data_documentation/index.htm)
10. [Kaggle Public Datasets](https://www.kaggle.com/datasets) are
    allowed but **only** those with really useful variables, no
    hierarchical structure and strong descriptions of how the data were
    gathered (which is at best 5% of what’s available on Kaggle). Don’t
    select a Kaggle data set without running it by us on Piazza to see
    if we’re willing to let you use it.

-   While data on COVID-19 would be permitted for 432 projects, most of
    the available data is longitudinal and thus unsuitable for
    Project A.
-   I encourage those of you who used NHANES data last Fall in 431 to
    use something else (just so that you can get familiar with some new
    data), but those of you who really want to may benefit from some
    [advice from the 431 class about using NHANES
    data](https://thomaselove.github.io/431-2021-projectB/data2.html) in
    a different project. Note that your rules are different, but most of
    the advice still holds well.
-   Don’t type “regression data sets” into Google. That will lead you to
    data sets we’ve seen before, and don’t want to see again. The data
    sets posted by the Cleveland Clinic for educational purposes are
    also a poor choice, since we’ve seen them before, many times.

# 7 What Makes an Acceptable Data Set?

1.  **Shareable with the World**. The data must be available to you, and
    shared with me and everyone else in the world (without any
    identifying information) as a well-tidied .csv file on 2022-01-31.
    If the data is from another source, the source (web or other) must
    be completely identified to me. Ongoing projects that require
    anyone’s approval to share data are not appropriate for Project A.
    -   You should have the data in R by 2022-01-26, so that you will
        have sufficient time to complete the other elements of this
        proposal. Any data you cannot have by that time is a bad choice.
    -   For Project A, you may not use any data set used in the 431 or
        432 teaching materials. You may not use any data set included in
        [an R package that we are
        installing](https://thomaselove.github.io/432/r_packages.html)
        this semester, other than NHANES.
    -   You must use meaningfully different data sets in 432 Projects A
        and B.
    -   You **are** allowed to use NHANES data in Project A, but only if
        you are combining information from at least three NHANES data
        sets. If you used NHANES data in your 431 project, you can use
        NHANES data again in Project A for 432, but you must study new
        outcomes, and we encourage you to try something else.
    -   You are permitted to use BRFSS data, but you are not permitted
        to use data from SMART BRFSS, since we will be using that
        regularly in class.
    -   In submitting your proposal, you will need to be able to write
        “I am certain that it is completely appropriate for these data
        to be shared with anyone, without any conditions. There are no
        concerns about privacy or security.” So be sure that’s true
        before you pick a data set.
2.  **Size**.
    -   A **minimum** of 100 complete observations are required on each
        variable. It is fine if there are some missing values, as well,
        so long as there are at least 100 rows with complete
        observations on all variables you intend to use in each model.
    -   The **maximum** data set size is 1200 observations, so if you
        have something larger than that, you’ll need to select a random
        subset of the available information as part of your data tidying
        process.
3.  **Outcomes**. The columns must include at least one quantitative
    outcome and one binary categorical outcome.
    -   We prefer distinct outcomes, but if necessary, the binary
        outcome can be generated from the quantitative outcome (as an
        example, your quantitative outcome could be resting heart rate
        in beats per minute, and your binary outcome could be whether
        the resting heart rate is below 70 beats per minute.)
4.  **Inputs**. You will need at least four regression inputs
    (predictors) for each of your two models.
    -   At least one of the four must be quantitative (a variable is
        **not** quantitative for this purpose unless it has at least 10
        different, ordered, observed values), *and* at least one must be
        multi-categorical (with between 3 and 6 categories, each
        containing a minimum of 30 subjects) for each model.
    -   Your other inputs can represent binary, multi-categorical or
        quantitative data.
    -   You can examine different candidate predictors for each outcome,
        or use the same ones in both your linear and logistic regression
        models.
    -   Depending on your sample size, you can study more regression
        inputs. Specifically, if you have N complete observations in
        your data set, you are permitted to study up to 4 + (N-100)/100
        candidate regression inputs, rounding down.
5.  **No hierarchical data**. In Project A, we ask that you restrict
    yourself to cross-sectional data, where rows indicate subjects and
    columns indicate variables gathered to describe those subjects at a
    particular moment in time or space. Do not use “nested” or
    “longitudinal” data in this project.
    -   The singular exception to this rule is that it will usually be
        acceptable to use very limited longitudinal data, specifically,
        for all inputs to be collected at a single (baseline) time point
        and both outcomes to be collected at a single future point in
        time. For example, you could predict systolic blood pressure in
        2021 (or whether or not a subject’s systolic blood pressure in
        2021 was below 140), based on a set of input variables (likely
        including systolic blood pressure) all gathered in 2020.

# 8 Running a Data Set Past Us for Project A

To get Dr. Love and the TAs to “sign off” on a data set as appropriate
for your project A proposal, you need to tell us five things in a
(private or public - your choice) note on Piazza in the project1 folder.
Please do this if you’re not sure your data set is appropriate.

1.  the data source, as described [here in item 1 in the proposal
    instructions](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/01_projectA_proposal.md#1-data-source)
    along with a URL so we can access the data
2.  a description of who the subjects are and how they were selected, as
    described [here in item 2 in the proposal
    instructions](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/01_projectA_proposal.md#2-the-subjects) -
    it helps if you also tell us how many subjects are in the data
3.  what quantitative outcome you plan to use in your linear regression
    model, including its units of measurement and the minimum, mean and
    maximum values available in your data
4.  what binary outcome you plan to use in your logistic regression
    model, specifying both of the mutually exclusive and collectively
    exhaustive categories and how many subjects fall into each of those
    two categories.
5.  that you’ve carefully read the [what makes an acceptable data set
    section of the project 1
    instructions](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/00_projectA_general.md#3-what-makes-an-acceptable-data-set)
    and can confirm that your data meets all of those specifications.

Also, we ask that you not ask us to pick between two “options” - submit
the one you’d rather do. If it’s a problem, we’ll let you know, and you
can then change to another option if necessary.

# Links

-   Detailed [Instructions for Project A Task 1 (The
    Proposal)](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/01_projectA_proposal.md)
-   [Draft Rubric for the
    Proposal](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/rubric_proposal_draft.md)
-   [Templates for Project
    A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/templates)
-   Detailed [Instructions for Project A Task 2 (Analyses and
    Presentation)](https://github.com/THOMASELOVE/432-2022/tree/main/projectA/02_projectA_analyses.md)
-   [Main Page for Project
    A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA)
