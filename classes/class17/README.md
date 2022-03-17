# 432 Class 17: 2022-03-17

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class17/432_2022_slides17.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class17/432_2022_slides17.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## Time to Event Data

Materials on time-to-event outcomes are found in Chapters 22-24 of our [Course Notes](https://thomaselove.github.io/432-notes/). This is a very brief introduction to the topic. We offer a full-semester course (PQHS 435) every spring in Survival Analysis, which goes into much more detail.

- In today's slides, I make reference to [this PDF guide by David Diez on Survival Analysis in R from OpenIntro](https://www.openintro.org/book/surv_in_r/), which I also recommend, and which provides the `OISurv` package.
- I strongly recommend you look at the (7-minute) video "[Survival Curves: Showing More by Showing Less](https://www.youtube.com/watch?v=EoIB_Obddrk)" on YouTube posted by Frank Harrell, which explains the logic behind several tools in the `rms` package which let you interact with a graph and a non-parametric survival function which saves a little more information than the usual Kaplan-Meier plot.
- The **survminer** package is where you can find the **ggsurvplot** approach we'll take today. 
- For more customization of plots like the Kaplan-Meier curves we'll build today, visit https://rpkgs.datanovia.com/survminer/ or https://github.com/kassambara/survminer/. 
    - For instance, they provide a [PDF cheat sheet](https://rpkgs.datanovia.com/survminer/survminer_cheatsheet.pdf) which was pretty helpful to me.
- You may also be interested in learning more about concordance in survival analysis (and in general) [from this vignette](https://cran.r-project.org/web/packages/survival/vignettes/concordance.pdf) (pdf).

## What Should I Be Working On?

1. [Lab 4](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab04) is due Monday 2022-03-21 at 9 PM. You can complete it today.
2. We want you to have read through Chapter 9 of Nate Silver's *The Signal and the Noise* before our next class. It's about chess, and if you like games, Chapter 10 is about poker, and you should have that read by 2022-03-29.
3. [Lab X](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labX) and [Lab Y](https://github.com/THOMASELOVE/432-2022/tree/main/labs/labY) are available to be done now, and don't require any material you haven't seen.
4. [Project B Outline and Scheduling Form](https://bit.ly/432-2022-projectB-register) is due **Sunday 2022-04-03 at 9 PM**. 
    - I encourage you to read the [Project B instructions](https://github.com/THOMASELOVE/432-2022/blob/main/projectB/projectB_instructions_2022.md) and look over the [Project B template](https://rpubs.com/TELOVE/projectB-template-432-2022) before you open and certainly before you complete the [Outline and Scheduling Form](https://bit.ly/432-2022-projectB-register). 
    - You might also want to look at the [Toy NHANES data cleaning example](https://rpubs.com/TELOVE/toy-nhanes-432), even if you're not using NHANES data.
5. [Lab 5](https://github.com/THOMASELOVE/432-2022/tree/main/labs/lab05) is due Monday 2022-04-04 at 9 PM (**the day after the Project B form**). Lab 5 uses tidymodels to fit and assess the performance of some models. As such, you can complete it today. There's no new material on these topics coming.

## Announcements

1. Feedback on the Minute Paper after Class 16 [is now available](https://bit.ly/432-2022-min-16-feedback).
2. Project A Grading Status update coming in class.
3. If you're not coming to class regularly, fix that. This **isn't a zoom class**. There should be 43 students in this class, and of late, we're under 30 attendees. This needs to stop now. Challenges shouldn't be happening twice a week for multiple weeks. If you're not here, you're not asking questions, and I don't know you. That is a problem.
4. If I'm not referring to you by name when I see you in class, or when you stop by after class, I'd try to fix that, were I you.

## Some Advice on Naming Things

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class17/figures/wooldridge.png) [Source](https://twitter.com/jmwooldridge/status/1501157439726575616)

Naming things is hard. [Jenny Bryan has you covered](https://speakerdeck.com/jennybc/how-to-name-files). The three principles are:

- machine readable
- human readable
- play well with default ordering

A perfectly lovely **file name** convention for project A was `2022-03-01_yourname_432projA.xxx`

Naming R data frames (tibbles) can be challenging, as well. I'll add 

- don't name tibbles things that are also data frames or functions or other things in R
- don't name tibbles things that make no sense without a very detailed explanation
- 8 characters is usually a good maximum for a tibble name that you'll use often
- if you insist on separating words in a tibble name, use underscores.

Here were the names of the main tibbles that people built for Project A, some of which were more useful than others...

- `a_sample`, `analysis_data`, `data_clean`, `projectA`, `main_df`
- `split_tidy_data`, `tidy`, `tidy_tibble`, `tidy_tracks`, `tidydata`
- `final_A`, `final_data`, `FinalA`, `hotel_final`, `hrs`, `hrsdata`
- `New8`, `place`, `places`, `climbers_train1`, `infant_mort_sample`, `gss2021_423`
- `brfss_2`, `chr_2021`,  `dat_ads`,  `jobloss`, `llcp`, `nhsda1999_oxy`
- `coffee_ratings`, `starbucks`, and `starbucks` again, `wine1` and `wine2`

You want naming conventions? OK, [here are some from Harvard](https://datamanagement.hms.harvard.edu/collect/file-naming-conventions).

# One Last Thing

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class17/figures/final.png) from [PhD Comics](https://phdcomics.com/comics/archive.php?comicid=1531)
