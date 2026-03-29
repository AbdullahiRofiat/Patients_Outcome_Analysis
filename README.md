# Patients_Outcome_Analysis

## Overview
This project presents a comprehensive Health Data Analysis Dashboard developed in Microsoft Power BI, transforming 10,000+ hospital patient records into actionable insights for decision-making.  

The objective of this analysis was to:  
- Understand patient outcomes and treatment trends  
- Identify cost drivers and operational inefficiencies  
- Evaluate department and hospital branch performance  
- Provide a scalable, interactive Business Intelligence solution**  

Although this dataset is healthcare-focused, the analytical approach applies to any industry with transactional data, including finance, retail, logistics, and SaaS operations.

---

## Data Cleaning & Preprocessing
Using Power Query, the dataset was prepared for analysis:  
- Removed duplicates to ensure data integrity  
- Standardized categorical values (e.g., department names: Cardiology, Neurology, etc.)  
- Corrected data types (dates, currency, text)  
- Validated key fields like PatientID, Treatment Cost, Outcome, Payment Type, and Visit Date 

This step ensured accurate aggregations and reliable insights.

---

## Data Modeling
An optimized star schema was designed for efficient reporting:  

### Fact Table
- Patient-level transactional records including Treatment Cost, Outcome, DoctorID, Department, Branch, Payment Type, and Visit Date  

### Dimension Tables
- Date  
- Department 
- Payment Type 
- Hospital Branch  

One-to-many relationships were established between dimensions and the fact table to enable dynamic filtering and accurate aggregations.

---

## Metrics & DAX Measures
Dynamic business metrics were created using DAX:  
- Total Patients: `DISTINCTCOUNT(PatientID)`  
- Total Treatment Cost: `SUM(TreatmentCost)`  
- Average Treatment Cost: `AVERAGE(TreatmentCost)`  
- Recovered Patients: `CALCULATE(COUNTROWS('Health Dataset'), FILTER('Health Dataset', Outcome = "Recovered"))`  

These measures power interactive dashboards and real-time insights.

---

## Report & Visualizations
A multi-page interactive dashboard was developed with four key pages:  

### 1. Health Performance Page
- Card visuals: Total Patients, Total Treatment Cost, Average Treatment Cost, Recovered Patients  
- Donut Chart: Payment Type distribution  
- Smart Narrative: AI-powered automatic summary of key metrics  
- Interactive slicers: Department, Branch, Date  

### 2. Cost & Department Analysis Page
- Decomposition Tree (AI visual): Identify top cost drivers  
- Clustered Bar Chart: Patient count by department  
- Stacked Bar Chart: Recovered vs non-recovered patients by department  

### 3. Branch & Payment Analysis Page
- Column Charts: Patient count and treatment cost per branch  
- Key Influencers (AI visual): Factors affecting recovery outcomes  

### 4. Trends & Timeline Page
- Line Charts: Treatment cost and patient count trends over time  
- Q&A Visual (AI): Interactive natural language queries  

---

## Insights
- Certain departments are major cost drivers
- Branches show significant variation in patient volume 
- Recovery rates differ across departments and treatment types  
- Payment patterns indicate insurance dominance 

---

## Recommendations
- Allocate resources to high-volume departments
- Monitor cost-heavy units for efficiency improvements 
- Optimize branch operations based on performance data  
- Continue tracking trends monthly for proactive decision-making  

---

## Skills Demonstrated
Power BI, DAX, Data Cleaning, Star Schema Modeling, AI Visuals (Decomposition Tree, Key Influencers, Smart Narrative, Q&A), Interactive Dashboards, Data Storytelling, SQL, SSMS, SSAS, SSIS  

---

This project demonstrates the full end-to-end process of transforming raw data into a scalable, decision-driven Business Intelligence solution — a capability highly transferable across industries.
