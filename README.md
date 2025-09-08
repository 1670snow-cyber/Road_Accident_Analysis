# 🚦 Road Accident Analysis Dashboard — Power BI Project

## 📌 Overview
This project is an **interactive Power BI dashboard** built to analyze road accident data.  
It demonstrates the full cycle of data cleaning, modelling, DAX calculations, and visualization.

---

## 🗂 Dataset
- Road accident data (CSV/Excel format).  
- Includes details like:
  - Number of accidents & casualties  
  - Severity (Fatal, Serious, Slight)  
  - Road type, weather, and light conditions  
  -  Caualties by Urban vs Rural areas  

A **Calendar table** is created in Power BI for time-based analysis.

---

## 🔧 Data Cleaning & Preparation
- Cleaned data in **Power Query**:
  - Fixed spelling error (`fetal → fatal`) in Severity column.  
- Created a **Calendar Table** using DAX:
  - Added calculated columns: Year, Month, Day, etc.  
- Established a **Many-to-One relationship** between Calendar table and Accident data table.

---

## 📐 DAX Measures
Some of the DAX measures created in the report:

```dax
-- Current Year Casualties
CY Casualties = TOTALYTD(SUM(Data[Number_Of_Casualties]),'Calender'[Data])

-- Previous Year Casualties
PY Casualties = CALCULATE([CY Casualties], SAMEPERIODLASTYEAR('Calendar'[Date]))

-- Current Year Accidents
CY Accidents = TOTALYTD(SUM(Data[Number_Of_Accidents]),'Calender'[Data])

-- Previous Year Accidents
PY Accidents = CALCULATE([CY Accidents], SAMEPERIODLASTYEAR('Calendar'[Date]))

-- Year-over-Year Casualties %
YoY Casualties = ([CY Casualties] - [PY Casualties]) / [PY Casualties]

## 📊 Dashboard Visuals

The dashboard contains:

### 🔹 KPIs
- Total CY Casualties  
- Total CY Accidents  
- Fatal, Serious, and Slight CY Casualties  

### 🔹 Charts & Graphs
- CY vs PY Casualties trend  
- Casualties by Urban/Rural Area  
- Casualties by Road Type  
- Casualties by Light Conditions
- Casualties by Location

---

## 🎛 Slicers

Interactive slicers used in the dashboard:
- Road Type  
- Weather Condition  

---

## 🚀 How to Use
1. Open the `.pbix` file in **Power BI Desktop**.  
2. Load the dataset (or update the file path in Power Query).  
3. Refresh the data and interact with the slicers for insights.  

---

## 📌 Key Learnings
- Using **Power Query** for data cleaning and transformation.  
- Building a **Calendar Table** for time intelligence.  
- Writing **DAX measures** for CY, PY, and YoY analysis.  
- Designing an **interactive dashboard** with KPIs, slicers, and multiple visuals.  

