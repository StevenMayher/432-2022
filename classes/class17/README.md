# 432 Class 17: 2022-03-17

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class17/432_2022_slides17.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class17/432_2022_slides17.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

Source: https://twitter.com/jmwooldridge/status/1501157439726575616

## Time to Event Data

Materials on time-to-event outcomes are found in Chapters 22-24 of our [Course Notes](https://thomaselove.github.io/432-notes/). This is a very brief introduction to the topic. We offer a full-semester course (PQHS 435) every spring in Survival Analysis, which goes into much more detail.

- In today's slides, I make reference to [this PDF guide by David Diez on Survival Analysis in R from OpenIntro](https://www.openintro.org/book/surv_in_r/), which I also recommend, and which provides the `OISurv` package.
- I strongly recommend you look at the (7-minute) video "[Survival Curves: Showing More by Showing Less](https://www.youtube.com/watch?v=EoIB_Obddrk)" on YouTube posted by Frank Harrell, which explains the logic behind several tools in the `rms` package which let you interact with a graph and a non-parametric survival function which saves a little more information than the usual Kaplan-Meier plot.
- The **survminer** package is where you can find the **ggsurvplot** approach we'll take today. 
- For more customization of plots like the Kaplan-Meier curves we'll build today, visit https://rpkgs.datanovia.com/survminer/ or https://github.com/kassambara/survminer/. 
    - For instance, they provide a [PDF cheat sheet](https://rpkgs.datanovia.com/survminer/survminer_cheatsheet.pdf) which was pretty helpful to me.
- You may also be interested in learning more about concordance in survival analysis (and in general) [from this vignette](https://cran.r-project.org/web/packages/survival/vignettes/concordance.pdf) (pdf).

## Some Advice on Naming Things

Naming things is hard. [Jenny Bryan has you covered](https://speakerdeck.com/jennybc/how-to-name-files). The three principles are:

- machine readable
- human readable
- play well with default ordering

All good tips for R data frame names as well. I'll add 

- don't name tibbles things that are also data frames or functions or other things in R
- don't name tibbles things that make no sense in context
- 8 characters is usually enough for a tibble name that you'll use often

Here were the names of the main tibbles that people built for Project A...

- `a_sample`, `analysis_data`, `brfss_2`, `chr_2021`, `climbers_train1`
- `coffee_ratings`, `dat_ads`, `data_clean`, `final_A`, `final_data`
- `FinalA`, `gss2021_423`, `hotel_final`, `hrs`, `hrsdata`
- `infant_mort_sample`, `jobloss`, `llcp`, `main_df`, `New8`
- `nhsda1999_oxy`, `place`, `places`, `projectA`, `split_tidy_data`
- `starbucks`, and `starbucks` again, `tidy`, `tidy_tibble`, `tidy_tracks`, `tidydata`
- `wine1` and `wine2`

