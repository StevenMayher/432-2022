# 432 Class 06: 2022-01-27

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class06/432_2022_slides06.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class06/432_2022_slides06.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class06/figures/son2019.png)

## Announcements

1. Feedback on the Minute Paper after Class 05 [is now available](https://bit.ly/432-2022-min-05-feedback). Thanks to you all for completing this.
2. A draft of the Lab 1 Answer Sketch is now available in our Shared Google Drive. Sorry for the delay. Grades should be available next Tuesday.
    - I recommend the use of [the `cut2` function in the `Hmisc` package](https://search.r-project.org/CRAN/refmans/Hmisc/html/cut2.html) for creating the BMI categories, otherwise rounding error seems to be an issue.

## What Should I Be Working On?

1. [Project A proposal](https://github.com/THOMASELOVE/432-2022/tree/main/projectA) is due Monday 2022-01-31 at 9 PM. That should certainly be your main focus for this course right now.
    - The main problem so far is people trying to use multilevel (or hierarchical) data, where subjects are contained within other groups in a tree-like structure, with "parents" and "children". An example could be a model of patient health that contains measures for individual patients as well as measures for clinics within which the patients are grouped. Multilevel models are particularly appropriate for research designs where data for participants are organized at more than one level (i.e., nested data). The units of analysis are usually individuals (at a lower level) who are nested within contextual/aggregate units (at a higher level). While the lowest level of data in multilevel models is usually an individual, repeated measurements of individuals may also be examined. That sort of data won't work for Project A. You want a cohort of subjects measured at one time, usually.
    - You are welcome to create multi-categorical predictors from quantitative data, but not go in the other direction.
2. We hope you'll also read through Chapter 2 of *The Signal and the Noise*. It's about making political (and other types) of predictions, and explains what it means to be a fox rather than a hedgehog. We hope you enjoy it.
3. [Lab 2](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab02) is due Monday 2022-02-07. You should be able to do all five questions after today's class.

## More from Jeff Leek

Updates to some of Jeff Leek's Guides [are found here](https://github.com/search?q=user%3Ajtleek+guides), including guides to data sharing, genomics papers, reading scientific papers and giving talks.

## Two Last Things

1. [COVID Is Changing the Dynamics of Medical Research and Publishing](https://www.medpagetoday.com/opinion/second-opinions/96786) by Alexandre Loupy and Marc Raynaud provides an interesting viewpoint, I thought.
2. [Would seeing Spider-Man: No Way Home decrease COVID-19 Cases?](https://livefreeordichotomize.com/2022/01/16/would-seeing-spider-man-no-way-home-decrease-covid19-cases/) by Lucy D'Agostino McGowan weighs in with a statistical analysis motivated by a sketch on Saturday Night Live earlier this month.

