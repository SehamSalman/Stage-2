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

Visualizes data issues such as missing values, duplicates, invalid formats, and overall compliance with quality rules.

> 🖼️ **Insert your data quality dashboard screenshot here**

```markdown
![Data Quality Dashboard]([images/data_quality_dashboard.png](https://github.com/SehamSalman/Stage-2/blob/main/images/Data%20quality%20Dashboard.png))
```

---

## 📘 Glossary & Term Classification

A business glossary was developed including:

* Clear term definitions
* Classification for sensitive data like PII (Personally Identifiable Information) and CDE (Critical Data Elements)
* Mapping of terms to relevant datasets and business processes

> 🖼️ **Insert your glossary/tool screenshot here**

```markdown
![Glossary Example](images/glossary.png)
```

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


