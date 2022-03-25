# 432 Class 19: 2022-03-24

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/432_2022_slides19.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/432_2022_slides19.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/poorman1.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/poorman2.png)

## Today's Agenda

Today we'll focus on two things:

1. survival analyses using Cox proportional hazards models for time-to-event outcomes with censoring. 
2. robust linear models using Huber weights, or bisquare weights or quantile regression.

## Announcements

1. I gave everyone credit for the Minute Paper after Class 18. Due to a mistake on my end, I wasn't able to associate a name with most of the submissions, and I know some people submitted more than once. [Feedback is now available, here](https://bit.ly/432-2022-min-18-feedback).
2. I made some adjustments to the topics listed in the [Calendar](https://thomaselove.github.io/432/calendar.html). We're set through Class 23 at the moment, and I will post more specific information about Classes 24-26 as soon as I can.
3. Reminder: Now would be a good time to upgrade to [R version 4.1.3](https://cran.case.edu/), and to [RStudio version 2022.02.0-443](https://www.rstudio.com/products/rstudio/download/#download) as well as [updating your packages](https://thomaselove.github.io/432/r_packages.html). See the [Class 18 README](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class18/README.md) for more details.
4. [rstudio::conf(2022)](https://www.rstudio.com/blog/rstudio-conf-2022-is-open-for-registration/) is now open for registration. If you can’t make it in person, virtual registration will be free and available closer to the date (2022-07-25 through 2022-07-28 in DC).
5. [Mapping and geographic data analysis with the simple features package in R](https://paldhous.github.io/NICAR/2022/r-sf-mapping-geo-analysis.html) has a lot of nice material, prepared by P. Aldhous for the 2022 NICAR meeting.
6. [How to use Fonts and Icons in ggplot](https://albert-rapp.de/post/2022-03-04-fonts-and-icons/) with [the showtext package](https://github.com/yixuan/showtext), a blog post from Albert Rapp.

## Upcoming (non-Minute Paper) Deliverables

1. By Friday 2022-04-01, we hope you'll have read through Chapter 11 of *The Signal and the Noise*. Finish the book by 2022-04-15.
2. Sunday 2022-04-03 at 9 PM: [Project B Outline and Scheduling Form](https://bit.ly/432-2022-projectB-register). 
    - See the instructions as well as [the Class 17 README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class17).
3. Monday 2022-04-04 at 9 PM: [Lab 5](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab05) due to Canvas.
4. Monday 2022-04-11 at 9 PM: [Lab 6](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab06) due to Canvas.
5. [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX) and [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) and even [Lab Z](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX), if you've finished reading *The Signal and the Noise*.

## One Last Thing

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck0.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck1.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck2.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck3.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck4.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck5.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class19/figures/zobeck6.png)

- [Source (Mark Zobeck's twitter thread)](https://twitter.com/MarkZobeck/status/1506615109170442244)
- The two references in the final image here are:
    - [Statistical Problems to Document and To Avoid](https://biostat.app.vumc.org/wiki/Main/ManuscriptChecklist)
    - [Glossary of Statistical Terms (from Frank Harrell)](https://hbiostat.org/doc/glossary.pdf)

