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

## ✅ Data Quality Rules

Examples of applied data quality rules:

* Mandatory field checks (e.g., student ID, attendance date)
* Format validations (e.g., email, phone numbers)
* Logic rules (e.g., graduation date should be after enrollment)

> 🖼️ **Insert your data rule list screenshot here**

```markdown
![Data Quality Rules](images/data_quality_rules.png)
```

---

## 📈 Analytical Dashboards

Dashboards created to monitor:

* **Student Status** (Current, Withdrawn, Graduated)
* **Attendance Tracking**
* **Program Metrics** (e.g., pass/fail rates, completion ratios)

> 🖼️ **Insert your Power BI or Excel dashboard screenshots here**

```markdown
![Trainee Status Dashboard](images/trainee_status_dashboard.png)
```

---

## 🧰 Tools & Technologies

| Category            | Tools Used                 |
| ------------------- | -------------------------- |
| ETL / Ingestion     | Airbyte, Python            |
| Visualization       | Power BI, Excel            |
| Metadata Management | DataHub / OpenMetadata     |
| Storage             | AWS RDS, PostgreSQL, MySQL |
| Governance          | DAMA-DMBOK, PDPL           |

---

## 👥 Team

> Add team members and roles if applicable
> Example:
>
> * **Sara A.** — Data Engineer
> * **Ahmed B.** — BI Developer
> * **Reem C.** — Data Governance Lead

---

## 📎 Attachments

* `docs/` — Project documentation
* `presentation/` — Final project presentation slides
* `requirements/` — Business requirements and user stories


