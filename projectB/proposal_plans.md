# Project B Plans

## Revisions Requested (Alphabetical Order of Form Respondent's First Name)

Group | Investigator(s) | Project Title | Time
:-----: | :-------: | :------------ | :-----
4 | [Alan Kiang](alan-kiang) | Predictors of poor mental health and suicide rates in US counties | Mon 2:15 PM
3 | [Kyaw Oo Hla](kyaw-oo-hla) | Predicting Health Status and Premature Death using **County Health Rankings** | Mon 1:45 PM

## No Revisions Requested At This Time (Alphabetical Order of Form Respondent's First Name)

Group | Investigator(s) | Project Title | Time
:-----: | :-------: | :------------ | :-----
5 | [Alex Olejko](alex-olejko) | Comparing objective versus subjective factors predicting educational attainment | Mon 2:15 PM
2 | [Audrey Zhu](audrey-zhu) | Exploring How Songs Get On and Stay On the Billboard Hot 100 | Mon 10 AM
1 | [Kristi Lin-Rahardja](kristi-lin-rahardja) | Influential Factors of Cancer Risk and Mortality Across Mammals | Mon 10 AM

## Kristi Lin-Rahardja

Project 1 | Kristi Lin-Rahardja
-------: | :-------------------
Title | Influential Factors of Cancer Risk and Mortality Across Mammals
Data Source | The data to be used is from [a 2021 Nature paper](https://github.com/OrsolyaVincze/VinczeEtal2021Nature) by Orsolya Vincze, et al titled "Cancer risk across mammals".
Public | Yes
Model 1 | **Should be** A model for a multi-categorical outcome
Outcome 1 | Risk groups were determined based on tertiles to describe "Low", "Mid", and "High" risk of cancer mortality.
RQ 1 | Does a mammal's life expectancy and taxonomical order influence their risk level of cancer mortality in a species?
Model 2 | A weighted linear regression model
Outcome 2 | Adult cancer mortality risk (ranges from 0-1) where I want to down-weight some outlier values
RQ 2 | Do larger animals have a higher cancer mortality risk than smaller animals?
Sample Sizes | 191 for each
Status | **Accepted.** Change the plan for Model 1 as indicated.

## Audrey Zhu

Project 2 | Audrey Zhu
-------: | :-------------------
Title | Exploring How Songs Get On and Stay On the Billboard Hot 100
Data Source | Tidy Tuesday's [Top 100 Billboard data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2021/2021-09-14/readme.md) (2021 Week 38)
Public | Yes
Model 1 | A model for a count outcome
Outcome 1 | Maximum number of consecutive weeks for which a song has stayed on the Billboard Hot 100.
RQ 1 | How well does a song's tempo, valence, and the number of times it had previously been on the Billboard Hot 100 predict the length of its longest stay on the Hot 100?
Model 2 | A logistic model fit using a generalized linear model and logit link
Outcome 2 | Has the song has been on the Billboard Hot 100 more than once?
RQ 2 | How well can a song's energy, speechiness, and length predict whether it will appear on the Billboard Hot 100 more than once?
Sample Sizes | 9017 for each (**probably want to cut that down even beyond just looking at those since 2000**)
Status | **Accepted.** Cut down the sample size, as indicated. How will you assess the number of times a song had "previously" been on the Hot 100 if their first time on the data yields the maximum number of weeks?

## Kyaw Oo Hla



Project 3 | Kyaw Oo Hla
-------: | :-------------------
Title | Predicting Health Status and Premature Death using **County Health Rankings**
Data Source | [County Health Rankings](https://www.countyhealthrankings.org/sites/default/files/media/document/analytic_data2019.csv) (2019)
Public | Yes
Model 1 | A linear model fit using a Bayesian engine
Outcome 1 | "Poor or Fair Health Value" (**which you should describe in additional detail**)
RQ 1 | How well can predict unhealthy score of US by using the poor physical health days, poor mental health days, smoking status, drinking status, and obesity of the people who are living in every county of the US in 2019? (**This needs to be repaired - your research question should more accurately describe your predictors, and should not specify all of the predictors you are planning to use.**)
Model 2 | A logistic model fit using a generalized linear model and logit link (**At least one of your models must be neither linear nor binary logistic.**)
Outcome 2 | "Premature Death Value" variable (**which, again, you should describe in additional detail**) but split into two categories: Low and High (**and you need to specify the cutpoint you are using.**)  
RQ 2 | How well can predict premature death rate of US by using physical inactivity status, obesity status, uninsured rate, unemployment rate, and graduate status of the people who are living in every county of the US in 2019 ? (**Again, this question needs to be repaired. Like your previous question it's not grammatically correct - start with something like "How well can we predict..." and also don't specify a complete set of predictors.**) 
Sample Sizes | 3081 for each
Status | **REVISION REQUIRED.** This proposal needs to be revised. Why, specifically are you using CHR from 2019 rather than some other year? In addition, I want you to demonstrate the ability (in either Model 1 or Model 2) to work with something other than a linear or logistic model. So you'll need to change either Model 1 or Model 2 accordingly. The simplest solution would be to split your planned outcome for Model 2 into four categories, rather than two, and these categories should be of roughly equal size. Then plan to predict the category using an appropriate model for a multi-categorical outcome. Finally, your predictors for Model 1 and Model 2 can overlap, but I want at least two predictors in each model that aren't in the other model if you're using County Health Rankings data. Please resubmit revised outcomes, revised research questions and revised specifications of models for both Model 1 and Model 2 that meet these requirements and address the comments below via email to Dr. Love by **9 PM this Thursday 2022-04-07** using the subject "Revised Project B Plans". Thank you.

## Alan Kiang


Project 4 | Alan Kiang
-------: | :-------------------
Title | Predictors of poor mental health and suicide rates in US counties
Data Source | [County Health Rankings](ttps://www.countyhealthrankings.org/sites/default/files/media/document/2021%20County%20Health%20Rankings%20Data%20-%20v1.xlsx) (**which year(s) - I think 2021, but I shouldn't have to guess?**)
Public | Yes
Model 1 | A linear model fit using a Bayesian engine
Outcome 1 | Average number of poor mental health days per month
RQ 1 | Does the mental health providers to population ratio predict the average number of poor mental health days per month? (**I want you to improve this to indicate what else you'll be adjusting for, or to specify a direction for the effect that you posit is true.**)
Model 2 | A linear model fit using ordinary least squares (**At least one of your models must be neither linear nor binary logistic.**)
Outcome 2 | Number of deaths due to suicide per 100,000 population
RQ 2 | Does the mental health providers to population ratio predict the rate of deaths due to suicide?
Sample Sizes | 3142 for Model 1, 2448 for Model 2
Status | **REVISION REQUIRED.** This proposal needs to be revised. I want you to demonstrate the ability (in either Model 1 or Model 2) to work with something other than a linear or logistic model. The instructions explicitly said that you couldn't run two linear models. So you'll need to change either Model 1 or Model 2 accordingly. Finally, your predictors for Model 1 and Model 2 can overlap and you can use the same *key predictor* if you want, as you imply here, but I want at least two predictors in each model that aren't in the other model if you're using County Health Rankings data. Please resubmit revised outcomes, revised research questions and revised specifications of models for both Model 1 and Model 2 that meet these requirements and address the comments below via email to Dr. Love by **9 PM this Thursday 2022-04-07** using the subject "Revised Project B Plans". Thank you.

## Alex Olejko

Project 5 | Alex Olejko
-------: | :-------------------
Title | Comparing objective versus subjective factors predicting educational attainment
Data Source | [National Longitudinal Study of Adolescent to Adult Health](https://www.icpsr.umich.edu/web/ICPSR/studies/21600/datadocumentation) (Add Health) 1994 - 2018 
Public | Yes
Model 1 | A model for a count outcome
Outcome 1 | Number of years of education completed
RQ 1 | Does educational ambition predict educational attainment above and beyond academic achievement?
Model 2 | A model for a multi-categorical outcome
Outcome 2 | Self-perception of your likelihood of graduating college, while enrolled. Likert 5-category scale (almost no chance, some chance, but probably not, a 50-50 chance, a good chance, almost certain)
RQ 2 | Does mental health predict one's perceptions of the college graduation likelihood above and beyond academic performance?
Sample Sizes | 4191 in Model 1, 4806 in Model 2
Status | **Accepted.** Looks good to me.
