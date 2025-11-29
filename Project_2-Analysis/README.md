# Introduction

As I transition into the data science industry, it is of great importance to understand the current job market to identify the skills necessary for securing a well-paying position. To achieve this, I conducted an analysis of industry trends and employer expectations. This research will help me focus my professional development on the most relevant technical and soft skills, ensuring I am well-prepared to meet market demands and advance my career prospects in data science.

---

## Questions to Analyze

To understand the data science job market, I asked the following questions:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

---

## Excel Skills Used

The following Excel skills were utilized for this analysis:

- 📊 **Pivot Tables**
- 📈 **Pivot Charts**
- 🧮 **DAX (Data Analysis Expressions)**
- 🔍 **Power Query**
- 💪 **Power Pivot**

---

## Data Jobs Dataset

The dataset used for this project contains real-world data science job information from **2023**.  
It includes detailed information on:

- 👨‍💼 **Job titles**
- 💰 **Salaries**
- 📍 **Locations**
- 🛠️ **Skills**

---

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
- 🗃️ The first with all the data jobs information.
- 🔧 The second listing the skills for each job ID.


## 🔄 Transform

- I transformed each query to prepare the data for analysis. The steps I applied to both queries were:

- Changed column data types to appropriate formats (text, number, date/time).
- Removed unnecessary or duplicate columns.
- Cleaned text fields to remove specific unwanted words and characters.
- Trimmed excess whitespace and normalized casing where appropriate.

---

 📊 data_jobs_salary

<img width="297" height="395" alt="Data Table" src="https://github.com/user-attachments/assets/4a0749c2-917c-4e75-8944-532867b10cd4" />

---

🛠️data_job_skills

<img width="303" height="404" alt="Job Skills" src="https://github.com/user-attachments/assets/77613be2-6e16-4e9a-abc7-cf36fa4929f7" />

---

## 🔗Load

- Finally, I loaded both transformed queries into the workbook to serve as the foundation for the subsequent analysis. Loading completed the ETL pipeline and allowed me to build the pivots, charts, and DAX measures for the analysis.


### Full table previews


 📊data_jobs_salary

<img width="1919" height="767" alt="Data job all" src="https://github.com/user-attachments/assets/9492ebb8-0f9b-4582-a084-04f60e4c90e4" />

--- 

🛠️data_job_skills

<img width="1919" height="786" alt="Data job skills" src="https://github.com/user-attachments/assets/4376a113-31b3-4129-85fd-c70700449f44" />

---

## 📊 Analysis
### 💡 Insights
- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.

- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.
  

 <img width="702" height="417" alt="Scatter plot" src="https://github.com/user-attachments/assets/a6a66c0f-7b0d-4926-88cd-f6f3be07664a" />
 
 
### 🤔 So What
- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.


 ## 2️⃣ What’s the salary for data jobs in different regions?
### 🧮 Skills: PivotTables & DAX
#### 📈Pivot Table
- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the job_title_short to the rows area and salary_year_avg into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
```=CALCULATE(
    MEDIAN(data_jobs_salary[salary_year_avg]),
    data_jobs_salary[job_country] = "United States")
```
### 🧮 DAX
- To calculate the median year salary I used DAX.

```Median Salary := MEDIAN(data_jobs_all[salary_year_avg])```

## 📊 Analysis
### 💡 Insights
- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.

- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.


<img width="913" height="344" alt="US,Non US Salary" src="https://github.com/user-attachments/assets/02dc1aa3-92c8-47dc-a5e7-6fe73c2dbfc7" />

### 🤔 So What
- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?
### 🔧 Skill: Power Pivot
#### 💪 Power Pivot
- 🔗 I created a data model by integrating the ```data_jobs_salary``` and ```data_jobs_skills``` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.
#### 🔗 Data Model
- I created a relationship between my two tables using the ```job_id``` column.

<img width="790" height="565" alt="Table connection" src="https://github.com/user-attachments/assets/6721cf3b-a3f8-419a-b38f-0ec6a24f2a4e" />

### 📃 Power Pivot Menu
- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

<img width="1919" height="795" alt="P Pivot menu" src="https://github.com/user-attachments/assets/893ca6f9-ec46-4492-803d-00084e7184d4" />

## 📊Analysis
### 💡Insights
- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.

- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

<img width="693" height="437" alt="Top Data Skills" src="https://github.com/user-attachments/assets/5573e7de-5d7e-47ac-a34c-8e8c11195af3" />

### 🤔So What
- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.
  
## 4️⃣ What’s the pay of the top 10 skills?
### 📊 Skill: Advanced Charts (Pivot Chart)
#### 📈 PivotChart
- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
  
🪙 Primary Axis: Median Salary (as a Clustered Column)

👍 Secondary Axis: Skill Likelihood (as a Line with Markers)

- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

## 📊 Analysis
### 💡Insights
- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.

- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

<img width="615" height="381" alt="Top Paying Skills" src="https://github.com/user-attachments/assets/48e48890-1a6d-4310-98b7-9897bf651bf6" />

### 🤔So What
- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

  
## Conclusion

As someone new to the data science field, I created a simple Excel project to learn how the job market works. I collected real job postings and used Excel tools—Power Query to clean the data, PivotTables and DAX to analyze it, and charts to visualize results—to explore job titles, salaries, locations, and the skills employers ask for. I found that having multiple skills, especially Python, SQL, and cloud technologies, often corresponds with higher pay. I hope this project helps other beginners see which skills to focus on and gives a practical example of how to use Excel for real-world data analysis.
