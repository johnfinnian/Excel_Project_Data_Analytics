# Excel Salary Dashboard



## Introduction

This is a data science salary dashboard created to help job seekers investigate salaries for their desired job and ensure they are adequately compensated. 
The dashboard contians the count of jobs postings in different countries, salaries, type of job schedule and the most common job postings platforms.

## Dashboard File
[Checkout my project on salary dashboard](Project_1-Salary_Dashboard.xlsx)

## Excel Skills Used
The following are the major skills employed in the Analysis:

**Charts**

**Formula and Functions**

**Data Validation**

## Data Job Dataset

The dataset used for this project contains real-world data science job information from 2023:

**Job titles**

**Salaries**

**Location**

**Skills**

## Dashboard Build

### Charts

**Data Science Job Salaries - Bar Chart**

<img width="561" height="351" alt="Salary Bar Chart" src="https://github.com/user-attachments/assets/7914977b-683b-4b70-b9b9-2d276f78b2b5" />

**Excel Feature**: Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.

**Design Choice**: Horizontal for visual comparison of median salary.

**Data Organization**: Sorted job job titles by descending salary for improved readablity

**Insights Gained**: This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.


**Country Median Salary - Map Chart**

<img width="505" height="381" alt="Country" src="https://github.com/user-attachments/assets/7debd194-eaab-4747-a7a3-7735cf321e4e" />

**Excel Features**: Utilized Excel's map chart feature to plot median salary globally.

**Design Choice**: Colour-coded map to visually diiferent salary levels across regions.

**Data Representation**: Plotted median salary for each country with available data.

**Visual Enhancement**: Improved readability and immediate understanding of geographic salary trend.

**Insight Gained**: Enables quick grasp of global salary disparities and high/low salary regions.


**Formula and Function**

**Median Salary by Job Titles**

         ```=MEDIAN( IF((Job_Data[job_title_short]=$A2) *
          (ISNUMBER(SEARCH(type,Job_Data[job_schedule_type])))*
          (Job_Data[job_country]=country) *
          (Job_Data[salary_year_avg]<>0),
          Job_Data[salary_year_avg]))```

**Multiple Criteria Filtering**: Checks job title, job schedule type, country, and excludes blank salaries.

**Arry Formula**: Utilized ```MEDIAN()``` function with nested ```IF()``` statement to analyze an array.

**Tailored Insight**: Provides specific salary information for job titles, regions and job schedule types.

**Formula Purpose**: This formula populates the table below, returning the median salary based on job title, county and type specified.

Background table

<img width="332" height="272" alt="Salary Table" src="https://github.com/user-attachments/assets/79e1e086-0372-43ed-800d-7de6df7fafd8" />

**Dashboard Implementation**

<img width="544" height="580" alt="Median Salary" src="https://github.com/user-attachments/assets/969f0ce1-8894-4ff0-b524-bd250732f836" />

**Count of Job Schedule Type**

```=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(", ",J2#))))*(J2#<>0))```

**Unique List Generation**: The Excel formula above empioys the ```FILTER()``` function to exculed entries containing "and" or "," and omit zero values.

**Formula Purpose**: This populates the table below, which gives us a list of unique job schedule types.

**Filter List** 

Enhanced data validation: Implementing the filtered list as a data validation rule under the ```job title```, ```country``` and ```type``` option in the data tab ensures: 
  User input is restricted to predefined, validated schedule types
  Incorrect or inconsistent entries are prevented
  Overall usability of the dashboard is enhanced

https://github.com/user-attachments/assets/d15b964c-3fde-4966-90b6-ac7fb918f57f

## Conclusion 

I created this dashboard to showcase insights into salary trends across various data-related job titles. This dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how country and job schedule type influence salaries.

