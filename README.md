# 📊 Student Depression Analysis - Tableau Dashboard

This repository showcases an interactive **Tableau dashboard** analyzing factors related to student depression using data stored in **Microsoft SQL Server**. The project includes SQL data transformations and visual storytelling through Tableau Public.

---

## 🔗 Tableau Dashboard Link

👉 [Click here to view the Tableau Dashboard](https://public.tableau.com/views/studentdashboard_17503589357300/DASHBOARD?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## 📂 Project Overview

- 📌 **Title:** Student Depression & Mental Health Dashboard  
- 📅 **Duration:** July 2022 – January 2025  
- 👨‍💼 **Analyst:** Anuj Agarwal  
- 💼 **Client (Contractor Role):** Dazzling Diamonds  
- 🔧 **Role:** Power BI & Tableau Analyst (Contract)  

---

## 🗃️ Dataset Summary

- **Source:** Internal dataset (`Depression+Student+Dataset`)
- **Total Columns:** Various indicators related to mental health
- **Key Fields:**
  - `Age`
  - `Sleep Duration`
  - `Study Hours`
  - `Academic Pressure`
  - `Financial Stress`
  - `Study Satisfaction`
  - `Student Count`

---

## 🧮 SQL Server Transformations

All SQL operations were performed on the table:  
`[dbo].[Depression+Student+Dataset]`

### 🔸 Add Index Column

```sql
ALTER TABLE [dbo].[Depression+Student+Dataset]
ADD Index_Column INT IDENTITY(1,1);
```

### 🔸 Add and Populate Age Group

```sql
ALTER TABLE [dbo].[Depression+Student+Dataset]
ADD Age_group VARCHAR(MAX);

UPDATE [dbo].[Depression+Student+Dataset]
SET Age_group = 
  CASE 
    WHEN Age BETWEEN 18 AND 24 THEN 'A1'
    WHEN Age BETWEEN 25 AND 30 THEN 'A2'
    ELSE 'A3' 
  END;
```

### 🔸 Grouped Age Count Query

```sql
SELECT Age_group, COUNT(*) AS Count
FROM [dbo].[Depression+Student+Dataset]
GROUP BY Age_group
ORDER BY Count DESC;
```

---

## 📊 Dashboard Visualizations in Tableau

The dashboard includes:

- 🍩 **Bubble Chart**: Sleep Duration vs Student Count  
- 📈 **Line Chart**: Study Hours vs Student Count  
- 📊 **Bar Charts**:  
  - Study Satisfaction vs Student Count  
  - Academic Pressure vs Student Count  
  - Financial Stress vs Student Count  

All charts are interactive and auto-refresh on database updates.

---

## 🔌 Data Connectivity

- 🧩 Tableau is connected to **SQL Server Management Studio**
- 🧪 Live data fetched via SQL queries
- 🔁 Changes in SQL are automatically reflected in Tableau
- 📌 Dashboard built using `.twb` file format

---

## 📁 Repository Contents

| File Name                                           | Description                            |
|----------------------------------------------------|----------------------------------------|
| `Depression+Student+Dataset.csv`                   | Original dataset                       |
| `depression student dataset modified.csv`          | Cleaned/updated version of dataset     |
| `student dashboard.twb`                            | Tableau workbook file                  |
| `depression student dataset database changes file.txt` | SQL scripts used in SQL Server     |

---

## 👤 Author

**Anuj Agarwal**  
Data Analyst | Power BI & Tableau Expert  
🛠 Worked as a contractor at **Dazzling Diamonds** (July 2022 – Jan 2025)

📧 Email: *[Your Email Here]*  
🌐 GitHub: [github.com/anuj489](https://github.com/anuj489)