# Top-N Analysis Using Ranking Window Functions

📚 **Author**: Ibrahim Ambale | ExploreAI Academy  
⚠️ **Note**: This notebook **cannot run on Google Colab** due to its dependency on a **local MySQL database** (`united_nations`). Please ensure it runs on the same machine where **MySQL Workbench** and the **united_nations** database are installed.

---

## 📌 Learning Objectives

In this notebook, you will learn:

- How to use `ROW_NUMBER()` and `RANK()` functions for **ranking rows**.
- How to apply **partition-wise ranking** operations using SQL.
- The difference between `ROW_NUMBER()` and `RANK()` results.
- How to perform **Top-N analysis** using window functions.

---

## 🗂 Overview

This notebook explores the use of **SQL ranking functions** to identify and order countries based on specific criteria.

### 🧠 Use Case:

You want to identify the **Top-N countries** with the **lowest or highest** access to **managed drinking water services per year**. Ranking functions are perfect for this type of analytical task.

---

## 🛠 Dataset & Setup

We are using the `Access_to_Basic_Services` table from the **united_nations** MySQL database.  
This table includes:

- Country
- Year
- Subregion
- Access to managed drinking water services

> Make sure your MySQL server is running and the database is properly set up before using this notebook.

---

## 🧪 Sample Query for Top-N Analysis

```sql
SELECT 
    Country,
    Year,
    Access_to_Water,
    RANK() OVER (PARTITION BY Year ORDER BY Access_to_Water ASC) AS Rank
FROM Access_to_Basic_Services;
```
---
## 💡 Why Use Ranking Functions?
ROW_NUMBER() gives a unique rank to each row.

RANK() gives the same rank to tied values, leaving gaps in the sequence.

Ideal for Top-N reporting, leaderboards, and trend analysis.
---
## 🔌 Prerequisites
- A local MySQL installation with:

  - MySQL Workbench
  
  - united_nations database

- Python libraries (for notebook execution):

  - mysql.connector or pymysql
  
  - pandas
  
  - sqlalchemy (optional)
---
🧠 Final Thoughts
SQL ranking window functions are powerful tools for identifying trends, outliers, and top/bottom performers in your dataset.
Use them to gain deeper insights into your data while maintaining the row-level granularity.

Happy ranking! 🚀

