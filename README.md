# **Update:
This project was terminated due to the discovery of a bug with Glassdoor's job postings website. After browsing to page 7 of the job postings, the same job postings would be repeated. As the direction of this project is to gain a better understanding of the Data Science market within Canada, the search term "Data Science" and location "Canada" were inputs in Glassdoor. The bug showed that while there may have been 800+ postings matching the search criteria, only a maximum of about 180 were displayed due to incorrect loading on Glassdoor's end.
<br />
<br />
Besides the bug on Glassdoor, another inherent bias of this project is that the analysis would describe the Canadian Data Science job market through the lens of Glassdoor only. For a more complete and thorough analysis of the job market, data should be scraped from various sources such as LinkedIn and Indeed. 
<br />
<br />
The cleaning and exploratory data analysis was conducted on a subset of the available job postings for testing and developemnt purposes. As the complete job posting list from Glassdoor is unavailable, the analysis does not provide an accurate description of the Data Science landscape in Canada.


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
<br />
The resulting dataframe from the scraper: <br />

![WebScrape DataFrame Img](https://github.com/myang987/dsjob/blob/main/Pictures/Web_Scrape_Dataframe.png)

### Changes to Original Scraper
There were two major complications when using the original scraper
1. Glassdoor had changed their website structure and HTML tags <br />
This rendered many HTML element finders (by XPATH) to become obsolete. Updates were made to reflect the changes in Glassdoor.
2. Updates to the Selenium package <br />
Many of the functions within the Selenium package were deprecated. The program was updated to use the new functions.

## Data Cleaning

The resulting dataframe was then cleaned in preperation for the EDA and model building. <br />
The following processes and variables were conducted/created:
1. Clean whitespace and other characters from the Company Name
2. New indicator variable for if Estimated Salary is Hourly or Annual 
3. New indicator variable for if Estimated Salary was provided by the employer
4. Parse the Estimated Salary range into min/max/avg salary
5. Parse Job Description for keywords of skills/technologies
New indicator variables were created for the following parsed keywords:
- Python
- R
- SQL
- Java
- R-Studio
- Spark
- AWS
- Excel
- Google BigQuery
- SQL Server
- Docker
- Jira
- Hybrid work
- Remote work

An entry from the resulting cleaned Dataframe: <br/>

<img src="/Pictures/Cleaned_Dataframe.png" alt="Cleaned Dataframe" width="800"/>

## Exploratory Data Analysis

First, observing the general distribution of the salary estimates: <br />
![Salary Distribution Img](https://github.com/myang987/dsjob/blob/main/Pictures/Salary_Distributions.png)
There is a small noticable trend among the 'Minimun Annual Salary Estimates'. The min-salaries distribution contains a slight right-skew, indicating that companies hiring for roles within data-science tend to have a similar baseline for salary. This could be a result of the industry trends and the industry as an emplyers market. <br />
The distribution for maximum annual salary follows a more normal distribution than the minimum annual salaries. For further insights, more analysis will be required.
<br />
<br />
Taking a look at industry and sector salary trends: <br />

<img src="/Pictures/Average_Salary_by_Industry.png" alt="Salary by Industry" width="350"/> <img src="/Pictures/Average_Salary_by_Sector.png" alt="Salary by Sector" width="350"/>
