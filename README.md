# **Update:
This project was terminated due to the discovery of a bug with Glassdoor's job postings website. After browsing to page 7 of the job postings, the same job postings would be repeated.

# Project: Data Science Job Market and Salary prediction model
##### Author: Lingfeng Yang
##### Date: October 31, 2022

The objective of this project is to analyze the current and past job market for Data Science roles, specifically new-grad roles. The project will also develop a model to predict salary based on various factors. 

This project will showcase the entire Data Science project life cycle:
1. Project Planning 
2. Data Collection  
3. Data Cleaning 
4. Exploratory Data Analysis 
5. Model Building 
6. Model Development 

This project will also aid in my personal job search to aggregate available position suited to my experience.

## Resources Used:
##### Scraper Article: ["Web Scraping Job Postings from Indeed" - Michael Salmon](https://medium.com/@msalmon00/web-scraping-job-postings-from-indeed-96bd588dcb4b)
##### Guiding Project: ["Data Science Salary Estimator" - PlayingNumbers Github](https://github.com/PlayingNumbers/ds_salary_proj)

## Data Scraper

File: Glassdoor_Job_Scraper.ipynb

Using the scraper (above) to aggregate 1000 jobs from Glassdoor.com. The following elements were obtained:
- Job Title
- Salary Estimate
- Job Description
- Rating
- Company Name
- Division
- Location
- Size
- Founded
- Type of ownership (ie. Company-public, Hospital, Non-Profit etc.)
- Industry
- Sector
- Company Revenue


### Changes
There were two major complications when using the original scraper
1. Glassdoor had changed their website structure and HTML tags \n
This rendered many HTML element finders (by XPATH) to become obsolete. Updates were made to reflect the changes in Glassdoor.
2. Updates to the Selenium package \n
Many of the functions within the Selenium package were deprecated. The program was updated to use the new functions.

## Data Cleaning



## Exploratory Data Analysis

