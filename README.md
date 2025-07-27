# Patient-Blood-Test-Analysis-Dashboard

## Project Overview
The Patient Blood Test Analysis Dashboard addresses the challenge of efficiently analyzing and interpreting large volumes of patient blood test data. By transforming raw CSV data into interactive visualizations, the dashboard empowers healthcare providers to quickly assess patient health status, identify at-risk individuals, and understand demographic health trends.

## Features
The dashboard is structured into several sections, each focusing on a specific aspect of the blood test data:

### 1. Patient Overview Section
Card Visuals: Provides quick statistics at a glance:

Total Patients

Average Age

Gender Distribution (Male/Female ratio)

Bar/Column Chart: Displays the number of patients categorized by distinct age groups.

DAX for Age Group Column:

Age Group =
SWITCH(
    TRUE(),
    bloodtest[Age] >= 20 && bloodtest[Age] <= 30, "20-30",
    bloodtest[Age] >= 31 && bloodtest[Age] <= 40, "31-40",
    bloodtest[Age] >= 41 && bloodtest[Age] <= 50, "41-50",
    bloodtest[Age] > 50, "Above 50"
)

### 2. Hemoglobin Levels
Gauge Chart: Visualizes the average Hemoglobin level, indicating whether it falls into low, normal, or high ranges.

Column Chart: Compares Hemoglobin levels across individual patients or aggregated groups.

Conditional Formatting Table: Highlights patients whose Hemoglobin levels are outside the predefined normal ranges (e.g., < 13 g/dL for males or < 12 g/dL for females).

### 3. WBC and Platelet Analysis
Scatter Plot: Illustrates the relationship between White Blood Cell (WBC) count and Platelet count, useful for identifying correlations or outliers.

Heat Map: Shows the concentration of WBC counts across different age groups and genders.

Line Chart: (If longitudinal data is available) Displays trends of WBC and Platelet counts over time.

### 4. Glucose Levels
Bar Chart: Groups patients based on their glucose levels into categories:

Normal (\<100 mg/dL)

Prediabetes (100−125 mg/dL)

Diabetes (125 mg/dL)

Pie Chart: Shows the percentage distribution of patients within each glucose range.

KPI Card: Highlights the count or percentage of patients with glucose levels above 125 mg/dL, indicating a potential diabetes risk.

### 5. Cholesterol Insights
Histogram: Displays the distribution of Cholesterol levels among the patient population.

Stacked Column Chart: Compares Cholesterol levels across different age groups and genders.

Bullet Chart: Benchmarks individual patient cholesterol levels against recommended healthy ranges.

### 6. Comprehensive Health Score
Custom Measure: A calculated "Health Score" is derived by normalizing and combining values from Hemoglobin, WBC, Platelets, Glucose, and Cholesterol. This provides a single metric for overall health assessment.

Treemap: Categorizes and displays patients' health scores into ranges such as "Excellent," "Good," and "Poor," allowing for quick identification of patient groups.

### 7. Demographic Insights
Donut Chart: Provides a clear breakdown of the patient population by gender.

Age Pyramid: Visualizes the age distribution, split by gender, offering insights into demographic structure.

### 8. Interactive Patient Table
Table Visual with Filters: A detailed table listing Patient Name, Age, Gender, and their respective blood test values.

Filtering Capabilities: Allows users to filter the table by age range, gender, or specific test abnormalities for focused analysis.

### 9. Abnormal Value Highlight
Conditional Formatting: Applied across tables and matrices to visually highlight cells where test parameters fall outside normal or healthy ranges.

Alert Bar: A visual indicator or card displaying the number of patients with abnormal levels for each specific test (e.g., "5 patients with low Hemoglobin").

### 10. Multi-Metric Comparison
Radar Chart: Enables a comparative view of multiple metrics (Hemoglobin, WBC, Platelets, Glucose, Cholesterol) for selected patients, useful for understanding individual patient profiles.

Matrix Chart: Summarizes average blood test values broken down by gender and age group, providing aggregate insights.

### 11. Filters and Slicers
Interactive slicers are available throughout the dashboard for dynamic data exploration:

Gender

Age Range

Specific Tests (e.g., filter to only show glucose-related visuals)

#### Data Source
The project utilizes patient blood test data sourced from:

Patient_Blood_Test.xlsx - Sheet1.csv

#### Technologies Used
Microsoft Power BI Desktop: For data modeling, visualization, and dashboard creation.

DAX (Data Analysis Expressions): For creating custom measures and calculated columns.
