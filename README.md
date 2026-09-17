# 📊Data-Science-Job-Market-Analysis
>An Excel based analysis of 2023 data science job postings, exploring the relationship between skills and salary, regional salary differences, and the most in demand skills across data roles. Built using Power Query, Power Pivot, DAX, Pivot Tables, and Pivot Charts to transform, analyse, and visualize real world job market data.

## 📌 Project Overview

What skills are employers looking for in data professionals, and how do those skills relate to salary?

This project explores the data science job market using real-world job posting data from 2023. The analysis focuses on salary differences across regions, the most frequently requested technical skills, and the relationship between the number of skills listed in job postings and median salary.

The project was completed using Microsoft Excel and its data analysis capabilities, including Power Query, Power Pivot, DAX, PivotTables, and PivotCharts.


## 🎯 Research Questions

The analysis was guided by four key questions:

1. Is having more requested skills associated with higher pay?
2. How do data job salaries compare across different regions?
3. Which skills are most frequently requested in data-related job postings?
4. What are the median salaries associated with the top 10 most requested skills?


## 🛠️ Tools & Skills

- Microsoft Excel
- Power Query
- PivotTables
- PivotCharts
- Power Pivot
- DAX (Data Analysis Expressions)

## 📁 Dataset

The dataset contains real-world data science job posting information from **2023** and was sourced from the Excel course that served as the foundation for this project.

It includes:

- Job titles
- Annual salaries
- Job locations
- Required skills
- Job IDs

---

## 1️⃣ Skills vs. Salary

### 🔍 Objective

To investigate whether job postings requesting a greater number of skills are associated with higher median salaries.

### 📥 Data Extraction

I used **Power Query** to import the original `data_salary_all.xlsx` file and created two queries:
- **`data_jobs_all`**  Containing general information about each data-related job posting.

- **`data_job_skills`**  Containing the skills associated with each job ID.

### 🔄 Data Transformation

The queries were cleaned and prepared by:

- Assigning appropriate data types
- Removing irrelevant columns
- Cleaning text values
- Removing unwanted words from text fields
- Trimming unnecessary spaces




