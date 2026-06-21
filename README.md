# Breast-Cancer-Dashboard

📌 Project Overview

This project is an interactive Breast Cancer Analysis Dashboard built using Power BI Desktop, analyzing patient data from the SEER (Surveillance, Epidemiology, and End Results) Breast Cancer Dataset. The dashboard provides actionable insights into patient survival, tumor characteristics, cancer staging, and demographic patterns.

<img width="772" height="432" alt="image" src="https://github.com/user-attachments/assets/37ae5ebc-e398-4f8b-94d8-a2b4fa2d8dea" />

🎯 Objectives


Analyze breast cancer patient survival rates across different cancer stages
Identify key tumor characteristics that influence patient outcomes
Understand demographic patterns (age, race, marital status) in breast cancer patients
Visualize survival trends over time using interactive charts

📊 Key Insights

🏥 Total Patients        3,413✅ 
Alive Count              2,903❌
Dead Count               510📈 
Survival Rate            85.06%⏳ 
Avg Survival Months      71.52🔬 
Avg Tumor Size           30.42 mm


📋 Dashboard Features

🃏 KPI Cards


Total Patients
Alive Count
Dead Count
Survival Rate
Average Survival Months
Average Tumor Size


📊 Visuals


Treemap — Patient distribution by Race
Donut Chart — Alive vs Dead patient split
Gauge Chart — Survival Rate vs 90% target
Bar Chart — Patient count by Age Group
Line Chart — Survival months trend with forecast trend line
100% Stacked Bar — Cancer Stage vs Survival Status
Clustered Bar — Survival Rate by Race


🔽 Filters & Slicers


Cancer Stage slicer (Stage 2A, 2B, 3A, 3B, 3C)

🗂️ Data Model (Star Schema)

<img width="394" height="438" alt="image" src="https://github.com/user-attachments/assets/65424c7e-adcf-438d-b607-eca9a0dbe554" />


Key DAX Measures

-- Survival Rate
Survival Rate =
DIVIDE(
    CALCULATE(COUNTROWS(FactSurvival), FactSurvival[VitalStatus] = "Alive"),
    COUNTROWS(FactSurvival),
    0
)

-- Mortality Rate
Mortality Rate =
DIVIDE(
    CALCULATE(COUNTROWS(FactSurvival), FactSurvival[VitalStatus] = "Dead"),
    COUNTROWS(FactSurvival),
    0
)

-- Avg Survival Months
Avg Survival Months = AVERAGE(FactSurvival[SurvivalMonths])

-- Avg Tumor Size
Avg Tumor Size = AVERAGE(DimTumor[TumorSize_mm])

-- Node Positivity Rate
Node Positivity Rate =
DIVIDE(
    SUM(FactSurvival[NodesPositive]),
    SUM(FactSurvival[NodesExamined]),
    0
)


🛠️ Tools & Technologies

Power BI Desktop    Dashboard development
Power Query         Data cleaning & transformation
DAX                 Measures & calculated columns
Star Schema         Data modeling


📁 Dataset
https://www.kaggle.com/datasets/sujithmandala/seer-breast-cancer-data

🚀 How to Use

Download the .pbix file from this repository
Open it in Power BI Desktop (free download from Microsoft)
Explore the dashboard using the slicers and filters
Download the SEER dataset from Kaggle if you want to refresh the data


📃 License

This project is open source and available under the MIT License.


⭐ If you found this project helpful, please give it a star!
