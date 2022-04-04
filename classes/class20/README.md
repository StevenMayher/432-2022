# 432 Class 20: 2022-03-29

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class20/432_2022_slides20.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class20/432_2022_slides20.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://imgs.xkcd.com/comics/spacecraft_debris_odds_ratio.png)

[Link at XKCD (with hover text)](https://xkcd.com/2599)

## Today's Agenda

Today we'll provide a brief survey demonstrating the use of R and two new ideas:

1. working with weights in regression (aggregation and survey weights)
2. CART (classification and regression trees)

## Announcements

1. There is a [Minute Paper](https://bit.ly/432-2022-min-20) after today's class, due Wednesday at noon. 
2. To use the tools we'll demonstrate today for CART analyses, you'll need to install the `party`, `rpart` and `rpart.plot` packages. I've added these three to [our R Packages](https://thomaselove.github.io/432/r_packages.html) list.
3. Make sure you upgrade your version of R to 4.1.3 and RStudio to 2022.02.0-443 or later. See the [Class 18 README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class18) for details.
4. Lab 4 grades and feedback [are now available](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab04#post-deadline-materials), and we've also shared [essays we liked responding to each of the three prompts to Question 1](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab04#post-deadline-materials).
5. As you've seen in your email, I'm giving a seminar on "[Stepped Wedge Designs in Practice: What Should We Think Hard About?](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class20/seminar_love_2022-04-01.pdf)" on Friday 2022-04-01 from 9-10 AM over Zoom. You're welcome to join for all or part of it.

## Upcoming Deliverables

See the [Calendar](https://thomaselove.github.io/432/calendar.html) for all deadlines.

- [Minute Paper after Class 20](https://bit.ly/432-2022-min-20) is due tomorrow (Wednesday) at noon.
- [Project B Outline and Scheduling Form](https://bit.ly/432-2022-projectB-register) is due Sunday at 9 PM. See [the Class 17 README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class17) and [the Project B instructions](https://github.com/THOMASELOVE/432-2022/tree/main/projectB).
- [Lab 5](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab05) is due Monday at 9 PM.

## Additional Resources on Survey Weights

The `survey` package home page: http://r-survey.r-forge.r-project.org/survey/index.html

### Tutorials...

- https://www.r-bloggers.com/2015/09/linear-models-with-weighted-observations/
- https://stackoverflow.com/questions/10268689/weighted-regression-in-r
- https://online.stat.psu.edu/stat501/lesson/r-help-13-weighted-least-squares

### On NHANES specifically...

- https://wwwn.cdc.gov/nchs/nhanes/analyticguidelines.aspx
- https://wwwn.cdc.gov/nchs/nhanes/tutorials/Module3.aspx
- https://stylizeddata.com/how-to-use-survey-weights-in-r/
- https://stats.idre.ucla.edu/r/faq/how-can-i-do-regression-estimation-with-survey-data/
- http://asdfree.com/national-health-and-nutrition-examination-survey-nhanes.html

## Additional Resources on CART

- [statmethods.net](http://www.statmethods.net/advstats/cart.html) (lots of the descriptions are here)
- [CART with rpart](https://rpubs.com/minma/cart_with_rpart) (uses the titanic data)
- [rpart vignette](https://cran.r-project.org/web/packages/rpart/vignettes/longintro.pdf)
- [party vignette](https://cran.r-project.org/web/packages/party/vignettes/party.pdf)
- [milbo.org](http://www.milbo.org/rpart-plot/prp.pdf) (tutorial on rpart.plot for tree plotting)
- [CART talk (pdf)](http://statweb.stanford.edu/~lpekelis/13_datafest_cart/13_datafest_cart_talk.pdf)
- [RandomForests](https://www.stat.berkeley.edu/~breiman/RandomForests/) is old, but still useful
- [Tune and interpret decision trees for #TidyTuesday wind turbines](https://juliasilge.com/blog/wind-turbine/) by Julia Silge (includes video)
- [Bagging with tidymodels and #TidyTuesday astronaut missions](https://juliasilge.com/blog/astronaut-missions-bagging/) also by Julia Silge (with video)

# One Last Thing

[A checklist for data graphics](https://statmodeling.stat.columbia.edu/2022/03/15/a-checklist-for-data-graphics/) from Christian Hennig, as posted by Andrew Gelman, with a few comments.

**Think about goals, and audience.**


