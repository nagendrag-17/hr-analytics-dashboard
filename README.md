# HR Analytics Dashboard

## Project Overview
An interactive HR Analytics Dashboard built using Microsoft Power BI to analyse employee data and identify workforce attrition patterns.

## Tools Used
- Microsoft Power BI
- Power Query
- DAX

## Key Analysis
- Total Employees
- Attrition Count
- Attrition Rate
- Attrition by Department
- Attrition by Job Role
- Attrition by Age Group
- Attrition by Gender

## Dashboard Features
- Interactive Department slicer
- Interactive Gender slicer
- KPI cards
- Employee attrition analysis

## Files
- HR_Analytics_Dashboard.pbix
- HR_Dashboard.png

## Data Cleaning Process

Data preparation was performed using Power Query in Power BI.

The following steps were carried out:

1. **Data Inspection:** Reviewed the dataset and checked column names, data types, and data quality.
2. **Data Type Correction:** Corrected column data types, including converting Age into Whole Number.
3. **Missing Values:** Checked for missing and blank values in relevant columns.
4. **Duplicate Check:** Checked employee records for duplicate entries.
5. **Column Validation:** Reviewed important HR fields such as Department, Gender, Age, Job Role, and Attrition.
6. **Data Transformation:** Created an Age Group calculated column to categorize employees into different age ranges.
7. **Data Loading:** Applied the transformations and loaded the cleaned data into Power BI for analysis.

## KPIs and DAX Measures

The dashboard uses the following key performance indicators (KPIs):

| KPI | Description |
|---|---|
| Total Employees | Total number of employees |
| Attrition Count | Number of employees who left |
| Attrition Rate | Percentage of employees who left |

### DAX Measures

**1. Total Employees**
```dax
Total Employees = COUNTROWS('hr dataset')
```

**2. Attrition Count**
```dax
Attrition Count =
CALCULATE(
    COUNTROWS('hr dataset'),
    'hr dataset'[Attrition] = "Yes"
)
```

**3. Attrition Rate**
```dax
Attrition Rate =
DIVIDE(
    [Attrition Count],
    [Total Employees],
    0
)
```

Format Attrition Rate as Percentage with 2 decimal places.

### Calculated Column

**Age Group**
```dax
Age Group =
SWITCH(
    TRUE(),
    [Age] < 25, "Under 25",
    [Age] < 35, "25-34",
    [Age] < 45, "35-44",
    [Age] < 55, "45-54",
    "55+"
)
```

### Dashboard Interactivity
- Department slicer
- Gender slicer
- Interactive KPI cards and charts
  
## Objective
To analyse employee attrition and help understand workforce trends through interactive visualisations.
