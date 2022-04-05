# Project B Plans

The [Schedule for Project B Presentations](https://github.com/THOMASELOVE/432-2022/blob/main/projectB/schedule.md) is now available. Please review your appointment and make sure there are no issues.

## Revisions Requested for these Projects 

**Revisions are due Thursday 2022-04-07 at 9 PM: see the Status section under your name for more details on what you need to address, and how to submit your revision.**

Group | Investigator(s) | Project Title | Time
:-----: | :-------: | :------------ | :-----
4 | [Alan Kiang](#alan-kiang) | Predictors of poor mental health and suicide rates in US counties | Mon 2:15 PM
7 | [Cerag Oguztuzun and Abhishek Bhardwaj](#cerag-oguztuzun-and-abhishek-bhardwaj) | Exploring County-Level COVID-19 Case Rates | Tue 9 AM
8 | [Gen Li and Jiayue Yang](#gen-li-and-jiayue-yang) | A study about smoking and drinking alcohol and several potential risks | Tue 9 AM
3 | [Kyaw Oo Hla](#kyaw-oo-hla) | Predicting Health Status and Premature Death using **County Health Rankings** | Mon 1:45 PM
6 | [Olivia Wilcox](#olivia-wilcox) | Assessing the Average Birth Weights of Babies Born in 2019 | Mon 2:15 PM

## Project Proposals Accepted by Dr. Love 

**Please review my comments and descriptions associated with your project closely. Substantial changes are bolded.**

Group | Investigator(s) | Project Title | Time
:-----: | :-------: | :------------ | :-----
5 | [Alex Olejko](#alex-olejko) | Comparing objective versus subjective factors predicting educational attainment | Mon 2:15 PM
2 | [Audrey Zhu](#audrey-zhu) | Exploring How Songs Get On and Stay On the Billboard Hot 100 | Mon 10 AM
9 | [Ben Kramer and Jacqueline Shaia](#ben-kramer-and-jacqueline-shaia) | Which Counties Brew the Best Beer? Factors Associated with a Successful Brewery | Tue 11:35 AM
1 | [Kristi Lin-Rahardja](#kristi-lin-rahardja) | Influential Factors of Cancer Risk and Mortality Across Mammals | Mon 10 AM
10 | [Michael Douglass](#michael-douglass) | International Violence & Conflict (1980-2000) | Tue 12 Noon
11 | [Norman Luc](#norman-luc) | Predicting Explosive Scoring and Offensive Efficiency in the '21-'22 NBA Season | Tue 12:25 PM

## Not Yet Sorted

Group | Investigator(s) | Project Title | Time
:-----: | :-------: | :------------ | :-----
12 | [Paulameena Shultes](#paulameena-shultes) | Relationships between Tuition, Ethnic Composition, and Types of 4-Year Colleges | Tue 1:20 PM
13 | [Tyler Petrie](#tyler-petrie) | Predicting character class and moral alignment in Dungeons and Dragons | Tue 1:45 PM
14 | [Jay Wei](#jay-wei) | Predicting Bench Press Contests Winnings with sex, bodyweight, and other factors | Tue 2:15 PM
15 | [Chris Jones](#chris-jones) | Do negative influences/substance abuse impact income and mental status? | Tue 2:15 PM
16 | [Sneha Yamsani and Himani Sancheti](#sneha-yamsani-and-himani-sancheti) | Understanding Volcano Types and Populations Around Volcanoes | Tue 2:15 PM
17 | [Jacob Rich and Steven Mayher](#jacob-rich-and-steven-mayher) | Just Say No: The Effect of Increasing Drug-Related Arrests On Racial Equity | Tue 3:30 PM
18 | [Rock Lim](#rock-lim) | Gender-dependent spending and revenue in college sports | Tue 3:55 PM
19 | [Harrison Lindley and Sarah Nock](#harrison-lindley-and-sarah-nock) | Predicting geographic origin of coffee using cup quality and production metrics | Thu 12 Noon
20 | [Ziyin Zhao](#ziyin-zhao) | Predict kidney damage by gender, binge drinking, and tobacco exposure | Thu 12:20 PM
21 | [Ava Fan](#ava-fan) | Racial Differences in Post-Secondary Education in the United States | Thu 12:40 PM
22 | [David Selvaraj](#david-selvaraj) | Relating Sugar-Sweetened Beverages, Area Deprivation and Dental Caries | Thu 1:10 PM
23 | [Ria Tilve](#ria-tilve) | Using Body Measures Predict Exercise Levels and Arthritis in the MrOS Study | Thu 1:10 PM
24 | [Kiran Desai and Grace Armstrong](#kiran-desai-and-grace-armstrong) | The Impact of Social Independence on Health in Mexican American Elderly Adults | Thu 1:10 PM
25 | [Siddharth Dugar](#siddharth-dugar) | Association of Left ventricle systolic velocity to ICU mortality in Sepsis | Thu 2:15:PM
26 | [Carly Rose and Diya Yang](#carly-rose-and-diya-yang) | Exploring Health-Related Factors and Physical Health Among US Residents | Thu 2:15 PM
27 | [Alise Carlson](#alise-carlson) | Exploring Factors Associated with Successful Survivor Players | Thu 2:15 PM
28 | [Makaela Mews](#makaela-mews) | Predictive value of sex and basic labs on visceral fat to trunk lean mass ratio | Thu 3:40 PM
29 | [Aaron Fletcher](#aaron-fletcher) | Exploring Common Observations in Outpatient Dietetics | Thu 4:00 PM
30 | [Anushree Iyengar](#anushree-iyengar) | Factors Associated with Cognitive Issues Among the Aging | Thu 4:25 PM
31 | [Katie Heinzinger](#katie-heinzinger) | Predicting Dog Breed Rankings and Traits | Thu 4:45 PM

## Kristi Lin-Rahardja

Project 1 | Kristi Lin-Rahardja
-------: | :-------------------
Title | Influential Factors of Cancer Risk and Mortality Across Mammals
Source | The data to be used is from [a 2021 Nature paper](https://github.com/OrsolyaVincze/VinczeEtal2021Nature) by Orsolya Vincze, et al titled "Cancer risk across mammals".
Public | Yes
Model 1 | **Should be** A model for a multi-categorical outcome
Out 1 | Risk groups were determined based on tertiles to describe "Low", "Mid", and "High" risk of cancer mortality.
RQ 1 | Does a mammal's life expectancy and taxonomical order influence their risk level of cancer mortality in a species?
Model 2 | A weighted linear regression model
Out 2 | Adult cancer mortality risk (ranges from 0-1) where I want to down-weight some outlier values
RQ 2 | Do larger animals have a higher cancer mortality risk than smaller animals?
Samples | 191 for each
Status | **Accepted.** Excellent start. Change the plan for Model 1 as indicated.

## Audrey Zhu

Project 2 | Audrey Zhu
-------: | :-------------------
Title | Exploring How Songs Get On and Stay On the Billboard Hot 100
Source | Tidy Tuesday's [Top 100 Billboard data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2021/2021-09-14/readme.md) (2021 Week 38)
Public | Yes
Model 1 | A model for a count outcome
Out 1 | Maximum number of consecutive weeks for which a song has stayed on the Billboard Hot 100.
RQ 1 | How well does a song's tempo, valence, and the number of times it had previously been on the Billboard Hot 100 predict the length of its longest stay on the Hot 100?
Model 2 | A logistic model fit using a generalized linear model and logit link
Out 2 | Has the song has been on the Billboard Hot 100 more than once?
RQ 2 | How well can a song's energy, speechiness, and length predict whether it will appear on the Billboard Hot 100 more than once?
Samples | 9017 for each (**probably want to cut that down even beyond just looking at those since 2000**)
Status | **Accepted.** Excellent start. Cut down the sample size, as indicated. How will you assess the number of times a song had "previously" been on the Hot 100 if their first time on the data yields the maximum number of weeks?

## Kyaw Oo Hla

Project 3 | Kyaw Oo Hla
-------: | :-------------------
Title | Predicting Health Status and Premature Death using **County Health Rankings** (**I have improved your title. Please use this one going forward.**)
Source | [County Health Rankings](https://www.countyhealthrankings.org/sites/default/files/media/document/analytic_data2019.csv) (2019)
Public | Yes
Model 1 | A linear model fit using a Bayesian engine
Out 1 | "Poor or Fair Health Value" (**which you should describe in additional detail**)
RQ 1 | How well can predict unhealthy score of US by using the poor physical health days, poor mental health days, smoking status, drinking status, and obesity of the people who are living in every county of the US in 2019? (**This needs to be repaired - your research question should more accurately describe your predictors, and should not specify all of the predictors you are planning to use.**)
Model 2 | A logistic model fit using a generalized linear model and logit link (**At least one of your models must be neither linear nor binary logistic.**)
Out 2 | "Premature Death Value" variable (**which, again, you should describe in additional detail**) but split into two categories: Low and High (**and you need to specify the cutpoint you are using.**)  
RQ 2 | How well can predict premature death rate of US by using physical inactivity status, obesity status, uninsured rate, unemployment rate, and graduate status of the people who are living in every county of the US in 2019 ? (**Again, this question needs to be repaired. Like your previous question it's not grammatically correct - start with something like "How well can we predict..." and also don't specify a complete set of predictors.**) 
Samples | 3081 for each
Status | **REVISION REQUIRED.** This proposal needs to be revised. Why, specifically are you using CHR from 2019 rather than some other year? In addition, I want you to demonstrate the ability (in either Model 1 or Model 2) to work with something other than a linear or logistic model. So you'll need to change either Model 1 or Model 2 accordingly. The simplest solution would be to split your planned outcome for Model 2 into four categories, rather than two, and these categories should be of roughly equal size. Then plan to predict the category using an appropriate model for a multi-categorical outcome. Finally, your predictors for Model 1 and Model 2 can overlap, but I want at least two predictors in each model that aren't in the other model if you're using County Health Rankings data. Please resubmit revised outcomes, revised research questions and revised specifications of models for both Model 1 and Model 2 that meet these requirements and address the comments below via email to Dr. Love by **9 PM this Thursday 2022-04-07** using the subject "Revised Project B Plans". Thank you.

## Alan Kiang

Project 4 | Alan Kiang
-------: | :-------------------
Title | Predictors of poor mental health and suicide rates in US counties
Source | [County Health Rankings](https://www.countyhealthrankings.org/sites/default/files/media/document/2021%20County%20Health%20Rankings%20Data%20-%20v1.xlsx) (**which year(s) - I think 2021, but I shouldn't have to guess?**)
Public | Yes
Model 1 | A linear model fit using a Bayesian engine
Out 1 | Average number of poor mental health days per month
RQ 1 | Does the mental health providers to population ratio predict the average number of poor mental health days per month? (**I want you to improve this to indicate what else you'll be adjusting for, or to specify a direction for the effect that you posit is true.**)
Model 2 | A linear model fit using ordinary least squares (**At least one of your models must be neither linear nor binary logistic.**)
Out 2 | Number of deaths due to suicide per 100,000 population
RQ 2 | Does the mental health providers to population ratio predict the rate of deaths due to suicide?
Samples | 3142 for Model 1, 2448 for Model 2
Status | **REVISION REQUIRED.** This proposal needs to be revised. I want you to demonstrate the ability (in either Model 1 or Model 2) to work with something other than a linear or logistic model. The instructions explicitly said that you couldn't run two linear models. So you'll need to change either Model 1 or Model 2 accordingly. Finally, your predictors for Model 1 and Model 2 can overlap and you can use the same *key predictor* if you want, as you imply here, but I want at least two predictors in each model that aren't in the other model if you're using County Health Rankings data. Please resubmit revised outcomes, revised research questions and revised specifications of models for both Model 1 and Model 2 that meet these requirements and address the comments below via email to Dr. Love by **9 PM this Thursday 2022-04-07** using the subject "Revised Project B Plans". Thank you.

## Alex Olejko

Project 5 | Alex Olejko
-------: | :-------------------
Title | Comparing objective versus subjective factors predicting educational attainment
Source | [National Longitudinal Study of Adolescent to Adult Health](https://www.icpsr.umich.edu/web/ICPSR/studies/21600/datadocumentation) (Add Health) 1994 - 2018 
Public | Yes
Model 1 | A model for a count outcome
Out 1 | Number of years of education completed
RQ 1 | Does educational ambition predict educational attainment above and beyond academic achievement?
Model 2 | A model for a multi-categorical outcome
Out 2 | Self-perception of your likelihood of graduating college, while enrolled. Likert 5-category scale (almost no chance, some chance, but probably not, a 50-50 chance, a good chance, almost certain)
RQ 2 | Does mental health predict one's perceptions of the college graduation likelihood above and beyond academic performance?
Samples | 4191 in Model 1, 4806 in Model 2
Status | **Accepted.** Excellent start.

## Olivia Wilcox

Project 6 | Olivia Wilcox
-------: | :-------------------
Title | Assessing the Average Birth Weights of Babies Born in 2019
Source | CDC Wonder data, specifically the [Natality, 2019 expanded data](https://wonder.cdc.gov/natality-expanded-current.html) and combining this with County Health Rankings (2019)
Public | Yes
Model 1 | A linear model fit using a Bayesian engine
Out 1 | Average birth weight in grams for babies born in a county. 
RQ 1 | How accurately can I predict the **mean** birth weight (grams) of babies born in 2019 at a county level after adjusting for insurance status,  unemployment, ratio of primary care providers, and median household income?
Model 2 | A model for a count outcome
Out 2 | Mean number of pre-natal visits mothers in each county attended.
RQ 2 | What is the relationship between median birth weight of babies born in 2019 and the number of prenatal visits the mother attended?
Samples | 626 for each (how were these selected?)
Status | **REVISION REQUIRED.** This proposal needs to be revised. Your link for County Health Rankings was for the 2021 measures. Be sure to get the correct measures for 2019. Your first research question had median, but you mean mean, I think. The main problem, though, is with model 2. I'd love for you to have a count outcome model, but while the number of visits for any particular mom can only be a whole number, and thus is appropriately modeled with a count, that's not true for the mean across all moms in the county, so I don't see what you've described as being a count outcome in model 2. You do need something other than a linear or (binary) logistic model in Outcome 2, but you'll have to convince me that county-level means are counts. Please resubmit revised outcomes, revised research questions and revised specifications of models for both Model 1 and Model 2 that meet these requirements and address the comments below via email to Dr. Love by **9 PM this Thursday 2022-04-07** using the subject "Revised Project B Plans". Thank you.

## Cerag Oguztuzun and Abhishek Bhardwaj

Project 7 | Cerag Oguztuzun and Abhishek Bhardwaj
-------: | :-------------------
Title | **Exploring County-Level COVID-19 Case Rates** (**I have improved your title. Please use this one going forward.**)
Source | [County Health Rankings](https://www.countyhealthrankings.org/explore-health-rankings/rankings-data-documentation) data (2021) and  NY Times' [Coronavirus (Covid-19) Data in the United States](https://github.com/nytimes/covid-19-data) from 2022.
Public | Yes
Model 1 | A model for a multi-categorical outcome
Out 1 | We plan to categorize death numbers into 3 categories as High, Medium and Low which will indicate the Covid19 related death rate for each county in the US. (**I encourage you instead to divide into 4 categories with roughly equal numbers of counties in each.**)
RQ 1 | Does flu vaccination predict lower covid19 deaths?
Model 2 | A model for a count outcome
Out 2 | A masking standard will be created by finding some thresholds that will act as a guideline to determine which counties meet most of the masking standards. We will then be able to understand how masking standards relate to health care access in a population.
RQ 2 | Do counties with higher access to primary care physicians meet standardized mask guidelines?
Samples | 2821 for Model 1, 
Status | **REVISION REQUIRED.** This proposal needs to be revised. You're going to need to flesh out the details of Outcome 1 and Outcome 2 more completely. In Outcome 1, how are you calculating death rates, and over what period of time? In Outcome 2, I need to know how many thresholds you're going to identify (so I know what the maximum count will be) and you need to be able to demonstrate that you will be able to get the data you need from these sources. I can't accept "will be created" - you have to create it. The only data I'm sure they have is survey responses related to frequency of masking, and that's not going to lead to what I think you'd need. 

## Gen Li and Jiayue Yang

Project 8 | Gen Li and Jiayue Yang
-------: | :-------------------
Title | A study about smoking and drinking alcohol and several potential risks (**new title needed**)
Source | [NHANES 2017-2018](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?BeginYear=2017) 
Public | Yes
Model 1 | A model for a count outcome
Out 1 |  Frequency of drinking (variable ALQ121) is a categorical variable with 11 levels but we can build a new outcome as the level of frequency of drinking. (**this won't work - see below.**)
RQ 1 | Which potential factors will make people drink more? / What's the feature for people drink more? (**revision needed**)
Model 2 | A model for a multi-categorical outcome
Out 2 | Smoking status (variable SMQ040) with three levels: Never smoke, smoking every day and smoking some days.
RQ 2 | What kind of people will tend to smoke? / What's the feature for people smoking? (**revision needed**)
Samples | 2232 for Model 1, 4545 for Model 2
Status |  **REVISION REQUIRED.** You need a new title that is much more specific about what you're doing and does not include the words "A study about". Why are you using NHANES 2017-18 instead of 2019-20? "What's the feature for..." isn't an acceptable construction for a research question. Try something like "How well can we predict frequency of drinking using ... (list key variables)?" I'm OK with Outcome 2, I think, but in Outcome 1, you will need to specify how you will use the data in ALQ121 to create a count variable. I'm virtually certain that you cannot do so. You could, on the other hand, use two variables together (ALQ121 (to identify the zeros) and then ALQ130 (Average number of drinks per day over the past 12 months)) to obtain a count, treating anyone with a 15 on ALQ121 as having a count of 15.

## Ben Kramer and Jacqueline Shaia

Project 9 | Ben Kramer and Jacqueline Shaia
-------: | :-------------------
Title | Which Counties Brew the Best Beer? Factors Associated with a Successful Brewery (**I prefer the title in this order.**)
Source | 1) TidyTuesday 2020 - [Great American Beer Festival](https://www.greatamericanbeerfestival.com/the-competition/winners/)  (Available via TidyTuesday Package) 2) [US Cities Data](https://simplemaps.com/data/us-cities), Updated 2021  3) [County Health Rankings](https://www.countyhealthrankings.org/explore-health-rankings/rankings-data-documentation) (2020).  
Public | Yes
Model 1 | A model for a multi-categorical outcome
Out 1 |  Medal (bronze, silver, gold) most often won by the county (among counties who have won at least one medal) in the Great American Beer Festival.
RQ 1 | What county characteristics predict how well an award winning beer will do in the Great American Beer Festival?
Model 2 | A logistic model fit using a generalized linear model and logit link
Out 2 | County has won or not won an award. 
RQ 2 | What county characteristics predict if it will be a winning county at the Great American Beer Festival?
Samples | 467 for model 1, 3084 for model 2
Status | **Accepted.** Excellent start.

## Michael Douglass

Project 10 | Michael Douglass
-------: | :-------------------
Title | International Violence & Conflict (1980-2000)
Source | (1) Brecher, Michael, Jonathan Wilkenfeld, Kyle Beardsley, Patrick James and David Quinn (2021). [International Crisis Behavior Data Codebook, Version 14](http://sites.duke.edu/icbdata/data-collections/). (2) Khoury, Colin K; Bjorkman, Anne D; Dempewolf, Hannes; Ramirez Villegas, Julian; Guarino, Luigi; Jarvis, Andy; Rieseberg, Loren H; Struik, Paul C, 2015, "[Replication Data for: Increasing homogeneity in global food supplies and the implications for food security](https://doi.org/10.7910/DVN/HYOWIC)", Harvard Dataverse, V1 (3) [Sustainable Development Report](https://dashboards.sdgindex.org/downloads) from the UN's Statistics Division. 
Public | Yes
Model 1 | A model for a count outcome
Out 1 |  The number of violent conflicts the country was involved in from the years 1980 to 2000, as derived from the ICB Project (Datasource 1).
RQ 1 | Can I predict a country's **involvement in conflict** based on a static look at factors that describe the country in a global context?
Model 2 | A model for a multi-categorical outcome
Out 2 | The status of the country's effort to achieve Goal 16 (Promote peaceful and inclusive societies for sustainable development, provide access to justice for all and build effective, accountable and inclusive institutions at all levels) of the UN's Sustainable Development Goals. Categories are: Goal Achievement, Challenges remain, Significant challenges, and Major challenges. (**as of what date?**)
RQ 2 | Does a history of violent conflict predict a nation's current efforts toward peace?
Samples | 152 for each.
Status | **Accepted.** Excellent start. In RQ 1, note my small change. As of what date, for outcome 2? 

## Norman Luc

Project 11 | Norman Luc
-------: | :-------------------
Title | Predicting Explosive Scoring and Offensive Efficiency in the '21-'22 NBA Season
Source | 2021-2022 NBA regular season data from [NBA Player Statistics](https://www.nba.com/stats/players/) and [Basketball Reference](https://www.basketball-reference.com/)
Public | Yes
Model 1 | A model for a count outcome
Out 1 | My count outcome is the number of 20 points games by a player as a "traditional" measure of scoring output.  
RQ 1 | How does an NBA player's shooting rate and percentage from each area of the court predict the number of 20 point games in the 2021-2022 season?
Model 2 | A linear model fit using ordinary least squares
Out 2 | Offensive Win Share per 48 minutes is my linear model outcome. This is a catch-all measurement of offensive efficiency, normalized to the amount of time played.
RQ 2 | How does an NBA player's shooting rate and percentage from each area of the court predict their Offensive Win Shares per 48 minutes in the 2021-2022 season?
Samples | 598 in Model 1, 196 in Model 2
Status | **Accepted.** Excellent start. Of course, you won't have the whole season's data yet, since the regular season isn't over until April 10. Do you propose to wait until then to finalize your data? Should you restrict Outcome 1 to players who played at least a certain number of minutes in the season or to those who started X games, or even to the players included in Outcome 2's model or something like that? Otherwise, won't you have a tremendous number of uninteresting zeros and ones among players who play infrequently?

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  

## Template

Project X | 
-------: | :-------------------
Title | 
Source | 
Public | 
Model 1 | 
Out 1 |  
RQ 1 | 
Model 2 | 
Out 2 | 
RQ 2 | 
Samples | 
Status |  
