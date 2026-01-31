# 🚀 Zenvy Payroll SaaS - Project Documentation

## 📝 Project Overview
Zenvy Payroll SaaS is a comprehensive human resources and financial management tool designed to streamline payroll processing, track employee attendance, and provide deep analytical insights into workforce costs. This project covers the end-to-end data lifecycle—from raw CSV processing to professional interactive business intelligence dashboards.

---

## 🏗️ Project Architecture & Workflow

### 1. Data Processing & Analytics (`app.ipynb`)
The project starts with a robust Python-based analytical pipeline:
- **Data Integration**: Merges `zenvy_employees.csv`, `zenvy_payroll.csv`, and `zenvy_attendance.csv` into a master dataset.
- **Feature Engineering**: Calculates critical KPIs like:
    - `attendance_ratio`: (Present Days / Working Days) * 100
    - `allowances`: Gross Salary - Base Salary
- **Date Dimension**: Extracts `Day`, `Month`, `Month Name`, `Quarter`, and `Year` for time-series analysis.
- **Data Export**: Generates `zenvy_master_for_powerbi.csv`, which serves as the clean source for the dashboard.

### 2. Power BI Dashboard (`Zenvy_Dashboard_Documentation.md`)
A professional 2-page dashboard designed for executive and departmental decision-making.

#### **Page 1: Executive Payroll Intelligence** 👑
Focuses on the "Big Picture" for CEOs and CFOs.
- **KPIs**: Total Cost, Actual Payout, Deductions, and Total Workforce.
- **Visuals**: Salary Frequency Analysis, Headcount by Designation, and Net Salary Trends.

#### **Page 2: Department-wise Expenses & Efficiency** 🏢
Focuses on team-level performance and cost efficiency.
- **KPIs**: Dept Count, Overtime Hours, Avg Attendance, and Total Allowances.
- **Visuals**: Dept Expense Share (Donut), Overtime Analysis by Role, and Detailed Compensation Ledgers.

---

## 🔢 Core DAX Measures (The Formulas)
*Created to ensure dynamic, real-time reporting:*

| Metric | Formula |
| :--- | :--- |
| **💰 Total Payroll Cost** | `SUM(gross_salary)` |
| **💸 Actual Payout** | `SUM(net_salary)` |
| **📉 Total Deductions** | `SUM(tax_deduction) + SUM(pf_deduction)` |
| **👥 Total Employees** | `DISTINCTCOUNT(employee_id)` |
| **🏢 Total Departments** | `DISTINCTCOUNT(department)` |
| **🕒 Total Overtime** | `SUM(overtime_hours)` |
| **📈 Avg Attendance %** | `AVERAGE(attendance_ratio)` |

---

## 🎨 Design System & UI/UX
- **Modern Aesthetics**: Premium Dark Mode UI with Glassmorphism effects.
- **Custom Backgrounds**: Professionally designed layouts (`page2_bg_pro_with_title.png`) with designated visual slots.
- **Emoji-Driven Design**: Uses modern icons (📊, 💠, 💰) in all titles and labels for a mobile-first, high-end feel.
- **Interactivity**: Fully synced slicers (Month & Department) allowing cross-page filtering.

---

## 📂 File Structure
- `app.ipynb`: Core Python analytical notebook.
- `zenvy_master_for_powerbi.csv`: Final processed dataset.
- `Zenvy_Dashboard_Documentation.md`: Detailed dashboard setup guide.
- `mock_dashboard_visuals/`: Directory containing interactive Plotly HTML renderings.
- `page1_bg.png` & `page2_bg.png`: High-resolution dashboard background assets.

---
*Developed for Zenvy Payroll SaaS - Strategic Workforce Analytics.*
