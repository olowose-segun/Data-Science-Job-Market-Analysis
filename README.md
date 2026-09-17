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

### 📊 Data Preparation

[data_jobs_all]

<img width="315" height="384" alt="Screenshot 2026-09-17 234931" src="https://github.com/user-attachments/assets/ff6e2f72-db39-4554-b9ed-6cec1029697a" />


[data_job_skills]

<img width="311" height="397" alt="Screenshot 2026-09-17 235025" src="https://github.com/user-attachments/assets/dee6a9dd-f7da-4306-8ef8-7c510d670f49" />




After completing the transformations, both queries were loaded into the workbook for further analysis.

<img width="1912" height="834" alt="Screenshot 2026-09-17 235221" src="https://github.com/user-attachments/assets/33ddca38-a6e3-4e57-9b20-e8ad63a641d0" />


<img width="1914" height="828" alt="Screenshot 2026-09-17 235402" src="https://github.com/user-attachments/assets/1bbce45a-cf7e-44d2-88e6-900a17772fae" />



### 📈 Results & Insights

The analysis shows a positive association between the number of skills requested in job postings and median salary, particularly among roles such as **Senior Data Engineer** and **Data Scientist**.

Roles requiring fewer specialised skills, such as **Business Analyst**, generally recorded lower median salaries in this dataset.

However, the results indicate an association rather than proof that acquiring additional skills directly causes higher pay.

[Skills vs Median Salary]

<img width="866" height="474" alt="Screenshot 2026-09-17 235627" src="https://github.com/user-attachments/assets/41870a50-12c8-49aa-95cb-8b4c7bd02097" />


### 📊 Data Interpretation

Developing multiple relevant and specialised skills may improve access to higher-paying opportunities, especially when those skills align with the requirements of advanced data roles.

---

## 2️⃣ Salary Comparison Across Regions

### 🧮 Tools Used

- Power Pivot
- PivotTables
- DAX

### 📊 Building the Analysis

Using the data model created with Power Pivot, I built a PivotTable to compare median salaries across job titles and geographical regions.

The PivotTable was configured with:

- `job_title_short` in the Rows area
- `salary_year_avg` in the Values area

I also created a DAX measure to calculate the median salary for jobs located in the United States:

```DAX
Median US Salary :=
CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States"
)
```

A general median salary measure was also created:

```DAX
Median Salary :=
MEDIAN(data_jobs_all[salary_year_avg])
```

### 📈 Results & Insights

Roles such as **Senior Data Engineer** and **Data Scientist** recorded relatively high median salaries in both the United States and international markets.

The comparison highlights how salary levels vary by role and geography, while also showing the strong compensation associated with advanced technical positions.

[salary_analysis]
<img width="1203" height="399" alt="Screenshot 2026-09-18 000930" src="https://github.com/user-attachments/assets/ee1032c3-1119-4bab-bfde-646b7dcb2294" />


### 📊 Data Interpretation

Regional salary analysis can help professionals understand market differences, evaluate career opportunities, and approach salary discussions with better context.

---

## 3️⃣ Most Requested Skills in Data-Related Jobs

### 🔧 Tool Used

**Power Pivot**

### 🔗 Building the Data Model

I integrated the `data_jobs_all` and `data_job_skills` tables into a single data model using Power Pivot.

A relationship was established between the two tables through the `job_id` column, allowing job information and skill requirements to be analysed together.

[Power Pivot Data Model]
<img width="912" height="601" alt="Screenshot 2026-09-18 001121" src="https://github.com/user-attachments/assets/51096248-82f4-4793-a577-c590da811871" />


### 📃 Model Refinement

The Power Pivot interface was used to manage the data model and create the measures required for the analysis.

[Power Pivot Menu]
<img width="1911" height="801" alt="Screenshot 2026-09-18 001310" src="https://github.com/user-attachments/assets/c2d292e6-1aef-4850-bdda-d5f6ee932c4c" />


### 📈 Results & Insights

**SQL** and **Python** emerged as the most frequently requested skills in the dataset, reinforcing their importance across data-related roles.

Cloud technologies such as **AWS** and **Azure** also appeared prominently, reflecting the growing role of cloud infrastructure and large-scale data technologies in the industry.

[Top Data Skills]

<img width="653" height="397" alt="Screenshot 2026-09-18 001803" src="https://github.com/user-attachments/assets/2cb83088-6192-45ba-910e-98fba34a4ae0" />


### 📊 Data Interpretation

Understanding which skills employers request most frequently can help aspiring data professionals prioritise their learning and align their development with industry demand.

---

## 4️⃣ Salary Associated with the Top 10 Skills

### 📊 Tool Used

**PivotCharts**

### 📈 Chart Development

I created a combination PivotChart to compare:

- Median salary
- Skill likelihood (%)

The chart used:

- Clustered columns on the primary axis to represent median salary
- A line with markers on the secondary axis to represent skill likelihood

I refined the visual presentation by adjusting the chart title, axis labels, gridlines, marker shapes, marker sizes, and overall formatting.

### 📈 Results & Insights

Skills such as **Python, Spark, and SQL** were associated with relatively higher median salaries, indicating their presence in roles offering stronger compensation within the dataset.

Meanwhile, **PowerPoint** and **Word** recorded lower median salaries and lower skill likelihood, reflecting their more limited association with specialised, high-paying data positions.

[Top 10 Skills Salary Analysis]

<img width="787" height="494" alt="Screenshot 2026-09-18 002558" src="https://github.com/user-attachments/assets/76e10d04-e13f-4b87-bb02-354eeab997d3" />


### 📊 Data Interpretation

The findings highlight the importance of prioritising technical skills that are both widely requested and associated with higher-paying opportunities, particularly **Python and SQL**.

---

## 🏁 Conclusion

This project was an opportunity to apply Excel beyond basic spreadsheet operations and use it as a tool for practical data analysis.

Using **Power Query, PivotTables, Power Pivot, DAX, and PivotCharts**, I explored real-world job posting data to understand:

- The relationship between requested skills and median salary
- Salary differences across regions
- The most frequently requested technical skills
- The skills associated with higher-paying data roles

The analysis highlighted the continued relevance of **Python, SQL, and cloud technologies** across the data job market.

As I continue my Data Analytics journey, projects like this are helping me strengthen my ability to clean data, build data models, create analytical measures, and communicate insights through visualisation.

## 🙌 Credits

This project is credited to **Luke Barousse**, the first person I learned Excel from through YouTube.

His Excel Beginners Course provided the foundation and dataset used for this analysis [here](https://youtu.be/pCJ15nGFgVg)
