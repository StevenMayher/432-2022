# 432 Class 07: 2022-02-01

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class07/432_2022_slides07.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class07/432_2022_slides07.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## Announcements

1. Grades on [Lab 1](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab01) are now available through the 432 Spring 2022 Grading Roster on our Shared Drive. 
    - You should have received your **Lab Code** (which you'll need to identify your work in the Roster) from Dr. Love via email (subject was "Your Lab Code for 432") on Monday morning 2022-01-31. If you didn't get your Lab Code, email Dr. Love immediately and he'll resend it.
    - **Regrade Requests**: If you want Dr. Love to review the grading of any Lab because you believe an error has been made in grading your work, please send those concerns through the Google Form at http://bit.ly/432-2022-lab-regrade-requests. See [Section 10.4 of the Syllabus](https://thomaselove.github.io/432-2022-syllabus/assignments-and-grading.html#appeal-policy-and-regrades) for more on this policy. The one exception is if there is a mistake in adding up points, or some similar clerical error. If you find such an issue, please bring it to Dr. Love’s attention via email, and he will resolve it immediately.
2. There is no Minute Paper this week. The next Minute Paper will be after Class 09.
3. Instructions for [Lab 4](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab04), [Lab 5](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab05) and [Lab 6](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab06) are now available, although I wouldn't worry about them before March.
4. Instructions for two more optional Labs: [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) and [Lab Z](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labZ) are now available. 
    - These optional Labs (including Lab X) are the best ways to improve your grade in the course (by as many as 2 points per optional Lab) and to impress Dr. Love outside of the required work. 
    - Please note the deadlines for these optional Labs that are now on the Calendar, and that Lab X is due earlier than Labs Y or Z. 
    - You can certainly do Labs X or Y today. Note that Lab Z requires that you've read all of *The Signal and the Noise*.
5. I started a poll on [Piazza](https://piazza.com/case/spring2022/pqhs432) about some ideas from Chapter 2 of *The Signal and the Noise*. Please feel encouraged to vote in the poll, and contribute to the discussion as well for some class participation credit. I'll keep the poll open until Wednesday afternoon.
6. I understand that both the Spring Festival (Chinese New Year) and Sollal (Korean New Year) are celebrated today, at the start of a new lunar year, and that this New Year is, in both the Chinese and Korean zodiacs, the Year of the Tiger, thanks to today's New York Times Crossword. I wish you all the best of fortune in the New Year...
7. Yes, I do the Times crossword puzzle every day (with my family Thursday - Sunday and alone Monday - Wednesday). I also do [Wordle](https://www.powerlanguage.co.uk/wordle/) (32 straight at 5 or fewer guesses) and now also [Nerdle](https://nerdlegame.com/), and occasionally some other sorts of puzzles.
8. The weather looks very bad for Thursday. We'll switch to Zoom if the roads become meaningfully difficult. I'll make a call on that as early as possible, probably by 8 AM Thursday.

## Learning More About the Harrell-Verse

In classes 07-09, we'll focus on a set of techniques from the `rms` and `Hmisc` packages for fitting and evaluating linear and logistic regression models developed by Frank Harrell at Vanderbilt, with his colleagues. As supplemental reading, I can strongly recommend:

- [An Introduction to the Harrell"verse": Predictive Modeling using the Hmisc and rms Packages](https://www.nicholas-ollberding.com/post/an-introduction-to-the-harrell-verse-predictive-modeling-using-the-hmisc-and-rms-packages/) by Nicholas Ollberding
- Frank Harrell's [Biostatistics for Biomedical Research (BBR) Course on YouTube](https://www.youtube.com/channel/UC-o_ZZ0tuFUYn8e8rf-QURA/videos) includes a series of lectures on many of the topics we'll be discussing in 432, in addition to several late-breaking items. Details on the course are available [here](https://hbiostat.org/bbr/) and the notes are linked below.
- Frank E. Harrell and Chris Slaughter [Biostatistics for Biomedical Research Notes](http://hbiostat.org/doc/bbr.pdf) (pdf) - also see the YouTube course above.
- Frank E. Harrell [Regression Modeling Strategies](https://github.com/THOMASELOVE/432-2022/blob/main/references/pdf/Harrell_Regression_Modeling_Strategies_2015_2e_protected.pdf), 2nd Edition, 2015.
- [datamethods](https://discourse.datamethods.org/) "is a place where statisticians, epidemiologists, informaticists, machine learning practitioners, and other research methodologists communicate with themselves and with clinical, translational, and health services researchers to discuss issues related to data: research methods, quantitative methods, study design, measurement, statistical analysis, interpretation of data and statistical results, clinical trials, journal articles, statistical graphics, causal inference, medical decision making, and more." This resource's [rationale is here](http://fharrell.com/post/disc), and Frank spends meaningful time responding to questions on that board, so when our course ends, you might consider looking there for some suggestions.

## What Should I Be Working On?

1. Once we review your Project A proposal and post your feedback and initial grade on Canvas, you will have 48 hours to revise your work (assuming your grade on the proposal is less than the full 10 points - see [the proposal rubric](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/rubric_proposal_draft.md) for details on grading.)
    - We hope to have all initial proposals reviewed by the end of the day on Thursday, although we're still waiting on proposals from six of you.
    - I have [some initial thoughts on project titles, provided here](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/proposals/titles.md).
2. [Lab 2](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab02) is due next Monday 2022-02-07 at 9 PM. You should already be able to complete all of the questions.
3. Today would be a good day to update your R packages! Click the Update button in the Packages window in RStudio.
4. Don't forget about responding to the Signal and the Noise poll on [Piazza](https://piazza.com/case/spring2022/pqhs432) and be sure you're caught up with the reading. Quiz 1 includes everything through Chapter 5.

## One Last Thing

Now that you have a Github account, you might want to use it. 

![](https://imgs.xkcd.com/comics/git.png) [XKCD link](https://xkcd.com/1597)

Here's some tailored advice from smart people...

- [How to Use Git/GitHub with R](https://rfortherestofus.com/2021/02/how-to-use-git-github-with-r/) blog post from David Keyes.
    - David recently (2022-01-13) tweeted about a new course: [Using Git and Github with R](https://twitter.com/dgkeyes/status/1481686458956075008) which looks like it could be very useful, too.
- [Happy Git and GitHub for the useR](https://happygitwithr.com/) book from Jennifer Bryan.

