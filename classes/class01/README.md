# 432 Class 01: 2022-01-11

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2022/tree/main/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

## Materials for Today's Class

- Today's Slides are [available in PDF](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/432_2022_slides01.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/432_2022_slides01.Rmd).
- All 432 Zoom classes are video-recorded, and the recordings will be archived in the Modules, and Echo 360 sections of [Canvas](https://canvas.case.edu).
- **BONUS video** I pre-recorded a 9-minute video walking through (fairly quickly) the development of the Bradley example in R Studio, anticipating that I might not get to it today in class. This is actually a recording I made in 2021, so it uses an older version of R, but is otherwise correct.
    - You'll find that recording on our Shared Google Drive (log into Google with your CWRU account).
    - The Shared Drive is called *432 Spring 2022 Dr Love and Students*. Inside that Drive, you should see a folder called *432 Spring 2022 Bonus Videos*. 

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/figures/lowndes_tidy_tw.png)

- Read [the entire illustrated series about tidy data here](https://twitter.com/juliesquid/status/1315710359404113920). 
- `@juliesquid` and `@allison_horst` are great people to follow on Twitter. 

## Logistics and Reminders

1. You should have received an email from me in the last 2-3 days with the subject heading "**PQHS / CRSP / MPHP 432 begins Tuesday at 1 PM**" 
    - If you have this email, please attend to what it asks you to do (register for the Zoom sessions, take the Welcome to 432 survey, buy two books (and read the book by Leek) and get started updating/installing R and R Studio). 
    - If you don't have this email, please let me know that via email to **Thomas dot Love at case dot edu** now.
2. If you haven't taken the Welcome to 432 survey already, please [do so today](https://bit.ly/432-2022-welcome-survey).
    - Thanks to the 34 of you who've already completed the survey as of 12:15 this afternoon!
3. Lab 01 will be posted soon and is due Monday 2022-01-24 at 9 PM.
    - To do this Lab, you'll need to have [R and RStudio up and running for you](https://thomaselove.github.io/432/software_install.html), and [download the data from our Data site](https://thomaselove.github.io/432/data_index.html).
4. Please read the [Syllabus](https://thomaselove.github.io/432-2022-syllabus/) and familiarize yourself with the [Course Website](https://thomaselove.github.io/432), the Shared Google Drive (which you can see from your Google CWRU account), [Piazza](https://piazza.com/case/spring2022/pqhs432) (be sure you can log in to this tool) and [Canvas](https://canvas.case.edu/) before Thursday's class so that if you have any questions or problems getting started, we can settle them quickly.
    - Questions should be posted to Piazza in the folder that suits them best. Use the "general_miscellaneous" folder when you're not sure where to put something.
    - I encourage you to change the default Piazza settings so that you receive email notifications either every 12 or 24 hours.
    - If you have an individual concern you want to raise with Dr. Love, email him at **Thomas dot Love at case dot edu**.
5. TA office hours will begin on Monday 2022-01-17, and we'll provide you with a detailed schedule and all the information you'll need to join those hours as soon as possible. All TA office hours will be given using Zoom.
    - The schedule will appear on [the Course Calendar](https://thomaselove.github.io/432/calendar.html#TA_Office_Hours), and in the [Contact Us](https://thomaselove.github.io/432/contact.html) menu on the website, as well as on our Shared Google Drive.
    - Zoom information for TA office hours will be found in the [Announcements section of Canvas](https://canvas.case.edu/), and in our Shared Google Drive.
6. By next Tuesday (2022-01-14), we'll expect you to have:
    - read the (short) book by Jeff Leek entitled [How To Be a Modern Scientist](https://leanpub.com/modernscientist), available as an e-book at Leanpub for a suggested $10.
    - obtained a copy of Nate Silver's The Signal and the Noise, which we'll also be reading this semester
    - looked over the entire syllabus and web site, and accomplished the things specified there.
7. You might want to take a look at the [Glossary of Statistical Terms](https://hbiostat.org/doc/glossary.pdf) (pdf) compiled by Frank Harrell and colleagues. 
    - This week, we will tacitly assume you know, for example, what the following terms mean: binary variable, case-control study, categorical variable, comparative trial, confidence limits, continuous variable, data science, dummy variable, estimate, goodness of fit, inter-quartile range, mean, median, nonparametric estimator, nonparametric tests, normal distribution, null hypothesis, observational study, one-sided test, p-value, parametric test, percentile, predictor, probability, quartiles, random error, random sample, rate, replication, risk, significance level, standard deviation, standard error, two-sided test, Type I error, variance.
    - If any of these terms seem unfamiliar, read up on them. If that's not too overwhelming, then glance through the remainder of the list and find a few more that interest you, and read those closely.
8. There is no [Minute Paper](https://github.com/THOMASELOVE/432-2022/tree/main/minute) this week. Our first Minute Paper is due next Wednesday 2022-01-19. If you have comments or questions about the class, ask them on Piazza, or in TA office hours (starting Monday) or before/after class, or in the chat, etc. We want to hear from you!
9. The final word on all deadlines is the [Course Calendar](https://thomaselove.github.io/432/calendar.html). All deliverables for the entire semester are listed.
10. I want to remind you of the University's resources to help you that are listed in [Section 15 of our syllabus](https://thomaselove.github.io/432-2021-syllabus/university-resources-for-student-support.html), especially the newly available [CWRU Care 24/7 Mental Telehealth for Students](https://timely.md/faq/cwrucare/) program.

### Materials for the Bradley et al. Table 1 example

Here are the materials I'll refer to in discussing the development of a Table 1 for the Bradley example. [Chapter 1 in the Course Notes](https://thomaselove.github.io/432-notes/building-table-1.html) covers the topic of building a Table 1 far more extensively, with two detailed examples. Those notes should be helpful for doing the Table 1 work required in Lab 01.

- **BONUS video** In 2021, I pre-recorded a 9-minute video walking through (fairly quickly) the development of the Bradley example in R Studio, anticipating that I might not get to it in class. You'll find the recording on our Shared Google Drive (log into Google with your CWRU account).

You'll also find:

- the [`bradley.csv`](https://github.com/THOMASELOVE/432-2022/tree/main/classes/class01/data) data file is in the data folder above (click **Raw** to download), and is also available on [our 432-data page](https://github.com/THOMASELOVE/432-data) for general downloads.
- [`bradley_table1.Rmd`](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/bradley_table1.Rmd) is the R Markdown script. Click **Raw** to download it.
- [`bradley_table1.md`](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/bradley_table1.md) shows the results (on github) of running that R Markdown script
- [`bradley_table1_result.csv`](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/bradley_table1_result.csv) is the table generated by that R Markdown script. Again, click **Raw** to download it.
- The original source is Steven M. Bradley, Joleen A. Borgerding, G. Blake Wood, et al. [Incidence, Risk Factors, and Outcomes Associated With In-Hospital Acute Myocardial Infarction](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2720923) *JAMA Netw Open* 2019; 2(1): e187348. doi:10.1001/jamanetworkopen.2018.7348.
- [JAMA Table Creation Instructions](https://jama.jamanetwork.com/data/ifora-forms/jama/tablecreationinst.pdf) (pdf)
- [How I created/simulated the `bradley.csv` data](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/bradley_sim.md)

## Today's References (from the Slides, etc.) 

1. Hadley Wickham and Garrett Grolemund [R for Data Science](https://r4ds.had.co.nz/)
2. Karl W. Broman & Kara H. Woo (2018) [Data Organization in Spreadsheets](https://github.com/THOMASELOVE/432-2021/blob/master/references/pdf/Broman_and_Woo_2018_Data_Organization_in_Spreadsheets.pdf), *The American Statistician*, 72:1, 2-10, DOI: [10.1080/00031305.2017.1375989](https://doi.org/10.1080/00031305.2017.1375989)
3. Jeff Leek and colleagues [How to Share Data with a Statistician](https://github.com/jtleek/datasharing)
    - Shannon Ellis and Jeff Leek's pdf "[How to Share data for Collaboration](https://peerj.com/preprints/3139v5.pdf)" touches on many of the same points.
4. Hadley Wickham [Tidy Data](https://www.jstatsoft.org/article/view/v059i10), *J of Statistical Software*.
5. Jenny Bryan's [Speakerdeck presentation on Naming Things](https://speakerdeck.com/jennybc/how-to-name-files).
    - Jenny and colleagues also provide [Good Enough Practices in Scientific Computing](http://bit.ly/good-enuff).
6. XKCD on 
    - [How to Write Dates](https://xkcd.com/1179/)
    - [Naming Files in Hard](https://xkcd.com/1459/)

### What's that course password again?

Some of the materials on the [References and Resources page](https://github.com/THOMASELOVE/432-2022/tree/main/references) of books, articles, videos and other things are password-protected. Please dip into them as your time allows.

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/figures/tukey.png)

## Questions (with Answers) from the "[Welcome to 432 Survey](https://bit.ly/432-2022-welcome-survey)"

Again, if you haven't taken the survey already, please [do so today](https://bit.ly/432-2022-welcome-survey).

1. How is Dr. Love feeling?
    - I am fine, in the 2022 sense that I am essentially healthy and my family is, as well. On the other hand, I am anxious most of the time, and certainly not functioning at full capacity. I ask for your patience.
    - With regard to the upcoming semester, I am hopeful that we can deliver an effective course, and that we can connect with each of you in a helpful, supportive way. 
    - I am very grateful for [our teaching assistants](https://thomaselove.github.io/432-2022-syllabus/teaching-assistants.html), who do a lot to keep us all moving forward (especially me). [Please let us know](https://thomaselove.github.io/432/contact.html) if we can help you along the way.
2. Has Dr. Love been boosted against COVID-19?
    - Yes. Three Pfizer shots. No one in my immediate family has contracted the illness, to our knowledge.
3. How did Dr. Love spend his holiday season?
    - With my wife and two (adult) children, in the house. We watched a fair amount of stuff together, and did a lot of crossword puzzles and spelling bees, and ate, a lot. The kids and I are now doing [Wordle](https://www.powerlanguage.co.uk/wordle/).
    - My older son has now returned to his apartment in Pittsburgh where he does geographic information systems work for the National Mine Map Repository.
    - My younger son is in his second year of college (Columbia University) - starting remote classes next week for two weeks.
4. Are the deadlines in the Course Calendar a complete description of what will be required of us this term?
    - Yes, even though most of the actual instructions for the assignments are not yet posted - every deadline is already on the Calendar. More detailed instructions for all assignments should appear by one week from today.
5. Are there multiple students in 432 who did not take 431 this past Fall?
    - Yes, four or five of the 44 students who are enrolled, I think. 
6. (from a student who did not take 431 with us in the Fall) Are there any specific parts of 431 that we should review and pay special attention to and that will be integral to succeeding in 432? 
    - I expect the most obviously useful elements will be the discussion of specific R packages and functions related to working with linear models. It would also be helpful to look at the lab assignments and project requirements and tips from 431 since we build on that knowledge in the 432 materials. [The R-basics document](https://github.com/THOMASELOVE/432-2022/tree/main/r-basics) from the 432 R and Data menu is certainly worth some of your time, too.
7. Do you plan to video record all class sessions this term?
    - Yes, although I may make a mistake at some point.
8. Will the class go back to being "in person" after the first four sessions?
    - That's the plan as of now, yes. When that happens, "live" Zoom sessions will no longer be available, but recordings will continue.
9. How can I express interest in being a TA next year?
    - After this semester is over, Dr. Love will send out an email to everyone who completed 432 in the past two years (plus all of this year's TAs) to explain the process and what would be required of you. If you're interested, all you need to do is respond to that email and apply. We have both compensated (very lightly compensated) and volunteer positions available, and I typically find a position for all applicants that are interested. I welcome anyone and everyone to help. There's plenty of work to go around.
10. Are you performing in any shows this semester?
    - The show "Something Rotten" at Hudson Players that I was scheduled to be in has been postponed from February to a new date in Fall 2022 that we cannot announce yet. I have no current plans to do any other shows before that.

## One Last Thing

Want to read the most misguided paper of 2020? Darren Dahly's [Twitter thread has you covered](https://twitter.com/statsepi/status/1338501499039739906).

![](https://github.com/THOMASELOVE/432-2022/blob/main/classes/class01/figures/dahly_2020-12-14.png)

- The paper Darren refers to is [Basic statistics: A research primer for low- and middle-income countries](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7718448/).
- Another 2020 paper in the series called [Research skills and the data spreadsheet: A research primer for low- and middle-income countries](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7718460/) is even more, well, I don't know what to say except for heaven's sake, don't take any of its advice. 
    - I'm happy to believe that the intentions here were nothing but good, but this has really gone wrong.
    - Check out the annotated biography in that second paper, for example.


