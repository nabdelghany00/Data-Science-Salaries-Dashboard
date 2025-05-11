# 🚀 README: Data Science Salary Dashboard (Excel)

---

## 📄 Overview
This Excel dashboard provides a visual and interactive summary of job data in the Data Science field. It allows users to filter results dynamically based on job title, country, and job schedule type (e.g., full-time, part-time), and view insights such as median salary, job count, and top job platforms.

---

## 📂 Workbook Structure
The Excel file is organized into multiple worksheets:

### 📊 1. **DS Salary Dashboard**
- This is the **main dashboard interface**.
- Contains drop-down inputs for filtering by **Job Title**, **Country**, and **Job Schedule Type**.
- Displays:
  - 🌐 A horizontal bar chart for average salaries by job title.
  - 🌏 A world map visualization based on country.
  - 📈 A bar chart showing salary ranges by job schedule types.
  - 💸 Average salary KPI.
  - 📊 Job count KPI.
  - 🔹 Top job platform KPI.
 
    ![image](https://github.com/user-attachments/assets/05b33d9c-f699-49b2-aaa5-f2796cd1e2b3)


### 📃 2. **Data**
- The **raw data source** for the entire dashboard.
- Filters out rows with **null or zero salaries**.
- Includes cleaned and transformed columns such as standardized **job titles**, **countries**, and **job types**.

  ![image](https://github.com/user-attachments/assets/6ca773f4-0313-4f92-a281-499df7bd49d6)


### 🔢 3. Validation

🔧 Used for data validation and contains reference fields that power all drop-down selections in the dashboard.

Contains dynamically filtered and sorted fields:

💼 Unique Job Titles: Extracted based on selected filters in the dashboard (Country, Job Type), and includes a count column next to each job title.

🌍 Unique Countries: Extracted and sorted alphabetically.

👥 Unique Job Types: Grouped uniquely and categorized by keywords (e.g., full-time, part-time, internship).

✨ Key Formula Functionality:
In the job count column, a dynamic XLOOKUP function is applied. For example:

=XLOOKUP(title1, D2:D11, E2:E11)

This formula retrieves the count value associated with a specific job title (title1) from the defined lookup array D2:D11 and returns the result from the corresponding array E2:E11.

🔁 This ensures the dashboard dynamically updates the job count whenever the selected filters change.

![image](https://github.com/user-attachments/assets/0a4d79e1-08c5-450e-b29f-e06b925ec760)


### 📚 4. **Jobs**
- Holds **Job Titles** and their corresponding **Median Salaries**.
- Also contains **sorted median salaries** for comparative insights.
- 🔎 **Formula Example**:
  ```excel
  =XLOOKUP(title1, D2:D11, E2:E11)
