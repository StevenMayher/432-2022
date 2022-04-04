# 432 Class 22: 2022-04-05

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class22/432_2022_slides22.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class22/432_2022_slides22.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## From [Kevin Reuning](https://twitter.com/KevinReuning/status/796107864704188420)

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class22/figures/shruggies.png) 

## Announcements

1. There is a Minute Paper after Class 22 due tomorrow (2022-04-06) at Noon. **Details to come.**
2. An answer sketch for Lab 5 will be posted to our Shared Drive **by class time**.
3. [Lab 6](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab06) is due next Monday 2022-04-11 at 9 PM.
4. Quiz 2 will be in your hands on Thursday 2022-04-14 at 5 PM. It is **now due** Tuesday 2022-04-19 at 9 AM.
    - The Quiz definitely includes materials from 432 classes **1-22**, plus all of *The Signal and the Noise* and all of Jeff Leek's *How To Be a Modern Scientist*. The Quiz does not include anything from Class 23, but may include things from Classes 24-25. Dr. Love will let you know during each of those classes (24 and 25).
5. Tuesday 2022-04-19 is a Project B working day, and we will have no 432 class that day.
6. Optional [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX) (website) is due Wednesday 2022-04-20 at noon. Congratulations to those of you who've already completed it. 
7. [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) and [Lab Z](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labZ) are due by our final course deadline (2022-05-02 at noon.)
8. I will announce the topics to be discussed in classes 24-26 as soon as possible.

## Four things I hope you will do when you finish this course and go out into the world...

1. be confident in your ability to use statistical thinking in developing scientific insight 
2. make a consistent serious effort to identify and develop  effective research questions and study designs to address them
3. make good, informed decisions about how to complete analytic work and produce results that avoid common pitfalls, and that are well-motivated by the data, and 
4. finally (and probably most importantly) communicate your findings in a way that allows people to understand them, evaluate them, and then make good decisions based on them.

## Today's Discussion

will be centered around replicable research as well as thinking about power issues through retrospective design. The main resources are:

- Andrew Gelman and John Carlin [Beyond Power Calculations: Assessing Type S (Sign) and Type M (Magnitude) Errors](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class22/references/Gelman_Carlin_2014_Beyond_Power_Calculations.pdf)
- Ronald L. Wasserstein, Allen L. Schirm & Nicole A. Lazar (2019) [Moving to a World Beyond "p < 0.05"](https://www.tandfonline.com/doi/full/10.1080/00031305.2019.1583913), *The American Statistician*, 73:sup1, 1-19, DOI: [10.1080/00031305.2019.1583913](https://doi.org/10.1080/00031305.2019.1583913). The PDF of this article [is also available here](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class22/references/ASA_2019_A_World_Beyond.pdf).
- Ronald L. Wasserstein & Nicole A. Lazar (2016) [The ASA's Statement on p-Values: Context, Process, and Purpose](https://www.tandfonline.com/doi/full/10.1080/00031305.2016.1154108), *The American Statistician*, 70:2, 129-133, DOI:
[10.1080/00031305.2016.1154108](https://doi.org/10.1080/00031305.2016.1154108). PDF [also available here](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class22/references/ASA_2016_Pvalues_Context_Process_Purpose.pdf).

### Need to have a tough talk with someone about statistical significance, and/or p values?

- The ASA Section on Teaching of Statistics in the Health Sciences has [some interesting material](https://tshsblog.wixsite.com/main/single-post/2018/05/08/ReadyResources-Publications-for-teaching-p-values)
- I've given these posts: [Why I've lost faith in p values, part 1](https://lucklab.ucdavis.edu/blog/2018/4/19/why-i-lost-faith-in-p-values) and [Why I've lost faith in p values, part 2](https://lucklab.ucdavis.edu/blog/2018/4/28/why-ive-lost-faith-in-p-values-part-2) to a few people. Maybe they'll help you.
- "[Abandoning statistical significance is both sensible and practical](https://peerj.com/preprints/27657/)" by Amrhein, Gelman, Greenland and McShane at PeerJ Preprints.
- Frank Harrell's post about "[Language for communicating frequentist results about treatment effects](https://discourse.datamethods.org/t/language-for-communicating-frequentist-results-about-treatment-effects/934)"
- "[Calculating Observed Power Is Just Transforming Noise](https://lesslikely.com/statistics/observed-power-magic/) at [LessLikely](https://lesslikely.com/)
    - "A discussion of events that transpired in the past year, where a group of surgical researchers decided to ignore much of the statistical literature and promote a highly misleading practice of calculating post-hoc power using the observed effect size."
    - Some related pieces at LessLikely include "[Misplaced Confidence in Observed Power](https://lesslikely.com/statistics/misplaced-power/)" and "[P-Values Are Tough and S-Values Can Help](https://lesslikely.com/statistics/s-values/)".
- Andrew Gelman: [Statistical-significance thinking is not just a bad way to publish, it’s also a bad way to think](https://statmodeling.stat.columbia.edu/2019/03/16/statistical-significance-thinking-is-not-just-a-bad-way-to-publish-its-also-a-bad-way-to-think/) - the money quote: "it’s ultimately not about what it takes, or should take, to get a result published, but rather how we as researchers can navigate through uncertainty and not get faked out by noise in our own data."

## Some Additional Notes

- If you'd like to read a little more about Fisher and the Lady Tasting Tea experiment, here's the [Wikipedia entry](https://en.wikipedia.org/wiki/Lady_tasting_tea). 
    - If you'd like to read a good deal more about the issue and the statistical revolution that took place in the 1900s, there's a very nice book by David Salsburg called [The Lady Tasting Tea](https://en.wikipedia.org/wiki/The_Lady_Tasting_Tea) that I can heartily recommend. 
    - R. A. Fisher himself has (at best) a troubling history that you can [read about here](https://en.wikipedia.org/wiki/Ronald_Fisher).
- To learn more about current thinking on sample size requirements for linear regression, I suggest Peter C. Austin and Ewout W. Steyerberg (2015) The number of subjects per variable required in linear regression analyses J Clinical Epidemiology 68: 627-636, which is [available on our References page](https://github.com/THOMASELOVE/432-2022/blob/main/references/pdf/Austin_and_Steyerberg_2015_subjects_per_variable_in_linear_regression_jce.pdf).

## One Last Thing

[The Eureka Phenomenon](https://www.yumpu.com/en/document/read/4657323/the-eureka-phenomenon-by-isaac-asimov) by Isaac Asimov is something you might want to be aware of.

