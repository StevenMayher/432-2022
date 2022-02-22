# 432 Class 13: 2022-02-22

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class13/432_2022_slides13.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class13/432_2022_slides13.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://imgs.xkcd.com/comics/data_trap.png) from [XKCD](https://xkcd.com/2582)

## Announcements

1. [Project A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA) is due next Friday 2022-03-04 at 9 PM. 
    - Be sure to review the [Submission Requirements](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/02_projectA_analyses.md#submission-requirements) and some of what we'll be doing to [evaluate your final materials](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/02_projectA_analyses.md#evaluating-your-final-materials) before you submit your work.
    - You should be submitting (1) a single R Markdown file containing the 13 section headings [described here](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/02_projectA_analyses.md#the-portfolio) that produces (2) a single HTML file containing all work on the portfolio, plus (3) your slides for your presentation and (4) your video recording (we prefer .mp4) and (5) your raw data and (6) your cleaned (.Rds) data.
    - In writing your portfolio, take the [Discussion section (section 10)](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/02_projectA_analyses.md#section-10-the-discussion) as seriously as you take the new analytic sections 8 and 9.
2. Remember that we don't have class (Project A working day) this Thursday. We return to in-person class one week from today.
3. [TA Office Hours](https://thomaselove.github.io/432/contact.html) continue every day through 2022-03-04 but will then close until 2022-03-12.
4. There is no Minute Paper this week. Our next Minute Paper is due next Wednesday (after Class 14).
5. Grades and TA feedback on Lab 3 are now available in the 432 Spring 2022 Grading Roster Google Sheet on our Shared Drive, and four nice examples of Essays responding to Question 10 from Lab 3 are also now available [in our Shared Drive](https://docs.google.com/document/d/1edHhTNRs-S4UEbNN-HWqOShxrb718zrTF44RY13_6dM/edit?usp=sharing).
6. Spring Break (no class March 8 or 10) is an excellent time to work on [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX), not to mention [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) and (if you've finished reading *The Signal and the Noise*, [Lab Z](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labZ).) 
    - I wouldn't be worrying about Labs 4 or 5 before you complete Project A, although you may want to start on them during the Break. [Lab 5](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab05) is mostly about `tidymodels` stuff, so you might look at that one first. [Lab 4](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab04) uses the material we'll start to talk about next week.
7. You'll need to finish reading *The Signal and the Noise* through Chapter 8 by our first class after Spring Break on 2022-03-15.
    - Chapter 6 is about how sensitive outcomes can be to error and look at predicting GDP growth
    - Chapter 7 is about disease outbreaks
    - Chapter 8 demonstrates the importance of Bayes' Theorem

## Quiz 1 Grading Update

I'll provide an update in class. The two bullets below will help me do so.

- Items 14, 19a and 22
- Items 2abcd, **5b**, **6**, 8a, 11, 13ab, 16ab, **17ab**, 18

## References from Today's Class

Three articles by Jonah Gabry and Ben Goodrich:

- "[How to Use the `rstanarm` Package](http://mc-stan.org/rstanarm/articles/rstanarm.html) 
- "[Prior Distributions for `rstanarm` Models](http://mc-stan.org/rstanarm/articles/priors.html) 
- "[Estimating Generalized Linear Models for Binary and Binomial Data with rstanarm](http://mc-stan.org/rstanarm/articles/binomial.html)

Also, don't forget about Max Kuhn and Julia Silge's [Tidy Modeling with R](https://www.tmwr.org/) and about the [main page for the tidymodels framework](https://www.tidymodels.org/).

## Other Resources

1. I'm not sure I've shared the New England Journal of Medicine's [New Guidelines for Statistical Reporting in the Journal](https://www.nejm.org/doi/full/10.1056/nejme1906559) from 2019-07-18, but someone was looking for some advice in this regard, so there it is. It was written to reflect a move towards more parsimonious reporting of p values. There's good advice here for those of you struggling with these issues in preparing your work for Project A, or for work outside of 432.
2. I found some interesting items in the [Journal of Data Science](https://jds-online.org/journal/JDS) recently, and thought you might want to have a look.
3. I also recommend Maggie Koerth's conversation at FiveThirtyEight with Jennifer Nuzzo entitled [What COVID Positivity Rates Can (And Can’t) Tell Us](https://fivethirtyeight.com/features/what-covid-positivity-rates-can-and-cant-tell-us/) focusing on "test positivity" and COVID-19.
4. Those of you looking for more content on things like supervised and unsupervised learning might enjoy [Modern Data Science with R](https://mdsr-book.github.io/mdsr2e/) by Benjamin S. Baumer, Daniel T. Kaplan, and Nicholas J. Horton.

## One Last Thing

You might enjoy [Words Said by No Academic Ever](https://phdcomics.com/comics/archive.php?comicid=2048) or perhaps [Academic Wordle](https://phdcomics.com/comics/archive.php?comicid=2051) from Jorge Cham at PhD Comics.
