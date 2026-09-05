# Family Pulse Dashboard

### Dashboard Over
<img width="1342" height="735" alt="Screenshot 2026-09-05 210729" src="https://github.com/user-attachments/assets/d5a53c74-07af-4906-847a-9dc67f0965cd" />

---
An interactive Power BI dashboard designed to analyze and visualize humanitarian family demographics, housing conditions, breadwinner statistics, and income across multiple regions (Syria, Yemen, Iraq, Libya).

---

## Dashboard Overview

![Family Pulse Dashboard](Screenshot%202026-09-05%20210729.jpg)

### Key Metrics & KPIs
* **Total Members:** 11,905
* **Total Families:** 1,701
* **Total Income:** $143K
* **Gender Breakdown:** 55% Male / 45% Female
* **Total Cities Covered:** 19

---

## Project Stages & Implementation

### Stage 1: Data Extraction & Transformation (Power Query)
1. **Data Ingestion:** Imported raw datasets containing family member records, housing types, breadwinner status, income figures, and location details.
2. **Data Cleaning:**
   * Handled missing values and standardized data formats (e.g., set Income as Currency, counts as Whole Numbers).
   * Corrected typos and standardized country text fields (e.g., standardizing "Lybia" / "Libya").
3. **Data Modeling:**
   * Established one-to-many relationships between Dimension tables (Geography, Housing Types, Gender) and Fact tables (Family records).

---

### Stage 2: DAX Calculations & Key Measures
Implemented Data Analysis Expressions (DAX) to compute high-level indicators dynamically:

```dax
// Total Members Count
Total Members = SUM(FamilyData[MemberCount])

// Total Families Count
Total Families = COUNTROWS(FamilyData)

// Total Income Measure
Total Income = SUM(FamilyData[Income])

// Gender Percentages
PCT Male = DIVIDE(CALCULATE(COUNT(Members[ID]), Members[Gender] = "Male"), COUNT(Members[ID]))
PCT Female = DIVIDE(CALCULATE(COUNT(Members[ID]), Members[Gender] = "Female"), COUNT(Members[ID]))
Stage 3: Visual Layout & Dashboard Design
