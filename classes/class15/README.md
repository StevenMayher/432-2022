# 432 Class 15: 2022-03-03

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class15/figures/carr_2021.png)

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class15/432_2022_slides15.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class15/432_2022_slides15.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class15/figures/rq.png)

## Project A

1. Please remember to submit [Project A](https://github.com/THOMASELOVE/432-2022/tree/main/projectA) by 9 PM on Friday 2022-03-04. 
    - Incomplete work, or late work (arriving after 9:30 PM) will be massively penalized. Do not be late.
    - If you are working with a partner, one of you should submit everything, and the other should submit a one-page note to Canvas stating who your partner is, and that your partner will submit the work by 9 PM Friday.
    - If you are in the midst of a crisis that will prevent you from submitting the work in a timely fashion, Dr. Love needs to know that **now**. Email him directly (and now), or talk to him right after class.

### A Few Last Thoughts on Project A

I asked people in the Minute Paper to tell me what their biggest concern was about the Minute Paper. Some common concerns were:

- Getting it finished on time.
- Making sure I meet all of the requirements.
- Making good choices about what to present in the available time.
- Feeling not completely confident about my decisions during the analysis.

A few other common issues:

- Using an outcome transformation other than the square, the square root, the logarithm or the inverse makes it very challenging to interpret the results.
    - Indeed it does. That's why I wouldn't do it.
- I have one predictor which is on a very different scale than the others.
    - Have you considered rescaling it? If it's in thousands of dollars, rather than dollars, does that help?
- Improving my visualizations 
    - Generating attractive and readable versions of nomograms, plot(summary()) seem to be the main concern here. Be sure to show your data.
- Working with missing data. 
    - It is safest to assume MCAR for outcomes, MAR for all predictors for this project, from my perspective.
    - I am equally happy with single or multiple imputation strategies for most of the work in this Project.

Here are some other issues that came up and that I want to talk about.

1. An ANOVA comparison of model Z to model Y can usually be done with `lrm` fits by running just `anova(modelZ)`, since model Y is just model Z without the non-linear or interaction pieces, and `anova(modelZ)` tells us about that directly. Same goes for model B vs. A.
2. There are **no** key steps to Project A analyses deliberately unmentioned in the instructions.
    - A related question is "Should I do everything I can think of with my data" and the clear answer is **NO**.
    - We don't grade by volume of written material, but by the quality of the material you present. Less is more. Some specific examples:
        - Validating the models. For OLS, the minimum requirement is validated summary statistics with validate for models A and B. There is no requirement that you also do something like split into training/test samples or use a k-fold cross-validation strategy. Same applies (with different summaries) for models Y and Z.
        - Writing a description of the effect of at least one predictor doesn’t mean you have to write one for each of the predictors. And you do this for the two **winning** models (one linear, one logistic) not all of the models you fit.
        - Nowhere in the instructions do we suggest that you need to use tidymodels methods to fit models, or to use things like stan to fit a model. We're not secretly hoping you'll do so anyway.
3. Don't go over the time limit in the video presentation. Cut some of what you were going to talk about instead. Focus on the things we emphasized in the instructions.
4. Good luck!

## Announcements

1. Feedback on the Minute Paper after Class 14 **will be available by class time**.
2. Remember that we do not have class next week, thanks to Spring Break. Our next class will be Tuesday 2022-03-15.
    - Dr. Love will be mostly away from email and not responding to Piazza from March 5-10. 
    - TA office hours are cancelled from March 5-11.
    - It would be a great idea to work on [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX) and [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) (and catch up on reading *The Signal and the Noise* - you should have completed at least through Chapter 8) over the break. I also posted an op-ed to Piazza that we'll discuss on 2022-03-15, to which you can contribute discussion.
    - If you want to get a little bit ahead over the break, I'd focus on [Lab 4](https://github.com/THOMASELOVE/432-2022/blob/main/labs/lab04/lab04_instructions.md) which is due on 2022-03-21, and which you should be able to complete after today's class.
3. [Project B](https://github.com/THOMASELOVE/432-2022/tree/main/projectB) instructions will be available by 9 PM Friday.
    - During the break, I recommend you read through the Project B instructions, and perhaps try to identify a partner if you want to work with one, but otherwise let that wait until we return on 2022-03-15. This will let me discuss the assignment with you in class 16. Also, the first deliverable with regard to Project B is brief and isn't due until 2022-03-28.

## This is our cat, Fuzzington.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class15/figures/fuzz_asleep.jpg)

## One Last Thing

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class15/figures/parade.png)
