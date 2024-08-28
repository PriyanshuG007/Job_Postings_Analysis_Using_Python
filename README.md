# Overview

**Introducing My Analysis on the Data Job Market: A Focus on Data Science Roles, Specifically Data Analysts in India**

This project was born out of a desire to better navigate and understand the complexities of the data job market, with a particular focus on data science roles, especially data analysts, within India. Through this analysis, I aim to uncover the top-paying and most in-demand skills, providing insights that can guide professionals toward optimal job opportunities in the field of data science.

The dataset sourced from Luke Barousse's account on hugging face website, containing detailed information on job titles, salaries, locations, and essential skills.

# The Questions

Below are the questions I answered in my project:

1. Which cities in India have the highest number of Data Analyst job opportunities?
2. What insights can be drawn from the companies posting Data Analyst jobs in India?
3. What are the most in-demand skills for the most popular Data Science roles?
4. How do different jobs correlate with salaries in Data Science roles?


# Tools I Used

For my deep dive into the data analyst job market, I harnessed the power of several key tools:

1. **Hugging Face**: Sourced my dataset form there.

2. **Python**: The backbone of my analysis, allowing me to analyze the data and find critical insights.I also used the following Python libraries:
    - **Pandas Library**: This was used to analyze the data.
    - **Matplotlib Library**: I visualized the data.
    - **Seaborn Library**: Helped me create more advanced visuals.

3. **Jupyter Notebooks**: The tool I used to run my Python scripts which let me easily include my notes and analysis.

4. **Visual Studio Code**: My go-to for executing my Python scripts.

5. **Git & GitHub**: Essential for version control and sharing my Python code and analysis, ensuring collaboration and project tracking.



# Data Preparation and Cleanup

This section outlines the steps taken to prepare the data for analysis

```python
# Importing Libraries
import ast
import pandas as pd
import seaborn as sns
from datasets import load_dataset
import matplotlib.pyplot as plt  

# Loading Data
dataset = load_dataset('lukebarousse/data_jobs')
df = dataset['train'].to_pandas()

# Data Cleanup
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda x: ast.literal_eval(x) if pd.notna(x) else x)
```

# The Analysis

## Which cities in India have the highest number of Data Analyst job opportunities?

To see the execution of the analysis view my notebook with detailed steps here: [Exploratory Data Analysis](1_Exploratory_Data_Analysis.ipynb).

### Results

![number of jobs postings for Data Analyst role in India.](Images\output_1.png)

*Bar graph visualizing the which city has the most number of jobs postings for Data Analyst role in India.*


### Insights 

**Out of over 6000 job postings, This bar graph provides insights into the distribution of Data Analyst job postings across different locations in India:**


1. Hyderabad, Telangana leads among individual cities, with 1,289 job postings.
2. Jobs listed as available Anywhere in India also show a significant number, with 1,052 postings, indicating a strong presence of remote job opportunities.
3. Bengaluru, Karnataka comes next with 355 job postings, followed by Maharashtra (203), Mumbai, Maharashtra (133), and Pune, Maharashtra (119).
4. Other notable cities include Gurugram, Haryana (108), Chennai, Tamil Nadu (106), and Secunderabad, Telangana (84).

Overall, the graph highlights Hyderabad, Telangana as the top city for Data Analyst jobs, with substantial opportunities also available for remote positions.

## What insights can be drawn from the companies posting Data Analyst jobs in India?

To see the execution of the analysis view my notebook with detailed steps here: [Exploratory Data Analysis](1_Exploratory_Data_Analysis.ipynb).

### Results

![number of jobs postings for Data Analyst role in India.](Images\output_2.png)

*The Pie chart visualizing the work from home status, degree requirement status, health insurance offered status bt the company for data analysts job roles in India.*

![number of jobs postings by Individual companies for data analysts roles in india.](Images\output_3.png)

*The bar chart visualizing the number of jobs postings by Individual companies for data analysts roles in India.*

### Insights

This set of pie charts provides insights into the benefits and requirements associated with Data Analyst job postings:

1. Work from Home Offered:
   - A significant majority of job postings (82.8%) do not offer a work-from-home option.
   - Only 17.2% of the postings offer the flexibility to work from home.

2. Degree Requirement:

   - 64.3% of the job postings do not require a degree, indicating that many employers may be open to candidates with relevant skills or experience regardless of formal education.
   - 35.7% of the job postings explicitly require a degree.

3. Health Insurance Offered:
   - None of the job postings offer health insurance as a benefit, as indicated by the chart being entirely blue and labeled "False."

Overall, the charts suggest that while flexibility in work location and degree requirements exists to some extent, health insurance is not commonly provided in these job postings.

## What are the most in-demand skills for the most popular Data Science roles?

To see the execution of the analysis view my notebook with detailed steps here: [Skills Demand Analysis](2_Skills_Demand.ipynb).

### Results

![number of jobs postings for Data Analyst role in India.](Images\output_4.png)

*The Bar graph visualizing the skills which are most demanded for most popular data science roles in India.*

### Insights

1. **Data Engineer**:
   - SQL and Python are the most in-demand skills for Data Engineers.
   - Spark is also a highly sought-after skill, followed by AWS and Azure.

2. **Data Scientist**:
   - Python is the most essential skill for Data Scientists, followed by SQL.
   - R is also a valuable skill, though less in demand than Python and SQL.
   - AWS and Tableau are additional skills that can be beneficial for Data Scientists.

3. **Data Analyst**:
   - SQL is the most crucial skill for Data Analysts, followed by Python and Excel.
   - Tableau and Power BI are important visualization tools for Data Analysts.

**Overall Trends**:

- Python is a common skill across all three roles, highlighting its versatility in the data field.
- SQL is another essential skill, particularly for Data Engineers and Analysts.
- Cloud platforms like AWS and Azure are increasingly important for data professionals.
- Visualization tools like Tableau and Power BI are valued for their ability to communicate data insights effectively.

## How do different jobs correlate with salaries in Data Science roles?

To see the execution of the analysis view my notebook with detailed steps here: [Salary Analysis](3_Salary_Analysis.ipynb).

### Results

![Salary Distribution of Data Science roles in India.](Images\output_5.png)

*The Boxplot graph visualizing the Salary Distribution of Data Science roles in Indias.*

### Insights

The boxplot provides a clear visualization of the salary distributions for various data roles in India. Here are the key insights:

1. **Senior Data Scientist**: This role has the highest median salary, indicating that senior data scientists generally earn more than other positions. The box is relatively long, suggesting a wider range of salaries within this role.

2. **Data Engineer**: The salary distribution for data engineers is similar to that of senior data scientists, with a high median salary and a wide range of earnings.

3. **Senior Data Engineer**: While the median salary is slightly lower than that of senior data scientists, the overall salary distribution is comparable, suggesting similar earning potential.

4. **Data Scientist**: Data scientists have a lower median salary compared to senior roles, but the range is still significant.

5. **Data Analyst**: Data analysts have the lowest median salary among the roles shown, with a narrower range of earnings.

6. **Business Analyst**: Business analysts have the lowest median salary and the narrowest range of earnings.

**Overall Trends**:

- Senior roles generally have higher median salaries and wider salary ranges compared to junior roles.
- Data scientists and data engineers tend to have similar salary distributions, suggesting comparable earning potential.
- Business analysts have the lowest earning potential among the roles shown.