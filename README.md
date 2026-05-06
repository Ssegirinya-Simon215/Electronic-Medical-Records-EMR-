# 🏥 Electronic Medical Records (EMR) System
### Database Management Systems Project — Hospital Setting

![Database](https://img.shields.io/badge/Database-MySQL-blue)
![Status](https://img.shields.io/badge/Status-Complete-green)
![Course](https://img.shields.io/badge/Course-Database%20Systems-teal)

---

## 📋 Project Overview

This project presents the **design and full MySQL implementation** of an Electronic Medical Records (EMR) system for a hospital setting. It replaces paper-based patient records with a centralized, structured relational database that serves doctors, nurses, pharmacists, lab technicians, receptionists, and hospital administrators.

**System:** Electronic Medical Records (EMR)  
**Setting:** Hospital  
**Database:** MySQL  
**Tables:** 9  
**Sample Queries:** 10  
**Real-World Reference:** OpenMRS  

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `EMR_Database_Report.docx` | Full project report (10+ pages, Times New Roman 12pt, 1.5-spaced) |
| `EMR_Project_Presentation.pptx` | 12-slide project presentation |
| `EMR_ERD_and_Schema.pdf` | ERD (Section 3e) and Physical Database Schema (Section 3g) |
| `EMR_Workbook_Week5.docx` | Week 5 Relational Algebra & Calculus workbook answers |
| `emr_create_tables.sql` | All 9 CREATE TABLE statements with constraints |
| `emr_insert_data.sql` | Sample INSERT data for all tables |
| `emr_sample_queries.sql` | 10 sample SQL queries with comments |
| `README.md` | This file |

> 📹 **Presentation Video:** [Link to be added after upload]

---

## 🗄️ Database Schema

The EMR database (`emr_hospital`) consists of **9 interrelated tables**:

```
patients          → Central entity. All records link back here.
doctors           → Attending physicians and specialists.
nurses            → Ward nursing staff.
wards             → Hospital wards and their capacities.
appointments      → Patient–doctor appointment bookings.
medical_records   → Diagnoses and treatment records.
prescriptions     → Medication prescriptions per medical record.
lab_tests         → Laboratory test orders and results.
admissions        → Patient ward admission and discharge tracking.
```

### Key Relationships
- **patients** ← 1:M → **appointments** ← M:1 → **doctors**
- **appointments** ← 1:1 → **medical_records** ← 1:M → **prescriptions**
- **patients** ← 1:M → **lab_tests** ← M:1 → **doctors**
- **patients** ← 1:M → **admissions** ← M:1 → **wards** ← 1:M → **nurses**

---

## ⚙️ How to Set Up the Database

### Requirements
- MySQL 8.0 or higher
- MySQL Workbench (recommended)

### Steps

**1. Create the database**
```sql
CREATE DATABASE IF NOT EXISTS emr_hospital;
USE emr_hospital;
```

**2. Run the table creation script**
```sql
-- Run emr_create_tables.sql in MySQL Workbench
source emr_create_tables.sql;
```

**3. Load sample data**
```sql
-- Run emr_insert_data.sql
source emr_insert_data.sql;
```

**4. Run sample queries**
```sql
-- Run emr_sample_queries.sql
source emr_sample_queries.sql;
```

---

## 🔍 Sample Queries Included

| # | Query | Purpose |
|---|-------|---------|
| Q1 | List all patients | Basic patient retrieval |
| Q2 | Appointments for a specific doctor | Doctor schedule view |
| Q3 | Patient load per doctor | Workload monitoring |
| Q4 | Full medical history for a patient | Clinical review |
| Q5 | Active prescriptions for a patient | Pharmacy dispensing |
| Q6 | Patients admitted to a specific ward | Nurse ward management |
| Q7 | Lab tests for a patient | Lab result review |
| Q8 | Most common diagnoses | Disease trend analysis |
| Q9 | Patients with no lab tests | Screening flagging |
| Q10 | Monthly appointment report | Performance reporting |

---

## 🏢 Business Case Summary

| Item | Detail |
|------|--------|
| **Problem** | Paper-based records are slow, error-prone, and hard to share across departments |
| **Solution** | Centralized MySQL EMR database accessible by all hospital staff |
| **Tangible Benefits** | Eliminates paper costs, reduces medication errors, faster processing |
| **Intangible Benefits** | Better care quality, improved security, regulatory compliance |
| **Estimated Cost** | $11,500 – $33,000 |
| **ROI** | Achieved within 12–18 months |

---

## 🌍 Real-World Reference

This project draws insights from **OpenMRS** (Open Medical Record System), deployed in 40+ countries including Uganda, Kenya, Rwanda, and South Africa. Key lessons applied:
- Patient-centric data model (patient_id as central FK)
- Role-based access control (separate UI per user group)
- Separate Appointments and Medical Records tables (Visit vs Encounter model)

---

## 📚 Bibliography

1. Connolly, T. & Begg, C. (2015). *Database Systems* (6th ed.). Pearson.
2. Silberschatz, A., Korth, H. F., & Sudarshan, S. (2019). *Database System Concepts* (7th ed.). McGraw-Hill.
3. MySQL Documentation. (2024). MySQL 8.0 Reference Manual. Oracle Corporation.
4. OpenMRS. (2024). OpenMRS Platform Documentation. https://openmrs.org
5. HealthIT.gov. (2023). What is an EHR? https://www.healthit.gov

---

## 👤 Author

**Course:** Database Management Systems  
**System:** Electronic Medical Records — Hospital Setting  
**Instructor:** Kenneth Baguma  

---

*All work in this repository is original and was developed as part of the Database Management Systems semester-long project.*
