# Massachusetts General Hospital Analysis
## Table of Contents
1. Introduction
2. Project Description
3. Project Aim
4. About the Dataset
5. Tools Used
6.  Importing the Dataset
7.  Data Cleaning & Transformation
8. Data Modeling
9. Data Analysis
10. Data Visualization
11. Key Insights
12. Recommendations
13. Conclusion

# Introduction
This project analyzes patient, encounter, and insurance data to uncover trends, generate insights, and provide actionable recommendations that address operational and financial challenges at Massachusetts General Hospital. By examining key factors such as readmission rates, treatment costs, and resource utilization, this analysis aims to support informed decision-making that improves patient care, optimizes resource allocation, and reduces operational inefficiencies.

# Project Description

This project involves analyzing patient, encounter, and insurance data from Massachusetts General Hospital to uncover trends and provide actionable insights. The goal is to optimize patient care, reduce readmission rates, and improve resource allocation by addressing key business questions related to treatment costs, readmission patterns, and insurance coverage impacts. The project includes data collection, cleaning, analysis, and visualization to guide informed decision-making.

#  Project Aim

To analyze patient, encounter, and insurance data to identify trends, derive insights, and provide actionable recommendations that support decision-making in optimizing patient care, reducing readmissions, and improving resource allocation at Massachusetts General Hospital.

#  About the Dataset

## Source of Dataset

The dataset  comes from Massachusetts General Hospital's internal data systems (patient encounters, Payers, procedures). T which were analyzed to uncover patterns in patient care, costs, and hospital resources.

 ## Encounters Table:
 PatientID,Start,Stop,Patient, Organisation,Payer,Encounter,Description,Reason Description 
## Procedures Table:
Start, Stop	Patient, 	Encounter	Code,	Description,	Base-Cost,Reason Code,	ReasonDescription


 ## Payers

Id,	Name,	Address,	City,	State,_Headquater,	ZIP,	Phone


 ## Patients Table:

PatientID, DOB, Age, Sex, Region, ChronicConditionFlag (e.g., diabetes, heart failure), etc.

 ## Date Table :

Date, Year, Month, Quarter, Day, etc.

## Tools Used


- Microsoft Excel

- Power BI


## Importing the Dataset

Imported CSV files into Excel for cleaning, then loaded into Power BI for visualization.

## Data Cleaning & Transformation

- Standardised column formats
- Removal of unnecessary or redundant columns
- Replacement of abbreviations & categorical standardisation
- Standardisation of text format
- Removal of personally identifiable information (PII)
- Renaming unclear or ambiguous columns
- Creation of calculated/derived fields
- Refinement of date formatting

# Data Modeling 

- Created Calculated Columns

- Created a calculated column Age of Deceased to determine the age of patients at death.

- Created a calculated column Length of Stay to measure the number of days each patient stayed in the hospital.

- Created an Age Band column to group patients into demographic categories.

- Cleaned and standardised categorical columns (Gender, Marital Status, Race, Ethnicity).

- Renamed unclear fields for clarity (e.g., Encounter → Encounter Code, ReasonCode → Diagnosis Code).

- Converted all DateTime fields to Date-only formats to support trend and time-based analysis.

## Created DAX Measures

- Created a measure Total Encounters to count all patient encounters.

- Created a measure Total Patients using DISTINCTCOUNT to count unique patients.

- Created a measure Average LOS to calculate the average patient Length of Stay.

- Created a measure Total Procedures to count the number of procedures performed.

- Created a measure Total Deaths to count all records with a valid Date of Death.

- Created a measure Total Cost (if cost data is available) to sum the cost of all procedures.

## Built Data Model Relationships

- Connected Patients[Patient Code] to Encounters[Patient Code] (One-to-Many).

- Connected Encounters[Encounter Code] to Procedures[Encounter Code] (One-to-Many).

- Connected Encounters[Encounter Code] to Payers[Encounter Code] (One-to-Many).

- Linked the Date Table to encounter start and stop dates for time-series analysis.

- Ensured all relationships use single-direction filtering to avoid ambiguity.

 # Data Analysis

## Metrics, KPIs, or Columns Analyzed

- Total Encounters

- Average Length of Stay (LOS)

- Readmission Rate (30-Day)

- Total Procedures Performed

- Cost of Procedures / Total Procedure Cost

- Patient Demographics (Age, Gender, Race, Marital Status)

- Diagnosis Performance (Top Diagnoses by Frequency)

- Procedure Performance (Volume and Cost)

- Insurance Coverage vs Out-of-Pocket Payments

- Mortality Metrics (Total Deaths, Age of Deceased)

- Encounter Trends Over Time (Monthly/Yearly)


# Data Visualization
Document dashboards/pages and charts used:

## Overview Dashboard
KPI Cards:

- Total Patients

- Total Encounters

- Total Claim Cost

- Readmission Rate (%)

- Average Length of Stay (Days)

Line Chart:

- Readmission Rate (%) Trend Over the Year

Bar + Line Combo Chart:

- Encounters per Month (Bar)

- Claim Cost per Month (Line)

Bar Chart:

- Total Claim Cost by Encounter Description

- Readmission Rate by Encounter Class

- Top 5 Payers by Total Claim Amount

## Patient Demographics Dashboard
Donut Charts:

- Readmission Rate by Gender

- Readmission Rate by Marital Status

- Readmission Count by Ethnicity

- Readmission Rate by Race

Bar Charts:

- Readmission Rate by City

- Readmission Rate by County

## View Dashboards

[Overview Dashboard](https://github.com/Nonye2211/-Massachusetts-General-Hospital-Data-Analysis-/blob/main/Overview_Dashboard.png.png)

[Insights Dashboard](https://github.com/Nonye2211/-Massachusetts-General-Hospital-Data-Analysis-/blob/main/Patient_Demographics_Dashboard.png.png)

## Key Insights
- Urgent Care encounters account for the largest portion of total claim cost, contributing over $23M, making it the highest-cost category in the hospital.

- Patients in the 51–65 and 66+ age bands drive the highest readmission rates, especially in counties like Plymouth and Norfolk.

- Medicare is the highest-paying insurer, responsible for over $24M in claims, but shows high readmission patterns across multiple encounter types.

- Inpatient and Urgent Care classes have the highest readmission rates (71–74%), indicating possible gaps in discharge planning or follow-up care.

- Hispanic and White patients show higher readmission percentages, suggesting demographic groups that may require targeted post-care intervention.

- Monthly claim costs peak in March and September, even though encounter volumes remain steady—indicating higher-cost procedures or acute cases during those months.

- Cities such as Hull and Weymouth show extremely high readmission rates (79–91%), suggesting geographic disparities in access to quality follow-up care.

# Recommendations
### Actionable Recommendations for Stakeholders
- Strengthen follow-up care for Urgent Care and Inpatient encounters, as these two classes have the highest readmission rates.

- Develop targeted care-coordination programs for high-risk demographics, especially Hispanic, White, and older patient groups showing elevated readmission patterns.

- Allocate additional resources to high-cost encounter types, such as Urgent Care Clinic visits, to improve efficiency and reduce unnecessary spending.

- Increase discharge planning support and patient education, particularly in high-readmission cities like Hull and Weymouth.

- Partner with Medicare and Medicaid providers to improve care continuity and reduce avoidable readmissions among insured patients.

- Implement cost-reduction strategies during peak months (e.g., March and September), where claim costs are highest despite stable encounter volume.

- Expand preventive and community-based programs in counties with elevated readmission rates (Plymouth and Norfolk) to reduce hospital returns.

## Conclusion
Insights from the hospital data highlight key opportunities to reduce readmissions, improve patient care, and optimize costs. By addressing high-risk encounter types, focusing on vulnerable patient groups, and strengthening follow-up care, the hospital can enhance outcomes and improve operational efficiency.

## Contact Information

LinkedIn: [www.linkedin.com/in/nonye-mbata-1a963212b]


Email: [anyadike4real@gmail.com]





