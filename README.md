# 📊 HR Analytics Dashboard (Power BI)

## 📌 Project Overview
This project is an interactive HR Analytics Dashboard built using Power BI to analyze employee attendance, Work From Home (WFH), and Sick Leave (SL) trends.

The dashboard helps HR teams monitor employee presence, identify work patterns, and make data-driven decisions.

---

## 🎯 Objectives
- Track employee attendance performance
- Analyze Work From Home (WFH) trends
- Monitor Sick Leave (SL) patterns
- Provide actionable insights using data visualization

---

## 🛠 Tools & Technologies
- Power BI (Data Visualization)
- Excel (Data Source)
- DAX (Data Analysis Expressions)

---

## 📂 Dataset Information
The dataset contains:
- Employee ID
- Attendance Status (P, WFH, SL, WO, HO)
- Date-wise records

---

## 📊 Key Metrics (DAX Measures)

### 🔢 Total Working Days
DAX
Total Working Days =
VAR totaldays = COUNT('Final Data'[Value])
VAR nonworkdays =
    CALCULATE(
        COUNT('Final Data'[Value]),
        'Final Data'[Value] IN {"WO", "HO"}
    )
RETURN
    totaldays - nonworkdays

### 🟢 Present Days

Present Days =
VAR presentdays =
    CALCULATE(
        COUNT('Final Data'[Value]),
        'Final Data'[Value] = "P"
    )
RETURN
    presentdays + [WFH Count]

### 🏠 WFH Count

WFH Count = SUM('Final Data'[WFH Count])

### 🤒 Sick Leave Count

SL Count = SUM('Final Data'[SL Count])

### 📊 Presence %

Presence % = 
DIVIDE(
    [Total Present Days],
    [Total Working Days]
) * 100

### 🏠 WFH %

WFH % = 
DIVIDE(
    [Total WFH Days],
    [Total Working Days]
) * 100

### 🤒 Sick Leave %

Sick Leave % = 
DIVIDE(
    [Total Sick Leave Days],
    [Total Working Days]
) * 100

### 📊 Attendance %

Attendance % =
DIVIDE(
    [Present Days],
    [Total Working Days],
    0
)

## 📈 Dashboard Features
- 📅 Attendance trend over time: ~91%
- 🏠 Work From Home (WFH) analysis: ~10%
- 🤒 Sick Leave tracking: ~1%
- 👩‍💼 Employee-level performance insights
- 📊 KPI cards for quick overview

📷 Dashboard Preview


