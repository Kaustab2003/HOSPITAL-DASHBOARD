# 🏥 End-to-End Dashboard Project in Excel

A complete, end-to-end **Hospital Emergency Room Analysis Dashboard** built in Excel/Power BI to improve operational efficiency and provide actionable insights for healthcare stakeholders.

---

## 📌 Project Purpose

This project creates a **Hospital Emergency Room Analysis Dashboard** to help stakeholders:

- Monitor and analyze patient flow in real time
- Make data-driven decisions for patient management
- Improve overall emergency room services and efficiency

---

## 🗂️ Project Steps

The project follows an end-to-end workflow:

1. **Data Collection** – Gather raw hospital emergency room data
2. **Data Preparation** – Clean and transform data for analysis
3. **Calendar Table Setup** – Build a date dimension table
4. **DAX Formula Creation** – Define calculated columns and measures
5. **Chart & Visual Design** – Build KPI visuals and charts
6. **Dashboard Assembly** – Combine all elements into a final interactive dashboard

---

## 📊 KPIs Tracked

The dashboard monitors key performance indicators (KPIs) for the emergency room, including:

- Total number of patients
- Admission vs. non-admission rates
- Patient wait time performance (within 30 minutes)
- Patient demographics (age groups, gender)
- Department referral volumes

---

## 📈 Charts & Visuals

| Chart | Description |
|---|---|
| **Patient Admission Status** | Shows how many patients were admitted vs. not admitted |
| **Patient Age Distribution** | Groups patients into age brackets |
| **Timeliness** | Measures the percentage of patients seen within 30 minutes |
| **Gender Analysis** | Displays patient count by gender |
| **Department Referrals** | Identifies the most frequently referred departments |

---

## 🗓️ Calendar Table

A custom calendar table was created using the following Power Query formula to generate a 2-year date range:

```powerquery
= List.Dates(#date(2023,01,01), 731, #duration(1,0,0,0))
```

> This generates 731 consecutive days starting from January 1, 2023, covering the full 2-year analysis period.

---

## 🧮 DAX Formulas

### Age Group Classification

Groups patients into meaningful age brackets for demographic analysis:

```dax
= IF([Patient Age] >= 70, "70-79",
  IF([Patient Age] >= 60, "60-69",
  IF([Patient Age] >= 45, "45-59",
  IF([Patient Age] >= 30, "30-44",
  IF([Patient Age] >= 15, "15-29",
  IF([Patient Age] >= 5,  "05-14",
                          "0-4"))))))
```

### Patient Attendance Status

Flags whether a patient was seen within the target wait time:

```dax
= IF([Patient Waittime] < 30, "Within Time", "Delay")
```

---

## 🖥️ Final Dashboard

The final dashboard consolidates all KPIs, charts, and filters into a single interactive view, enabling emergency room managers and stakeholders to:

- Track real-time patient flow
- Identify bottlenecks in wait times
- Analyze demographic trends
- Optimize department resource allocation

---

## 🛠️ Tools & Technologies

- **Microsoft Excel** – Data modeling and dashboard layout
- **Power Query (M Language)** – Data transformation and calendar table
- **DAX (Data Analysis Expressions)** – Calculated columns and measures
- **Power BI** – Dashboard visualization and interactivity

---

## 📁 Project Structure

```
📦 End-to-End Dashboard Project
 ┣ 📊 Raw Data File
 ┣ 📅 Calendar Table
 ┣ 🧮 DAX Measures
 ┣ 📈 Charts & Visuals
 ┗ 🖥️ Final Dashboard
```

---

## 👤 Author

> This project was built as a complete end-to-end data analytics solution for hospital emergency room management.
