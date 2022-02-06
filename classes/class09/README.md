# 432 Class 09: 2022-02-08

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/432_2022_slides09.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/432_2022_slides09.Rmd). 
    - We'll begin today's class on Slide 62 from the [Class 07](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class07) slides (available [here in PDF](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/432_2022_slides07.pdf)).
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/figures/harrell_tw.png)

## Announcements (to come)

1. I updated the [Course Notes](https://thomaselove.github.io/432-notes/), mostly fixing typos, so be sure you're looking at the 2022 edition. Any mistakes you find there can be reported to us through Piazza.
2. [Feedback on Project A proposals is here](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/proposals/feedback1.md), along with my comments on [your titles](https://github.com/THOMASELOVE/432-2022/blob/main/projectA/proposals/titles.md).
    - Those of you needing to submit a revision, please submit your revised proposal, including R Markdown, HTML, raw data, and Rds (cleaned data) to Canvas in the **Project A Proposal Revision** assignment by 9 PM tonight (Tuesday 2022-02-08.)
3. There is a Minute Paper after Class 09. **Details to come**.
4. An **Answer Sketch for Lab 2** should be available by class time.
5. Several good essays from **Lab 1 Question 3** (about Jeff Leek's book) are now posted to our Shared Google Drive in the **Lab 01 Materials** section, and also as separate notes on Piazza. Please feel encouraged to add to the discussion of these pieces on Piazza, if you have any thoughts.
6. Thanks to those of you who participated in the poll on Piazza about Chapter 2 of *The Signal and the Noise*. You should be able to see the results there now, in the `silver_signal_noise` folder.
    - I asked which of the following principles outlined in Chapter 2 of the Signal and the Noise seems most important to you as you think about improving your own ability to forecast, meaning both (1) use data from the past to make more effective forecasts about what will happen in the future, and (2) learn from the forecasts made by others.
    - Today's Forecast is the First Forecast of the Rest of Your Life was chosen by 19 people (46% of respondents)
    - Think Probabilistically was chosen by 16 people (39% of respondents)
    - Look for Consensus was chosen by the remaining 6 respondents (15%)
    - Several people were good enough to add some thoughts in the discussion below. Thank you very much for your insight.

## Important Note from Dr. Love on Effect Size and Interpreting Effect Sizes

I [built a description of effect sizes and how to discuss them](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/effects_note.pdf). 

- I strongly encourage you to read this document over the next couple of weeks. I think it will help you in several ways, most especially for Quiz 1, Lab 3, and Project A. 
- If you want to see the R Markdown file I used to generate this result, [here it is](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/effects_note.Rmd). The small data set I used to fix ideas is in [today's data folder](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class09/data).
- For more on these sorts of handouts (popularized by Edward Tufte) see [RStudio's implementation](https://rstudio.github.io/tufte/)

## One Last Thing

I'll link to an interesting presentation of some survey results on nearly 4000 science and engineering PhDs reported by Maggie Kuo and Jia You in *Science* for 2017-11-27, entitled [Explore the skills that can open career doors after your doctoral training](https://www.sciencemag.org/careers/2017/11/explore-skills-can-open-career-doors-after-your-doctoral-training). 

- A series of what are called [radar charts](https://en.wikipedia.org/wiki/Radar_chart) (also known as spider charts or web charts) illustrate how well PhD training prepares you for a job.
- Separate charts describe technical skills, then interpersonal skills and then day-to-day skills.
- The three images I've clipped below describe results across all sectors, but in [the actual presentation](https://www.sciencemag.org/careers/2017/11/explore-skills-can-open-career-doors-after-your-doctoral-training), you can look at specific subgroups including several types of research positions, consulting, scientific writing, teaching, and others.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/figures/phd_fig1.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/figures/phd_fig2.png)
![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/figures/phd_fig3.png)

- Interested in drawing charts like these in R? Check out [Beautiful Radar Charts in R using the fmsb and ggradar packages](https://www.datanovia.com/en/blog/beautiful-radar-chart-in-r-using-fmsb-and-ggplot-packages/) at datanovia.com.
