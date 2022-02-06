# 432 Class 11: 2022-02-15

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides: [PDF version](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class11/432_2022_slides11.pdf), as well as [R Markdown code](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class11/432_2022_slides11.Rmd). 
- All 432 classes are video-recorded, and archived on [Canvas](https://canvas.case.edu). Links to all recordings are on our Shared Google Drive.

## More To Come

1. If you haven't yet read this [Important Note from Dr. Love on Effect Size and Interpreting Effect Sizes](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class09/effects_note.pdf) first mentioned [in Class 09](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class09#important-note-from-dr-love-on-effect-size-and-interpreting-effect-sizes), then I encourage you to do so.
2. More to come.

## The `tidymodels` packages

Today we're introducing the `tidymodels` set of packages. **Note** Rather than creating a set of materials (in Chapters 15-17 of the Course Notes) to cover tidymodels topics, I'm going to instead point you to the following excellent external resources for learning more.

1. The [tidymodels website](https://www.tidymodels.org/), in particular the [Get Started](https://www.tidymodels.org/start/) tutorials, and the [Learn section](https://www.tidymodels.org/learn/), which has additional information on performing analyses, tuning models, and developing custom approaches, among other things.
2. Max Kuhn and Julia Silge's book [Tidy Modeling with R](https://www.tmwr.org/) which has been my main way to learn about these approaches.
3. For videos with great `tidymodels` examples, try [Julia Silge's YouTube page](https://www.youtube.com/c/JuliaSilge/videos). I'll highlight...
    - [Model student debt inequality with tidymodels](https://www.youtube.com/watch?v=4ayOjlRv8bA) from 2021-02-12
    - [Get started with tidymodels and classification of penguin data](https://www.youtube.com/watch?v=z57i2GVcdww) from 2020-07-28
    - [Predict astronauts' mission duration with tidymodels and bootstrap aggregation](https://www.youtube.com/watch?v=rzfTA3xi-W0) from 2020-07-15
    - [Data preprocessing and resampling using tidymodels](https://www.youtube.com/watch?v=s3TkvZM60iU) from 2020-03-10
    - [Get started with tidymodels using vaccination rate data](https://www.youtube.com/watch?v=E2Ld3QdXYZo) from 2020-02-25
4. You may be interested in Bruna Wundervald's [An introduction to the tidymodels package](http://brunaw.com/tidymodels-webinar/slides/slides.html#1) slides, too.

## A few thoughts on the adjusted R-square statistic

In linear regression work, the "adjusted R-square" statistic attempts to use the same data to fit the model and evaluate it, through applying a penalty based on the number of coefficient estimates that need to be developed and the sample size. This summary is somewhat interesting, and has some value occasionally. However, I usually avoid placing much weight on summary statistic "adjusted R-square" to describe the predictive quality of a model, in favor of a validated R-square statistic, which might include:

- the "optimism-corrected" results of a bootstrap validation (as in `validate` for an `ols` fit)
- the r-square value observed when applying a model fit in a training sample to holdout data in a test sample
- some other cross-validated r-square statistic, as can be developed using the `rsample` and `yardstick` packages (see, for example, Chapters 9 and 10 in [Tidy Modeling with R](https://www.tmwr.org/).

So my main point is that I wouldn't use adjusted R-square much (if at all) in linear regression, instead using a better method to assess predictive power in linear regression.
