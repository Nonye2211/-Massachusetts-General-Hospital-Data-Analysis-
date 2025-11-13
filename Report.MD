

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

## Data Modeling 

- Age of Deceased

Used to analyse mortality trends and age-related patterns.

Age of Deceased = 
IF (
    NOT ISBLANK([Date of Death]),
    DATEDIFF([Date of Birth], [Date of Death], YEAR),
    BLANK()
)

- Length of Stay (LOS)

Used to determine patient-stay efficiency and identify long-stay outliers.

Length of Stay = 
DATEDIFF([Start Date], [Stop Date], DAY)

- Age Band (for demographic grouping)

Grouped patients into standard age brackets for clearer analysis.

Age Band = 
SWITCH(
    TRUE(),
    [Age] < 18, "0–17",
    [Age] <= 35, "18–35",
    [Age] <= 50, "36–50",
    [Age] <= 65, "51–65",
    "66+"
)

- Cleaned Categorical Columns

These were created after replacing abbreviations:

Marital Status (M → Married, S → Single)

Gender (M → Male, F → Female)

- Standardised Race & Ethnicity values

(Performed in Power Query using Replace Values and Text Formatting.)

1.5 Diagnosis and Procedure Standardization

Columns renamed or restructured:

ReasonCode → Diagnosis Code

ReasonDescription → Diagnosis Description

Code → Procedure Code

(Performed using Rename Column feature in Power Query.)

-  DAX Measures (For Use in Visuals and KPIs)


- Total Number of Encounters
Total Encounters = COUNTROWS(Encounters)

- Average Length of Stay
Average LOS = AVERAGE(Encounters[Length of Stay])

- Total Procedures Performed
Total Procedures = COUNTROWS(Procedures)

- Total Cost (If Procedure Cost Exists)
Total Cost = SUM(Procedures[Cost])

- Death Count
Total Deaths = COUNTROWS(FILTER(Patients, NOT ISBLANK(Patients[Date of Death])))

- Readmission Rate (If 30-day readmissions were required)

(If using Start/Stop date to determine next encounter for same patient)

Readmission Rate = 
DIVIDE(
    [Number of Readmissions],
    [Total Index Admissions]
)


(You can remove this if your dataset does not contain readmission logic.)

- Patient Count
Total Patients = DISTINCTCOUNT(Encounters[Patient Code])

