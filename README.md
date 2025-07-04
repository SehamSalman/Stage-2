# 🧠 Learning Management System (LMS) — Data Management & Governance

A project focused on organizing and managing educational data for the LMS platform by applying data governance and data quality frameworks. It follows best practices such as DAMA-DMBOK and aligns with PDPL (Personal Data Protection Law) standards.

---

## 📂 Project Structure

- **Business Requirements**  
  Documented stakeholder needs and expectations from the LMS data.

- **Data Sources & Ingestion**  
  Data was ingested from PostgreSQL, MySQL, and CSV files using Airbyte.

- **Data Profiling & Quality Rules**  
  Analyzed data structure, profiled datasets, and applied custom data quality rules.

- **Metadata Management**  
  Created a business glossary with term classifications (CDE, PII), and uploaded it to a metadata management platform.

- **Dashboards & Insights**  
  Built dashboards to monitor attendance, student status, data quality, and overall program performance.

---
## 🏗️ System Architecture

1. Data Ingestion
   ├── PostgreSQL (LMS system)
   ├── MySQL (Local stage 1)
   └── CSV files (Attendance records)

2. Centralized Storage
   └── MySQL on AWS RDS

3. Data Preparation & Cleaning
   ├── Handle missing values
   ├── Remove duplicates
   ├── Standardize formats
   └── Merge datasets

4. Data Profiling & Quality Rules
   ├── Null checks
   ├── Field validation (e.g., email format)
   └── Rule enforcement for critical fields

5. Metadata Management
   ├── Glossary creation
   ├── Term classification (PII, CDE)
   └── Lineage documentation

6. Governance & PDPL Compliance
   ├── Data masking (names, emails)
   ├── Access control
   └── User rights (edit/delete data)

7. Dashboards & Analytics
   ├── Student status tracking
   ├── Attendance patterns
   └── Program-level performance metrics


---

## 📊 Data Quality Dashboard

This dashboard provides a summary of key data quality metrics calculated from the LMS datasets.  
It highlights:

- ✅ **Completeness** – percentage of non-missing data per column  
- 🔁 **Uniqueness** – percentage of distinct values per column  
- 📄 **Rows Processed** – total number of records analyzed  

![Data Quality Dashboard](https://raw.githubusercontent.com/SehamSalman/Stage-2/main/images/Data%20quality%20Dashboard.png)

---

## 📘 Metadata & Privacy Masking – Users Table

The table below describes the key attributes from the `users` table, their business meaning, classification, and whether masking is required to ensure privacy compliance (e.g., under PDPL).

| **Attribute**  | **Data Type** | **Description**                                | **Classification** | **Masking** |
|----------------|---------------|------------------------------------------------|---------------------|-------------|
| id             | Bigint        | Unique user identifier                         | Master Data         | ✅ Yes       |
| role           | Text          | Role of the user (e.g., student)               | Master Data         | ❌ No        |
| email          | Text          | Email address of the user                      | Master Data         | ✅ Yes       |
| client_id      | Text          | ID of the associated client or organization    | Master Data         | ✅ Yes       |
| last_name      | Text          | User’s last name                               | Master Data         | ❌ No        |
| first_name     | Text          | User’s first name                              | Master Data         | ❌ No        |
| student_id     | Text          | System-generated or formal student ID          | Master Data         | ✅ Yes       |

> 💡 Masking for sensitive fields like `email`, `id`, and `student_id` is done using star characters (`*****`) to protect personally identifiable information (PII).

![Data Masking Example](https://raw.githubusercontent.com/SehamSalman/Stage-2/main/images/Masking%20Example.png)


---

## ✅ Data Quality Rules & Observations

To ensure data quality across the LMS datasets, we identified a set of **Critical Data Elements (CDEs)** and defined validation rules for each.

The table summarizes:

- The **CDE** (e.g., score, email, question_id)
- The **validation rule** to ensure data integrity
- Actual **observations** from the datasets (e.g., format issues, empty fields, inconsistent values)
- The **table and column** where the issue was found


📄 **View the full list of rules and observations** here:  
[🔗 Google Sheet – Data Quality Rules & Observations](https://docs.google.com/spreadsheets/d/13jJYKG20iVjhwGZUHFfKGo6n6o8t2R84CqljN4IIcow/edit?gid=1334388161#gid=1334388161)

---

## 📈 Analytical Dashboard – Business Requirements

This dashboard provides an overview of key business metrics extracted from the LMS datasets.  
It highlights performance indicators used to evaluate program scale, student attendance, and enrollment activity.

### 📌 Key Insights:

- 🏫 **13 Programs** are actively tracked in the system.
- 👥 **913 Students** total, across two client groups:
  - **Client 1**: Former students from **Stage 1**
  - **Client 2**: Current active students
- 🧑‍💻 **920 Users** with unique LMS accounts
- 📊 **Attendance Distribution**:
  - **P (79.7%) = Present**  
  - **X (20.3%) = Absent**
- 📉 Visual comparison of program cohorts vs total enrollments
- 📋 Breakdown of student statuses: **Enrolled**, **Withdrawn**, and **Client-Specific Completed**

This dashboard supports analysis of student engagement, cohort planning, and overall program reach.

![Business Requirements Dashboard](https://raw.githubusercontent.com/SehamSalman/Stage-2/main/images/Dashboard%20Business%20Requirements.png)


## 🧰 Tools & Technologies

| Category                 | Tools Used                                     |
| ------------------------ | ---------------------------------------------- |
| Data Ingestion & ETL     | Airbyte, MySQL Workbench, Google Colab         |
| Data Storage             | AWS RDS Cloud Database                         |
| Data Visualization       | Power BI                                       |
| Reporting & Presentation | Google Sheets (reports), Canva (presentations) |
| Data Governance          | Personal Data Protection Law (PDPL) Compliance |



## 👥 Team

Seham Salman, Nawal Mohammed, Maha Sultan, Sarah Alzahrani, Mathyel Al Muteriy

---

## 📎 Presentation File

[presentation/your-presentation.pdf](presentation/your-presentation.pdf)



