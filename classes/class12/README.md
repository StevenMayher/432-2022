# 432 Class 12: 2022-02-17

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class12/432_2022_slides12.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class12/432_2022_slides12.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class12/figures/amira.png)

## Today's Agenda

We'll clean up some loose ends related to linear and logistic regression today, in light of questions we've seen in the Labs, in TA office hours, on Piazza, and in the Minute Papers.

## Announcements

1. We'll continue talking about the `tidymodels` packages in Class 13, in particular describing some methods for doing logistic regression with those tools. I'll remind you that there's [a list in the Class 11 README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class11#the-tidymodels-packages) of some useful things to read if you want to learn more about or go further with this approach. I have modified the [Course Calendar](https://thomaselove.github.io/432/calendar.html) to reflect this change.
2. A reminder that we do have class next Tuesday 2022-02-22, but **not** on Thursday 2022-02-24. Dr. Love will be at AHRQ study section, reviewing grants. We hope you'll use this time to work on Project A, which is due on **Friday 2022-03-04 at 9 PM**.
3. Sorry to be picky, but it's called **logistic** regression. It's **not** called *logistical* regression or *logistics* regression or anything else.
4. [Minute Paper after Class 11 feedback](https://bit.ly/432-2022-min-11-feedback) is now available. The Course Grading Roster on our Shared Drive is up to date through this Minute Paper, and Lab 2. Lab 3 grades will appear early next week.
5. I've posted to Piazza (in Question @134) in an effort to try to identify some great restaurants in the Cleveland area that won't break a student's budget. If you have a suggestion, please add to the discussion there. I'll keep it up until Spring Break.

## On Why We Impute

A student asked: 

> Can you explain why imputing is sometimes preferred over doing complete cases analysis? I still can’t wrap around the idea of faking values and then predicting based on that.

Thinking of it that way isn’t helping you. So stop. Some key points:

1. Data are expensive to gather - you don't want to waste them. Moving to a complete case analysis means any observations partially completed go totally unused.
2. Our choice is between assuming all missing values are missing completely at random (MCAR = the missing values are simply a random subset of all of the observations so that there are NO systematic differences between the missing values and the observed values), which is the only case in which a complete case analysis would be appropriate. Such an assumption...
    - can never be proven to be true in real data.
    - is easily shown to be false in lots of real data settings, or at least it can be easily shown that the known data on other variables for people with a missing value in some target are different from the known data on those same other variables for people with an observed value of the target.
3. When data are not MCAR but just missing at random (MAR = Missing at random means there might be systematic differences between the missing and observed values, but these can be entirely explained by other observed variables) a complete case analysis would be much worse than multiple imputation, and somewhat worse than single imputation. In health data, MAR is usually a much more tenable assumption - or at least one that’s easier to convince yourself of - than MCAR.
4. You might want to read [this interesting article "What is the difference between missing completely at random and missing at random?"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4121561/) by Krishnan Bhaskaran and Liam Smeeth in the International Journal of Epidemiology, 2014. They lay out the most common scenario that comes to me from clinical researchers right at the start of their article...

> Clinical researcher: I'm not considering multiple imputation for my study because I read that the data have to be missing at random. I am using routine health records, and I have missing blood pressure data. But they won't be randomly missing, because people with blood pressure missing are totally different to people with blood pressure recorded.

## About [Quiz 1](https://github.com/THOMASELOVE/432-2022/tree/main/quiz/quiz1) and Related Issues

1. Quiz 1 will be available to you by 5 PM today. [Go here](https://github.com/THOMASELOVE/432-2022/tree/main/quiz/quiz1) for everything you need. The Quiz is due Monday 2022-02-21 at 9 PM.
    - **PLEASE** read the Quiz 1 instructions carefully.
    - **PLEASE** submit your completed Google Form Answer Sheet by **9 PM Monday**. We won't grade late work on the Quiz, and we won't be sympathetic to pleas for extensions. You have four days to do the Quiz, and it should take you 4-6 hours.
    - If you have questions about the Quiz, you have only two ways to get an answer:
        - Post a **private** question on Piazza to the instructors, or email `431-help at case dot edu`.
        - In either case, we will answer all questions received by 5 PM Monday. After that, you're basically on your own.
2. TA office hours **will be** held during the Quiz, for general questions and project questions, but if you have a specific question about the Quiz, you'll have to ask it in one of the two allowable ways mentioned above.
3. Piazza will close at 5 PM to everything but private questions to the instructors. It'll reopen after the Quiz deadline.
4. It is extremely rare for a student to receive a perfect score on one of my Quizzes. There are just too many ways to make a small mistake, and too many details I'm trying to assess. Don't panic if you have trouble with two or three questions. Just walk away and try again later. Or ask us for help! **Good luck to you all**!

## One Last Thing

It's probably time to trot this out again, from [XKCD](https://xkcd.com/2048/)...

![](https://imgs.xkcd.com/comics/curve_fitting.png)

