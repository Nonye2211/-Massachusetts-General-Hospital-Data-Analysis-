

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

