# 432 Class 14: 2022-03-01

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class14/432_2022_slides14.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class14/432_2022_slides14.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## Today's Agenda

Today, we'll be presenting some key ideas on fitting models for count outcomes. Counts are discrete (rather than continuous) and counts are typically integers (0, 1, 2, 3 and so on) and cannot be made more precise. Relevant materials (some a little out of date now, I fear) are available in Chapter 19 of the [Course Notes](https://thomaselove.github.io/432-notes/).

Methods we will touch on today include Poisson regression and negative binomial regression, along with augmentations of these two approaches to inflate the number of zeros predicted, and also "hurdle" versions which specify one process for zero counts and another for positive counts. In Chapter 19, we discuss all of these, as well as another approach, called a tobit (or censored) regression model, which we will postpone until later in the term.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class14/figures/ghement.png)

Here's [a link to the start of the "tweetorial"](https://twitter.com/IsabellaGhement/status/1363957122787024901) on some key practical aspects of understanding Poisson regression models.

## 432-Specific Items

1. There is a Minute Paper after today's class. **Details to come.**
2. The Quiz 1 answer sketch is now on our Shared Drive in the Quiz 1 folder, and has been revised to add materials for Questions 2 and 21. You should have an email from me (sent 2022-02-23) containing your grade. See the last page of the Answer Sketch for class-wide results. I will close the Quiz 1 grades on 2022-03-04 at 9 PM. If you have questions about your grade, please email me before then to ask them.
3. The [Course Calendar](https://thomaselove.github.io/432/calendar.html) now shows March at the top. January and February are now found at the bottom of the document.
4. Project B instructions are coming this week. **Details to come.**

## Why I use `read_csv()` all the time, and never use `read.csv()` anymore

1. `read_csv()` is much faster than `read.csv()`, 
2. `read_csv()` provides a progress meter and a compact method for specifying column types,
3. `read_csv()` will read compressed files automatically,
4. `read_csv()` automatically creates a tibble, and
5. `read_csv()` allows me to speed the process of debugging by providing much more useful error messages about which rows are problematic, especially when the error is non-fatal.

- For more details, see the [Data import section of R for Data Science](https://r4ds.had.co.nz/data-import.html).
- From Josh Gonzales at Medium: [read_csv(): The Best Way to import CSV data into R](https://medium.com/r-tutorials/r-functions-daily-read-csv-3c418c25cba4)

## Exploding Coefficients in Logistic Regression

Take a look at [this toy example with explosive coefficients](https://rpubs.com/TELOVE/explosion_logistic_432) to see one way in which this problem can emerge and what to do about it.

## More General Announcements

1. David Robinson did a Tidy Tuesday live screencast on YouTube [analyzing the World Freedom Index in R](https://www.youtube.com/watch?v=VOzUHk3aaBw). I hope you find it useful and interesting.
2. The [Cleveland R Users Group](https://www.meetup.com/Cleveland-UseR-Group/) is holding a Project Showcase on 2022-03-23 at 6 PM. If you're interested in attending or presenting, [here is the information](https://www.meetup.com/Cleveland-UseR-Group/events/284281072/).
3. DPhi is holding a [5-week data science bootcamp in Python](https://dphi.tech/bootcamps/5-week-data-science-bootcamp) starting 2022-03-11 which seems to be free. I can't tell you anything about it, except that a couple of past students took a prior version and told me they liked it. There's material here on feature selection and building machine learning models.
4. If you're interested in working on a COVID-19 project for Project B, you might consider [these repositories from BroadStreet Health](https://github.com/orgs/BroadStreet-Health/repositories).

## One Last Thing

FiveThirtyEight has [revamped their polling tracker](https://fivethirtyeight.com/features/weve-revamped-our-polling-tracker/)!
