# 432 Class 14: 2022-03-01

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class14/432_2022_slides14.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class14/432_2022_slides14.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## 432-Specific Announcements

1. There is a [Minute Paper after today's class](https://bit.ly/432-2022-min-14). Please complete it by noon tomorrow (2022-03-02).
2. The Quiz 1 answer sketch is now on our Shared Drive in the Quiz 1 folder, and has been revised to add materials for Questions 2 and 21. You should have an email from me (sent 2022-02-23) containing your grade. See the last page of the Answer Sketch for class-wide results. I will close the Quiz 1 grades on 2022-03-04 at 9 PM. If you have questions about your grade, please email me before then to ask them.
3. The [Course Calendar](https://thomaselove.github.io/432/calendar.html) now shows March at the top. January and February are now found at the bottom of the document.
4. Project B instructions are coming this week. **Details to come.**

# Some Project A Tips

## Why I use `read_csv()` all the time, and never use `read.csv()` anymore

1. `read_csv()` is much faster than `read.csv()`, 
2. `read_csv()` provides a progress meter and a compact method for specifying column types,
3. `read_csv()` will read compressed files automatically,
4. `read_csv()` automatically creates a tibble, and
5. `read_csv()` allows me to speed the process of debugging by providing much more useful error messages about which rows are problematic, especially when the error is non-fatal.

- For more details, see the [Data import section of R for Data Science](https://r4ds.had.co.nz/data-import.html).
- From Josh Gonzales at Medium: [read_csv(): The Best Way to import CSV data into R](https://medium.com/r-tutorials/r-functions-daily-read-csv-3c418c25cba4)

## What should I do if I have a problem with Normality in my linear model (Project A)?

1. Not all problems can be fixed with power transformations and non-linear terms.
2. You should describe what the residual plots show, accurately.
3. If there is a problem with the residual plots, use that fact in making a decision about which model to select as your final model. 
4. If you have to select a final model with residual plot problems, describe how those problems might affect your conclusions.

## Exploding Coefficients and Problems in Logistic Regression

Sometimes, we see people fitting models to predict a binary outcome using a predictor which completely determines that outcome (for example, if predictor > 12, then outcome is always no, or if predictor = "Yes" then outcome is always no.)

Take a look at [this toy example with explosive coefficients](https://rpubs.com/TELOVE/explosion_logistic_432) to see one way in which this problem can emerge and what to do about it.

## Some Common Problems You Can Fix in your Project A

1. Sometimes, we see people failing to drop levels of a categorical predictor after combining levels. Use the `droplevels()` command.
2. Sometimes, we see people fitting restricted cubic splines or polynomials either to categorical predictors or to quantitative predictors with just a few observed values.
3. Remember that it's perfectly fine to add fewer than 3 additional degrees of freedom beyond the main effects model [if necessary, so long as you include at least one non-linear term](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/02_projectA_analyses.md#on-the-size-of-the-regression-models-you-build).
4. Suppose you decide to create a decision rule for a logistic regression model. If 10% of your observations are "Yes" on your binary outcome, and 90% are "No", then use a .fitted value of something like 0.1 as your decision rule. Don't use 50% unless your observations are split pretty close to 50-50 between your two categories for your binary outcome.
5. When you build a plot of the ROC curve for your final model, be sure it provides the same C statistic value as you get from the `lrm` fit to the data, and that you also provide the validation-adjusted C statistic estimate for that model.
6. Something we've seen **a lot** in looking at R Markdown files people have sent is the failure to include a blank line **before and after** every **heading and subheading**, and **every block of code**.
7. Please make sure you have a real title for the work, that is no more than 80 characters long.
8. Don't name the file `projectAproposal.Rmd` when it's not your proposal. A good generic name would be `2022_03_04_432_projA.Rmd` or `432projectA_2022-03-04.Rmd` assuming it's the version from that date (2022-03-04).
9. Be sure to run the spell-check, and ideally, have someone else read through your work.
10. We hate scrolling windows in HTML output caused by code that runs too long on one line. Use the ENTER key liberally to help avoid this problem, and check your HTML to see if it is happening.
11. Make sure your headings are in an appropriate order, and that you have 13 main sections in your Project, as laid out in the sample project. Check your HTML to make sure the headings make sense, for instance, `10`, then `10.1`, then `10.1.1.` is OK, but `10`, then `10.0.1` isn't OK.
12. If you're loading a package not on our [R packages list](https://thomaselove.github.io/432/r_packages.html), then you should definitely indicate why you're doing this at the top of your work as you load it in a short comment. Also, don't load elements of [the core `tidyverse`](https://www.tidyverse.org/packages/) separately: load them with `tidyverse` only.

## More General Announcements

1. Today, 2022-03-01 at 4 PM, Dr. Nancy Geller, Director of the Office of Biostatistics Research at the Heart and Lung Institute of the National Institutes of Health and past-President of the American Statistical Association, is speaking to CWRU students (especially in our MS program) about [What am I going to be when I grow up? Evolving as a statistician (zoom link)](https://cwru.zoom.us/j/98644220705?pwd%3DSGZkUFo0K2JMakFqOVpkUkdnYkZvZz09&sa=D&source=calendar&ust=1646496376642569&usg=AOvVaw2uDNWauFKQ_DW8KCpZLYNl). Please attend if you can (this is mandatory for our MS students.).
2. David Robinson did a Tidy Tuesday live screencast on YouTube [analyzing the World Freedom Index in R](https://www.youtube.com/watch?v=VOzUHk3aaBw). I hope you find it useful and interesting.
3. The [Cleveland R Users Group](https://www.meetup.com/Cleveland-UseR-Group/) is holding a Project Showcase on 2022-03-23 at 6 PM. If you're interested in attending or presenting, [here is the information](https://www.meetup.com/Cleveland-UseR-Group/events/284281072/).
4. DPhi is holding a [5-week data science bootcamp in Python](https://dphi.tech/bootcamps/5-week-data-science-bootcamp) starting 2022-03-11 which seems to be free. I can't tell you anything about it, except that a couple of past students took a prior version and told me they liked it. There's material here on feature selection and building machine learning models.
5. If you're interested in working on a COVID-19 project for Project B, you might consider [these repositories from BroadStreet Health](https://github.com/orgs/BroadStreet-Health/repositories).
6. The American Statistical Association's 2022 Women in Statistics and Data Science conference will be [held in St. Louis, MO on October 6-8](https://ww2.amstat.org/meetings/wsds/2022/conferenceinfo.cfm) and session submission starts today. 
    - If you're interested in a [student membership in ASA, go here](https://www.amstat.org/membership/become-a-member). It's $25 per year for full-time students.

## Today's Agenda

Today, we'll be presenting some key ideas on fitting models for count outcomes. Counts are discrete (rather than continuous) and counts are typically integers (0, 1, 2, 3 and so on) and cannot be made more precise. Relevant materials (some a little out of date now, I fear) are available in Chapter 19 of the [Course Notes](https://thomaselove.github.io/432-notes/).

Methods we will touch on today include Poisson regression and negative binomial regression, along with augmentations of these two approaches to inflate the number of zeros predicted, and (optionally) also "hurdle" versions which specify one process for zero counts and another for positive counts. In Chapter 19, we discuss all of these, as well as another approach, called a tobit (or censored) regression model.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class14/figures/ghement.png)

Here's [a link to the start of the "tweetorial"](https://twitter.com/IsabellaGhement/status/1363957122787024901) on some key practical aspects of understanding Poisson regression models.

## One Last Thing

FiveThirtyEight has [revamped their polling tracker](https://fivethirtyeight.com/features/weve-revamped-our-polling-tracker/)!
