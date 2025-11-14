

1. # Introduction


This project analyzes patient, encounter, and insurance data to uncover trends, generate insights, and provide actionable recommendations that address operational and financial challenges at Massachusetts General Hospital. By examining key factors such as readmission rates, treatment costs, and resource utilization, this analysis aims to support informed decision-making that improves patient care, optimizes resource allocation, and reduces operational inefficiencies.

# Project Description

This project involves analyzing patient, encounter, and insurance data from Massachusetts General Hospital to uncover trends and provide actionable insights. The goal is to optimize patient care, reduce readmission rates, and improve resource allocation by addressing key business questions related to treatment costs, readmission patterns, and insurance coverage impacts. The project includes data collection, cleaning, analysis, and visualization to guide informed decision-making.

#  Project Aim

To analyze patient, encounter, and insurance data to identify trends, derive insights, and provide actionable recommendations that support decision-making in optimizing patient care, reducing readmissions, and improving resource allocation at Massachusetts General Hospital.

#  About the Dataset

- ## Source of Dataset

Source: The dataset  comes from Massachusetts General Hospital's internal data systems (patient encounters, insurance, procedures). The hospital has years of internal patient data, encounter data, and insurance data, which were analyzed to uncover patterns in patient care, costs, and hospital resources.

- ## Number of Rows and Column

-  ## Key fields/columns

   - ## Encounters Table:
- EncounterID, PatientID, AdmissionDateTime, DischargeDateTime, Department/Service, Diagnosis/Procedure, LOS Days (Length of Stay), Cost/Charge, etc.

- ## Procedures Table:

ProcedureCode, EncounterID, Cost/Charge, Quantity, ResourceTime, etc.

- ## Claims Table:

ClaimID, EncounterID, Payer, InsurancePaid, PatientPay, ClaimStatus, etc.

- ## Patients Table:

PatientID, DOB, Age, Sex, Region, ChronicConditionFlag (e.g., diabetes, heart failure), etc.

- ## Date Table :

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

-Average Length of Stay (Days)

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

[Overview Dashboard](https://github.com/Nonye2211/-Massachusetts-General-Hospital-Data-Analysis-/blob/main/Overview_Dashboard.png.png?raw=true)

[Insights Dashboard](https://github.com/Nonye2211/-Massachusetts-General-Hospital-Data-Analysis-/blob/main/Patient_Demographics_Dashboard.png.png)

## Key Insights
- What is the current rate of readmissions — and is it rising? Urgent care and inpatient departments are driving high readmission rates, indicating potential gaps in follow-up care or care quality.
- Which procedures/encounters are the most expensive and why? Urgent care clinic visits generate the highest financial burden, signaling a need for better primary care access and preventive programs.
- How does insurance coverage compare with patient out-of-pocket payments? The hospital relies heavily on government-funded insurance, indicating high proportions of elderly and low-income patients.
- Which patient demographics are linked to more readmissions? Certain ethnic groups and specific cities (Hull, Weymouth) show significantly higher readmission rates, suggesting socioeconomic or care-access disparities.
- Are patients staying longer than expected? Longer hospital stays may be due to patient complexity or delays in care transitions.




