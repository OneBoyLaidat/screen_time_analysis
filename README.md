## OVERVIEW

If I got a dollar for every time I have heard the words “You spend too much time on your phone!” I would be the richest man in Africa. 

This data analysis project is my attempt to fix that and gain insights into my phone usage by analysing my screen time data from March 2nd to October 5th, 2023. 

**My goal is straightforward -** Understand how long I spend on my phone and reduce daily screen time to under 2 hours. 

Through this project, I want to find peak usage periods and the apps that held me captive, unveiling the true culprits behind my screen time woes.


## TABLE OF CONTENTS

- [Questions to Answer](##questions-i-want-to-answer)
- [Tools Used](##tools-used)
- [Data Preparation and QA](##data-preparation-and-qa)
- [Analysis](##the-analysis)
- [Data Model](##data-model)
- [Dashboard](##dashboard)
- [Recommendations](##recommendations)
- [Closing Thoughts](##closing-thoughts)

## QUESTIONS I WANT TO ANSWER.

- What is my average daily screen time across the entire period analysed? 
Reason: Just to confirm if there is a problem to begin with.

- Is there a significant difference in screen time between weekdays and weekends? Are there specific days where I tend to overindulge? 
Reason: To see what days I tend to overindulge.

- Which apps am I spending the most time on? Is there a specific category dominating my usage (e.g., social media, games, news)?
Reason: I want to know what my biggest time-drain are and if it is the usual suspects.

## TOOLS USED
For my deep dive into my screen time, I harnessed the power of:

1. **Power BI** – I used Power BI for the whole analytical process from data cleaning to data prep, to Data Modelling and Exploring the data till Data Visualization. 

I used the following skills and tools during the project. 
- Power Query
- DAX
- Slicers
- Data Visualization

## DATA PREPARATION AND QA
### DATA
The dataset has aggregated phone usage records, for each app from the 2nd of March to 5th of October 2023, with three different sheets including details on each app total screen time, total app opens, and a total phone unlocks.

The data was stored in multiple worksheets in a single Excel workbook in a XLSX format. It was collected using an app called ‘Stayfree’ that provides device usage analytics for free.


### DATA PREP AND CLEANING
|**Before Data Prep**|**After Data Prep**|
|:---:|:---:|
|![time_spent_b4_modelling](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/66f78cf8-f7fb-4780-992e-64c1cb558fe0) | ![screen_time_after_modelling](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/d48b3c2b-1617-4010-ab3d-50dc5e662ab8)|

- Loaded the dataset with Power Query.
- Selected the three worksheets I would be working with:

  - App - Usage Count (renamed to “Fact_App_Sessions”)
  - App - Usage Time (renamed to "Fact_Screen_Time”)
  - Device Unlocks (renamed to “Fact_Device_Sessions”)

- Unpivoted the dates from columns into a single column called ‘Date’ in each table.
- Removed all rows that had “Total Usage” Values in each table.
- Converted the screen time values from “Xh Ym Zs” text format to its equivalent in seconds in the “Fact_Screen_Time” Table.
- Added a Dim_Date lookup table.
- Added a Dim_App lookup table to include details about app categories.

  

## METRICS TRACKED
Next, I created an interactive dashboard in Power BI to look at my Screen time metrics. I wanted to get a glance of my screen time habits and my daily screen time. I included the following metrics:

- **Daily Average Screen Time:** The biggest and most important thing to know about reducing my screen time is what my screen time is. That is why this metric is top.

- **Total Screen Time (in Hours):** I chose this metric to be able to see the how much productive time I have lost to the screen.

- **Average Length per Session (in Mins):** This is an important metric because it shows how much productive time I lose every time I unlock my phone. Could help me Identify high usage apps. 

- **Average Daily Sessions:** This metric shows how many times I pick up and unlock my phone on average per day. I can use it to tell how much impulse unlocks I make.

## DATA MODEL
![database_model_after_modelling](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/74c10b09-c1c0-49a3-8574-89cecc187dec)

## THE ANALYSIS
Each query for this project aimed at investigating specific aspects of my screen time. Here’s how I approached each question:
1. **What is my average daily screen time across the entire period analysed?**

![Total Time Spent](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/7fe4a9c1-9206-457f-a648-5c0570fe653a)
    
With a daily average screen time of almost 7 hours (6hrs 56mins), that’s 3hrs 13mins more the global average for mobile phone usage (3hrs 43 mins) and almost 5 hrs more my target goal of 2hrs.

I can say there is indeed a problem about my relationship with my phone.


2. **Is there a significant difference in screen time between weekdays and weekends? Are there specific days where I tend to overindulge?**

![Weekend_vs_Weekdays_Screentime](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/f84e2b6d-a5ae-4784-b00c-6d00b36edaca)

My average screentime on weekends were 30 minutes less than on weekdays but were both higher than my target of 2hrs.


![avg_daily_screen_time_by_dow](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/7346f384-0fc5-4c4b-8977-95484b857b01)


Mondays have the highest average screen time i.e. I spend more time on my phone on Monday than any other day.


3. **Which apps am I spending the most time on? Is there a specific category dominating my usage (e.g., social media, games, videos)?**
   
![Top 5 app categories](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/9c51a752-c0cb-4df2-babd-f9a03a0cdb70)

The top 5 categories were Games, Socials, Videos, Browser and Others (which was is a category for apps I couldn’t categorise) in that order, contributing 1380 hours out of the total screen time of 1500 hours between March 2nd and October 5th, 2023. 

![Top 10 apps used by screen time](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/b7cb6f87-bf4c-4a55-a48c-25318e3e8d7c)

It’s no surprise to me that 2 of the top 5 apps used were football games. I’m a big fan of football and love being part of it either on the field or off it. My favorite team is Fc Barcelona. But it is obvious they’re big distractions to my productivity goals.

WhatsApp, YouTube, Chrome, Google, VLC, Sudoku, Phone and Files by Google finished up the top 10 apps used and contributed to 81% of the total screen time (1500 hrs.) spent.

## DASHBOARD
Here’s a snapshot of what the final dashboard looks like. [Click to view the live dashboard.](https://bit.ly/screen-time-report)

![Screen_Time_Report](https://github.com/OneBoyLaidat/screen_time_analysis/assets/139885891/a50d8e61-30e0-4881-bf81-1b3c3c8ffcc5)

 
## RECOMMENDATIONS

1.	Delete FM 23, Sudoku and eFootball. Avoid all apps that are in the Games category.
2.	Restrict YouTube use to only my laptop.
3.	Since I use WhatsApp to contact Family, I don’t want to delete it. So, I came up with a compromise to restrict my WhatsApp Usage to 2 times a day for 20 minutes each at 2pm and 8pm. And I’ve spoken to my family and friends about it.
4.	Schedule time blocks for catching up with sport news since that is what I spend most of my time on Google and Chrome doing.

## CLOSING THOUGHTS
This project has enhanced my Power BI and Data Visualization skills and offered valuable insights into my screen time habits. The findings from the analysis serve as a guide to prioritizing apps to cut for increased productivity.

Now I can better position myself to get things done without distraction.
