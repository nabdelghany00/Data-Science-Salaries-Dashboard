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

---

### 📃 2. **Data**
- The **raw data source** for the entire dashboard.
- Filters out rows with **null or zero salaries**.
- Includes cleaned and transformed columns such as standardized **job titles**, **countries**, and **job types**.

  ![image](https://github.com/user-attachments/assets/6ca773f4-0313-4f92-a281-499df7bd49d6)

---

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

---

### 📚 4. **Jobs**
- Contains a list of **unique job titles** with their respective **median salaries**.
- Used to compare salaries based on job titles filtered through the dashboard.
- 💡 Contains logic to distinguish between:
  - General median salaries for all jobs.
  - Median salaries specific to the job title selected in the dashboard (via `D2`).
- 🔎 **Example Formula**:
  ```excel
  =XLOOKUP(title1, D2:D11, E2:E11)

![image](https://github.com/user-attachments/assets/058da083-4972-46d7-8ccf-33016fadb118)

---

### 🌍 5. **Country**
- This worksheet focuses on analyzing salaries by **Country**.
- 🧠 Calculates and displays the **median salary per country**, dynamically adjusted based on filters selected in the dashboard.
- 🧩 Filters are applied using the selected **Country** in the dashboard interface:
  - Only rows where the dataset's country matches the value of the selected country in the dashboard are considered.
- 📊 Output columns include:
  - List of countries
  - Corresponding median salary for each
- 💡 Designed to support side-by-side comparison of country-level insights:
  - When `D2` (selected job title) **equals** a job title in the dataset ➝ show salary specific to that role in that country
  - When `D2` **does not equal** a job title ➝ show general salary trends by country
- 🔁 Enables dashboard charts and metrics to reflect **localized economic patterns** for Data Science roles.

![image](https://github.com/user-attachments/assets/2f5ae859-7fe7-43d1-906e-d4653f8fc9b3)


---

### 👥 6. **Type**
- Focuses on **Job Types** such as:
  - Full-time
  - Part-time
  - Internship
  - Contract
- Calculates **median salaries** and **job distributions** by type.
- 💡 Contains logic to distinguish between:
  - General median salaries for all job types.
  - Median salary specific to the job type selected in the dashboard (via `E2`).
  - Generates an insightful Bar Chart in the Dashboard workbook diplaying the highest median salaries based on the job type available according to the selected job title and country.
    
- 📊 Useful for analyzing salary trends across different employment formats.
- Updates dynamically if:
  - `Job Type = selected type`
  - `Job Title = selected job title`
  - `Job Country = selected job country`
 
    ![image](https://github.com/user-attachments/assets/a5c841da-34e6-4889-84f6-087b4f873a95)


---

### 🔗 7. **Platform**
- Displays **unique job platforms** (e.g., "via LinkedIn", "via Indeed") and their **count of job postings**.
- 🔍 Filtered by:
  - 🎯 `Job Title = selected title`
  - 📅 `Job Type = selected type`
  - 🌍 `Country = selected country`
- 📉 Sorted **descendingly** to highlight the most-used platforms.
- Enhances user understanding of where jobs are most commonly listed.
- The selected cell shows you the highest job platform resulted according to the desired job title, job country, and job type.
- The selected cell main functionality focuses on substitutiong the "Via" keyword into a blank space showing the job platform solely.
- 🔎 **Example Formula**:
  ```excel
  =SUBSTITUTE(D2,"via","")

![image](https://github.com/user-attachments/assets/338ae98c-70e5-4ddb-9003-9e1f9b33b742)


---

## ⚖️ Functional Highlights
- 🧩 **Interactive Filtering**: 
  - Job Title, Country, and Job Type filters are created using **data validation** lists driven by the **Validation** worksheet.
- 📊 **Dynamic Calculations**:
  - Core functions used: 
    - `XLOOKUP()` for retrieving values
    - `COUNTIFS()` for filtered counting
    - `SORT()` to rank values like top platforms
- 🖥️ **Visual Feedback**:
  - Charts and summary cards are tied to dynamic inputs
  - All metrics refresh automatically as selections are changed
- 🎯 **Use of Named Ranges**:
  - Some formulas utilize named ranges for better structure and readability

---

## 🎨 Color and Formatting Tips
- 📊 **Charts**:
  - Use color-coded bars or lines
  - Label axes clearly for readability

---

## 🔄 Future Enhancements
- 🧠 Add **Pivot Charts** or **Slicers** for deeper analysis

---

## 📅 Final Notes
- ✅ Double-check cell references for consistency and absolute references
- 📌 Keep **Validation worksheet** synced with the raw dataset

---

**👤 Created By**: [Nour Abdelghany]  




