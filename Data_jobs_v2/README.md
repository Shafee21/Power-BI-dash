# Data Jobs Dashboard v2 w/ Power BI

![Dashboard Page 2](/Data_jobs_v2/Dashboard.png)

## Introduction

This dashboard (V2.0) was created as part of the second phase of **Luke Barousse’s Power BI tutorial**, focusing on more advanced techniques. It builds on earlier work by incorporating **DAX measures**, **merge queries**, **parameter-driven filtering**, and additional **Power Query transformations**.

Using a **2024 dataset of data science job postings**, the dashboard explores patterns in **job titles**, **salaries**, and **locations**. Designed as a **single-page report**, it provides a clean and efficient layout for users to interact with the data and uncover key insights without navigating between multiple views.

![Dashboard Page 2](/Data_jobs_v2/Dashboard.png)

This report serves as a central overview of the data job market, highlighting key metrics such as **Job Count**, **Skills per Job**, **Median Yearly Salary**, and **Median Hourly Salary**. It also includes insights on **Skill Popularity**—measured by percentage or total count—and compares **Salary trends across different Job Titles**. All visuals are presented in a compact layout to support quick and effective exploration.

### Skill Pairings Table – Custom Addition

![Skill pairing table](/Data_jobs_v2/table.png)

The middle table, **“Top Skill Pairings in Job Postings,”** is a custom feature I added to the original dashboard. While the common skills chart is helpful for identifying frequently mentioned tools (e.g. SQL, Excel), it doesn’t always offer insight into **which combinations of skills are most valuable to learn next**.

This table was built by compiling job listings that mention **multiple skills** and analyzing the most frequent pairings. For example, when filtering by the "Data Analyst" role, SQL and Excel both rank highly. However, since both are database-oriented tools, it may be more strategic to pair SQL with a **visualization tool like Tableau** or a **programming language like Python**, which also appear near the top.

The goal of this table is to highlight **complementary skill sets**, helping users better prioritize their learning paths based on how skills tend to appear together in real job postings. That said, **Excel remains an important and accessible entry point** into data analytics, and its continued demand should not be overlooked.

### How the Table Was Built

This table was created in Power Query to identify skill combinations listed within the same job.

#### Steps:

1. **Duplicated** the job-skill mapping table twice (`SkillsA` and `SkillsB`).
2. **Merged** them using an **inner join** on `job_id` to pair all skills within the same job.
3. **Expanded** to get `skill_id_A` and `skill_id_B`.
4. **Filtered out self-pairs and duplicates** using:
   ```powerquery
   keep = if [skill_id_A] < [skill_id_B] then true else false



## Conclusion

This updated dashboard (Version 2.0) highlights Power BI’s ability to turn large job posting datasets into a structured, streamlined tool for career analysis. 

It is designed to support **Job Seekers**, **Job Transitioners**, and **Job Swappers** by enabling them to filter and explore key market insights on a single page—helping them make informed decisions about their next career move.
