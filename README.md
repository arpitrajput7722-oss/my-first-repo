# Salesforce Mini Project – Student Attendance & Fee Tracker

## 📌 Problem Statement
Schools and coaching institutes often face challenges in **tracking student attendance and fee payments**. Manual tracking leads to errors, delays, and poor reporting.  
This project aims to build a **Salesforce-based Student Attendance & Fee Tracker** that simplifies record keeping, automates reminders, and provides clear dashboards for management.

---

## 🎯 Objectives
- Automate student attendance management.
- Track fee payments with reminders for due dates.
- Provide dashboards and reports for quick insights.
- Ensure stakeholders (Admin, Teachers, Parents) can view necessary information.

---

## 🛠️ Core Objects & Relationships
- **Student (Custom Object)** – stores student details.  
- **Attendance (Custom Object)** – linked to Student.  
- **Fee (Custom Object)** – linked to Student.  
- **Teacher (Custom Object)** – linked to Attendance.  

Relationships:  
- One Student → Many Attendance Records  
- One Student → Many Fee Records  

---

## 🚀 Key Features
- **Flows:** Auto-generate attendance records daily.  
- **Validation Rules:** Ensure no duplicate fee entries.  
- **Reports/Dashboards:** Attendance % by student/class, Fees collected vs pending.  
- **Email Alerts:** Parents get reminder emails for pending fees.  

---

## 🎥 Demo Flow
1. Add new student → Auto-generated unique Student ID.  
2. Mark attendance via a form (Teacher entry).  
3. Enter fee payment → Automatic status update.  
4. Dashboard shows:  
   - Top defaulters (pending fees).  
   - Monthly attendance % report.  

---

## ✅ Why this Project?
  
- Attractive demo with dashboards and automation.  
- Practical use case (every school/college faces this).  

---

## 📂 Repository Structure
- `problem-statement.md` → Detailed problem description  
- `requirements.md` → Functional & Non-functional requirements  
- `stakeholders.md` → Stakeholder analysis  
- `use_cases.md` → Industry use case mapping  
- `appexchange.md` → Related Salesforce AppExchange tools  
- `mock-data.csv` → Sample student & fee dataset  
- `demo-plan.md` → Final demo script  
-
