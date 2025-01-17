# 432 Class 26: 2022-04-21

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class26/432_2022_slides26.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class26/432_2022_slides26.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class26/figures/signal.png) [Source: Saturday Morning Breakfast Cereal](http://smbc-comics.com/comic/signal)

## Announcements

1. I've graded [Quiz 2](https://github.com/THOMASELOVE/432-2022/tree/main/quiz/quiz2).
    - An [answer sketch for Quiz 2 is available](https://github.com/THOMASELOVE/432-2022/blob/main/quiz/quiz2/432_quiz2sketch_2022.pdf). This document includes details on how each question was graded.
    - The questions that didn't go well were 2-3 (imputation), 20 (Silver), 22 (LASSO), 26 (predicted counts comparison) and 29 (Leek where all statements were true).
    - Dr. Love emailed you your grades on Quiz 2 on Wednesday evening 2022-04-20.
    - Almost everyone did pretty well on the Quiz. Nearly all scores were between 70 and 100 out of 100 points, and the median was 84.
2. Grades on [Lab 6](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab06) are now available on the Course Grading Roster on our Shared Drive. 
    - The Answer Sketch for Lab 6 is also available in the Lab 06 Materials folder on our Shared Drive.
    - Five of the essays written in response to Question 1 are also available in a document on our Shared Drive. Congratulations!
    - If you need a regrade on Labs 1-6, you should submit the [Lab Regrade Form](http://bit.ly/432-2022-lab-regrade-requests) as soon as possible. [See here for details](https://github.com/THOMASELOVE/432-2022/tree/main/labs#regrade-requests).
3. Thanks to those of you who submitted [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX).
4. Thanks also to the 14 of you who contributed suggestions on Piazza for future students (and this is still an open opportunity until 2022-05-02 at Noon), and the 18 who shared thoughts on Leek, and 15 who shared thoughts on The Signal and the Noise (these oppportunities are now closed for grading purposes.) 
5. TA office hours continue through this Sunday 2022-04-24. We **implore** you to take advantage of this resource while it lasts. While Piazza will remain open until 2022-05-02 at Noon, we'll be watching it less closely after this Sunday.
6. All notes I will have for you after today can be found at 
    - the [reminders page about Project B and the end of the semester](https://github.com/THOMASELOVE/432-2022/blob/main/projectB/reminders.md), along with
    - the [post-class README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/postclass).

## Today's Presentation

1. I'll start with slides, as usual.
2. Then I'll share [a few interesting visualizations, and also discuss a few topics briefly](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class26/stuff.md) and leave you with some advice. 
3. I'll also point you to the [post-class README](https://github.com/THOMASELOVE/432-2022/tree/main/classes/postclass) for things to do to maintain and enhance what you've learned in the course.

## Some Reminders about Project B, and the end of the semester

Again, those key reminders [will be found here](https://github.com/THOMASELOVE/432-2022/blob/main/projectB/reminders.md). Please take a look.

## A Few Last Things

1. Erika Hutt had her baby (a little girl) last Friday. Everyone is OK.
2. Let me take one last opportunity to thank our Teaching Assistants, especially Wyatt, Stephanie and Shiying who are here with us today.
3. Yes, the [Mets](https://www.mlb.com/mets) are off to a fine start, with 9 wins in 13 games. This is a key to my daily mood, I'm afraid.
4. I have settled into using ROUTE or TENOR most of the time in doing [Wordle](https://www.nytimes.com/games/wordle/index.html) and [Dordle](https://zaratustra.itch.io/dordle). When doing longer Wordles ([Quordle](https://www.quordle.com/#/), [Octordle](https://octordle.com/), [Sedecordle](https://www.sedecordle.com/) and [Duotrigordle](https://duotrigordle.com/)) I use SPORE, GUILT and CANDY as my first three guesses, or sometimes modest variants, like PROSE or SPORT/GUILE. I also like [Squareword](https://squareword.org/), [Waffle](https://wafflegame.net/), and more recently, [Xordle](https://xordle.xyz/).
5. My family and I do the New York Times crossword together on Thursday-Sunday. I do them (usually alone) on Monday-Wednesday. Our current streak (begun on 2021-11-01) is 171, and our longest streak is 303, back in 2020-21. We've solved 1110 puzzles through Wednesday of this week. My personal fastest time for a Monday puzzle is 4:13, but our family did one in under four minutes earlier this month. Our average times by day of the week are:

All Time | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday
:------: | :-----: | :----: | :-----: | :----: | :-----: | :----: | :-----: 
Daily Mean | 9:08 | 11:10 | 16:19 | 17:27 | 16:52 | 19:17 | 32:21
Fastest Time | 3:46 | 5:08 | 6:05 | 8:15 | 9:54 | 8:52 | 15:43

Since 2021-11-01 | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday
:------: | :-----: | :----: | :-----: | :----: | :-----: | :----: | :-----: 
Mean | 6:07 | 8:40 | 13:48 | 13:58 | 16:19 | 17:16 | 25:16
SD | 1:49 | 2:46 | 4:22 | 3:08 | 3:46 | 5:11 | 3:31
Median | 5:42 | 8:02 | 13:48 | 13:32 | 15:45 | 16:05 | 25:27
n | 25 | 25 | 25 | 24 | 24 | 24 | 24
Fastest Time | 3:46 | 5:08 | 7:37 | 8:15 | 11:32 | 11:22 | 15:43
Slowest Time | 11:48 | 16:01 | 25:26 | 21:14 | 30:58 | 33:12 | 34:08


