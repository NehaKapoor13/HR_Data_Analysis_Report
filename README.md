# HR Data Analysis

### Project Overview
The HR report provides an overview of workforce demographics, highlighting a diverse and stable employee base with a balanced gender representation and significant racial diversity. Most employees work remotely, while others are based at headquarters. Key departments such as Engineering and Sales have the highest staffing levels. Age distribution shows a majority of employees within the mid-career age range, suggesting a seasoned workforce with a variety of backgrounds and skills.

### Data Source
HR data : The primary dataset used for this analysis is this " HR_Data.csv" file.Cointaining detailed information about each empolyee of the company.

### Tools
- Excel - Data cleaning
- sql - Data Analysis
- power bi - Creating reports

### Data Cleaning/Preparation
In the initial data preparation phase, we preformed the folloeing tasks:

- Data loadind and inspections.
- Handling missing values.
- Data cleaning and formatting.

### Exploratary Data Analysis

EDA involved exploring the hr data answering key questions, such as:

- what's the age distribution in the company?
- what's the gender breakdown in the company?
- how does gender is very across departments and job tittles?
- what's the race distribution in the company?
- what's the average length of the employment in the company?
- which department has the highest turnover rate?
     - get total count
     - get terminated count
     - terminated count/total count
- what's is the tenture diatribution for each department?
- how many employees work remotrly for each department?
- what's the distribution of employee across different states?
- how are job titles distributed in the company?
- how have employee hire counts varied over time?
    - calculates hires.
    - calculates terminations
    - (hires-treminations)/hires precent hire change

### Data Analysis

Include some interesting code/features worked with

```sql
select
department,total_count,
terminated_count,
round((cast(terminated_count as float)/total_count) ,2)*100as turnover_rate
from(select  
department, count(*) as total_count,
sum(case
    when new_termdate is not null and new_termdate<= getdate() then 1 else 0
	end) as terminated_count
from hr_data
group by department) as subquery
order by  turnover_rate desc;
```

### Result/ Findings

Based on the analysis, recommended the following actions

- according to data emoployees are between 22 to 59 age groups.
- focus on the empolyee result the gender determins the females are 9942 and the male candidates 10864.
- gebder according to job titiles and departments about found out 600 employees.
- White, Two or More Races, Black or African American, Asian, Hispanic or Latino, American Indian or Alaska Native, Native Hawaiian or Other Pacific Islander those the part that are enable in the race distribution.
- the average length of the employment in the company is 8.
- the highest turnover rate is auiditing that is 4.
- the tenture diatribution for each department is 7 to 10 tenture range.
- Headquarters - 16080  and the remote is 5304.
- the 17330 is highest employees are working in ohio.
- by the categorical distributions are preformed in job titiles that can be separated the results.
- in tear of 2020 is the most hire chage is recorded is 100 percente.


### Recommendations

Based on the analysis, recommanded the following actions:

- calculate the age and gender distributions that founding the better results.
- male and female employees are the main analysis part that can be separated value.
- in tha analysis i can be separete the terminations that can be provide meaningful insights.
- in year by year the that cange of hire is increaded at 100%.




✨
😎

