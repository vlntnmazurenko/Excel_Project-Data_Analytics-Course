# Excel_Project-Data_Analytics-Course
## Introduction
This project was completed as part of the Data Analytics course by [Luke Barousse](https://www.youtube.com/@LukeBarousse), a data analyst and educator who creates practical tutorials for aspiring data professionals. Throughout this project, I strengthened my Excel skills, including data cleaning, analysis, and visualization techniques, while exploring the most optimal jobs and in-demand skills in the data science market.  
## Project Objectives
The goal of this project was to explore the data science job market in 2023 and identify key trends related to salaries and required skills. Through the analysis, I focused on answering the following questions:  
1. Does possessing a broader skill set lead to higher salaries?
2. How do salaries for data-related roles vary across different regions?
3. Which skills are most commonly required for data professionals?
4. What salary levels are associated with the most in-demand skills?
## Skills & Tools Applied
During this project, I strengthened and applied the following Excel skills:  
- 📊 Pivot Tables for data summarization and analysis
- 📈 Pivot Charts for data visualization
- 🧮 DAX (Data Analysis Expressions) for advanced calculations
- 🔍 Power Query for data cleaning and transformation
- 💪 Power Pivot for data modeling and relationship management
## 1. Does possessing a broader skill set lead to higher salaries?
To answer this question, I used Power Query to perform the ETL (Extract, Transform, Load) process and prepare the dataset for analysis.
### 📥 Data Extraction
I imported the original dataset (data_salary_all.xlsx) into Power Query and created two separate queries:
- data_jobs_salary – containing information about data-related positions, salaries, and locations.
- data_jobs_skills – containing the skills associated with each job posting.
### 🔄 Data Transformation
To ensure data quality and consistency, I performed several cleaning and transformation steps:
- Adjusted data types for relevant columns
- Removed unnecessary fields
- Cleaned text values by removing unwanted words and characters
- Trimmed extra whitespace
- Prepared the data for further analysis and reporting
  - data_jobs_salary  

    <img width="1683" height="827" alt="Снимок экрана 2026-05-31 140319" src="https://github.com/user-attachments/assets/5beaf5e0-76ae-40fa-9cbd-e38a718bc5a8" />
        
  - data_jobs_skills  

    <img width="1694" height="822" alt="Снимок экрана 2026-05-31 140341" src="https://github.com/user-attachments/assets/89321aa4-3ce7-4f24-9b81-2dc537e89b31" />

### Key Insights
- 📈 The analysis revealed a positive relationship between the number of skills required in job postings and median salary levels. Roles such as Senior Data Engineer and Data Scientist, which typically demand a broader and more specialized skill set, tend to offer higher compensation.
- 💼 Positions with lower skill requirements, such as Business Analyst, generally show lower median salaries. This suggests that employers place a premium on candidates with diverse technical expertise and advanced analytical capabilities.
- 🎯 The findings indicate that investing in additional technical skills can increase earning potential and create access to more specialized, higher-paying opportunities within the data industry.

  <img width="707" height="389" alt="Снимок экрана 2026-05-31 140820" src="https://github.com/user-attachments/assets/2ca23723-85f1-4568-8ceb-cba1f106aa47" />

## 2. How do salaries for data-related roles vary across different regions?
To compare salary levels between the United States and other countries, I used PivotTables, Power Pivot, and DAX measures to analyze median salaries across different data-related roles.
### 📊 PivotTable Analysis
I created a PivotTable based on the data model built in Power Pivot and organized the data by job title. To provide a more reliable comparison, I focused on median salary rather than average salary, as it is less affected by extreme values.
### 🧮 DAX Measures
To calculate median salaries, I created custom DAX measures, including:   

`Median Salary:= MEDIAN(data_jobs_all[salary_year_avg])`  

and a measure specifically for United States positions:  

`Median Salary USA:=
CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States"
)`  

and a measure specifically for non United States positions:  

`Median Salary Non USA:=CALCULATE([Median Salary]; data_jobs_salary[job_country]<>"United States")`  

### Key Insights
- 💼 Senior Data Engineer and Data Scientist roles consistently show the highest median salaries, both within the United States and internationally, highlighting the strong global demand for advanced data expertise.
- 🌍 Salaries for data-related positions are generally higher in the United States compared to other regions, particularly for highly technical roles.
- 💰 The largest salary gaps between US and non-US markets appear in specialized positions, suggesting that factors such as market maturity, industry concentration, and demand for advanced technical skills may significantly influence compensation levels.
- 📈 Across all regions, technical and data-focused roles tend to command higher salaries than more business-oriented positions, reflecting the growing value of analytical and engineering expertise in the job market.

  <img width="914" height="285" alt="Снимок экрана 2026-05-31 143344" src="https://github.com/user-attachments/assets/fbea4c1b-b460-4a74-9b55-2de9ac782f7f" />

