# 432 Class 21: 2022-03-31

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class21/432_2022_slides21.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class21/432_2022_slides21.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## From [Richard Riley](https://twitter.com/richard_d_riley/status/1500759467402612738)

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class21/figures/reviewer.png)

## Two Quick Questions Before We Start

1.  If you had to guess, what percentage of American adults live in New York City?
2.  If you had to guess, what percentage of American adults

## Today's Agenda

Today we'll introduce two ideas, meant to help us think about variable selection in a linear model:

1. ridge regression
2. the LASSO (Least Absolute Shrinkage and Selection Operator) model

My code for doing this work is largely out-of-date. It still works, but most people now use the `glmnet` package for this sort of work, and I will switch over next year. The references below all use something like `glmnet` to do the work.

## A Few References For Ridge Regression and the LASSO

From the [Wikipedia page on the LASSO](https://en.wikipedia.org/wiki/Lasso_(statistics))

> Just as ridge regression can be interpreted as linear regression for which the coefficients have been assigned normal prior distributions, lasso can be interpreted as linear regression for which the coefficients have Laplace prior distributions. The Laplace distribution is sharply peaked at zero (its first derivative is discontinuous at zero) and it concentrates its probability mass closer to zero than does the Normal. This (explains) why lasso tends to set some coefficients to zero, while ridge regression does not.

> [Elastic net regularization](https://en.wikipedia.org/wiki/Elastic_net_regularization) adds an additional ridge regression-like penalty that improves performance when the number of predictors is larger than the sample size, allows the method to select strongly correlated variables together, and improves overall prediction accuracy.

- [Machine Learning for Biostatistics](https://bookdown.org/tpinto_home/Regularisation/) text from the Biostatistics Collaboration of Australia
    - includes chapters on Best Subset Selection, Stepwise Methods, Ridge Regression and the Lasso
- YouTube Video from Julia Silge
    - [LASSO regression using tidymodels and #TidyTuesday data for The Office](https://juliasilge.com/blog/lasso-the-office/)
- YouTube Videos from StatQuest
    - [Regularization Part 1: Ridge Regression](https://www.youtube.com/watch?v=Q81RR3yKn30)
    - [Regularization Part 2: Lasso (L1) Regression](https://www.youtube.com/watch?v=NGf0voTMlcs)
    - [Regularization Part 3: Elastic Net Regression](https://www.youtube.com/watch?v=1dKRdX9bfIo)
    - [Ridge, Lasso and Elastic-Net Regression in R](https://www.youtube.com/watch?v=ctmNq7FgbvI)
- [Linear, Lasso, and Ridge Regression with R](https://www.pluralsight.com/guides/linear-lasso-and-ridge-regression-with-r) using `glmnet` for some of the work, also includes Elastic Net Regression
- [A lab from Smith College on Ridge Regression and the Lasso (with downloadable Rmd)](http://www.science.smith.edu/~jcrouser/SDS293/labs/lab10-r.html)
- [Simple Guide To Ridge Regression In R](https://www.r-bloggers.com/2020/05/simple-guide-to-ridge-regression-in-r/)
- [Lasso Regression Model with R code](https://www.r-bloggers.com/2021/05/lasso-regression-model-with-r-code/)

## Announcements

1. On this, the last day of Woman's History Month, I thought I would share some of the American Statistical Association's stories celebrating [Women in Statistics](https://magazine.amstat.org/blog/2022/03/01/whm_2022/)
2. [The `cols4all` package](https://github.com/mtennekes/cols4all) is a new R package for selecting color palettes. "Color for all" refers to our mission that colors should be usable for not just people with normal color vision, but also for people with color vision deficiency. Color palettes are well organized and made consistent with each other. While not yet available on CRAN, the package can be downloaded and used, by [following these instructions](https://github.com/mtennekes/cols4all#installation).
3. Feedback on the Minute Papers after Class 20 **will be available by class time**.
4. Make sure you upgrade your version of R to 4.1.3 and RStudio to 2022.02.0-443 or later. See the [Class 18 README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class18) for details.
5. My seminar on "[Stepped Wedge Designs in Practice: What Should We Think Hard About?](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class20/seminar_love_2022-04-01.pdf)" is Friday 2022-04-01 from 9-10 AM over Zoom. You're welcome to join for all or part of it.

## Upcoming Deliverables (besides Minute Papers) - see [Course Calendar](https://thomaselove.github.io/432/calendar.html) for all deadlines.

1. **Two** things due this weekend:
    - Sunday 2022-04-03 at 9 PM: [Project B Outline and Scheduling Form](https://bit.ly/432-2022-projectB-register)
    - Monday 2022-04-04 at 9 PM: [Lab 5](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab05)
2. Monday 2022-04-11 at 9 PM: [Lab 6](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab06)
3. You will need to have finished *The Signal and the Noise* by the time you take Quiz 2, which will appear on 2022-04-14, and is due 2022-04-18 at 9 PM.
4. The deadline for [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX) (optional) is 2022-04-20 at Noon. 
    - [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) and [Lab Z](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labZ) are also optional and due with all Project B materials at noon on 2022-05-02.

## One Last Thing

[From millionaires to Muslims, small subgroups of the population seem much larger to many Americans](https://today.yougov.com/topics/politics/articles-reports/2022/03/15/americans-misestimate-small-subgroups-population)

Americans overestimate the size of minority groups and underestimate the size of most majority groups: "If you had to guess, what percentage of American adults..."

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class21/figures/subgroups.png)
