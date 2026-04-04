# **Patients Outcome Analysis: Strategic Healthcare Business Intelligence**

This repository features a comprehensive end-to-end data analysis project that transforms **10,000 patient records** into a multi-page interactive **Power BI dashboard**. The project focuses on evaluating **$5.003 billion in total treatment costs** to uncover departmental efficiencies, regional cost drivers, and patient outcome patterns.

---

## **Data Cleaning & Preprocessing**
The raw dataset consisted of **10,000 rows** of hospital transactional data. Using **Power Query**, the following cleaning steps were performed to ensure data integrity:
*   **Data Volume:** Processed 10,000 records to ensure a high-confidence analysis of hospital operations.
*   **Duplicate Removal:** Identified and removed duplicate patient records to prevent the artificial inflation of financial and volume metrics.
*   **Categorical Standardization:** Resolved naming inconsistencies and typos, specifically correcting **"Neurologylogy"** to **Neurology** to ensure accurate departmental aggregation.
*   **Handling Nulls/Blanks:** Addressed **"(Blank)"** entries in the **Hospital Branch** field to maintain the integrity of regional cost and volume comparisons.
*   **Data Type Validation:** Formatted **Treatment Cost** as currency and **VisitDate** as date objects to facilitate accurate time-series analysis.

---

## **Data Modeling**
I implemented an **optimized star schema** to support high-performance reporting and dynamic cross-filtering:
*   **Fact Table:** Contains transactional records including PatientID, Treatment Cost, Outcome, and Visit Date.
*   **Dimension Tables:** Created separate dimensions for **Hospital Branch, Department, and Payment Type** for granular filtering.
*   **Relationships:** Established one-to-many relationships between dimension and fact tables, allowing for seamless drill-down capabilities.

---

## **DAX Measures**
To power the dashboard's interactive elements and KPIs, I developed several custom DAX measures:
*   **Total Patients:** `COUNTROWS('PatientData')` — Used to track the total volume of 10,000 patients.
*   **Total Treatment Cost:** `SUM('PatientData'[Treatment Cost])` — Aggregated to show the **$5.003 Billion** total expenditure.
*   **Average Treatment Cost:** `AVERAGE('PatientData'[Treatment Cost])` — Reveals the **$514.7K** average per patient.
*   **Referral Count:** `CALCULATE(COUNTROWS('PatientData'), 'PatientData'[Outcome] = "Referred")` — Used to identify the 684 referrals in **Pediatrics** and other departments.

---

## **Report & Visualizations**
The report is structured into four strategic pages, each utilizing specialized visuals to communicate complex data:

### **1. Hospital Performance**
<img width="381" height="212" alt="17752928731096022549552494438090" src="https://github.com/user-attachments/assets/ec1c57c3-322a-4ed3-9494-631c1afb02de" />

*   **KPI Cards:** Displaying high-level executive metrics like **Total Patients**, **Average Treatment Cost ($514.7K)**, and **Total Treatment Cost**.
*   **Donut Chart:** Visualizes **Payment Type Count**, revealing a balanced split: **Insurance (34.03%)**, **Cash (33.2%)**, and **HMO (32.77%)**.

### **2. Cost & Department Analysis**
<img width="379" height="212" alt="17752927921338067629391820501281" src="https://github.com/user-attachments/assets/02b1e407-304a-4c8f-a049-dd7904491496" />

*   **Decomposition Tree (AI Visual):** Breaks down the **$5.003 Billion total cost** by Payment Type, Department (e.g., **General Medicine** at $350M), and Branch.
*   **Clustered Bar Chart:** Ranks departments by volume, identifying **Pediatrics** as the largest (2,019 patients).
*   **Stacked Bar Chart:** Displays the outcome distribution per department, highlighting the split between **Ongoing, Recovered, and Referred**.

### **3. Branch & Payment Analysis**
*   **Branch Column Charts:** Compares **Patient Count** (led by **Abuja**) against **Treatment Cost** (led by **Ibadan**).
*   **Key Influencers (AI Visual):** Identifies that when the **Department is Neurology**, the average treatment cost **decreases by $1.74 Million**.

### **4. Trends & Timeline**
*   **Line Charts:** Track the **Treatment Cost Trend** and **Patient Count Trend** over time, allowing for the identification of seasonal surges.
*   **Q&A Natural Language Visual:** Allows users to query the data directly, revealing a **$993,090,657** trend for the **Cardiology** department.

---

## **Strategic Insights**
*   **Regional Disparity:** While **Abuja** manages the highest number of patients, **Ibadan** leads the network in total treatment cost, suggesting higher case complexity or operational costs in that branch.
*   **Departmental Volume:** **Pediatrics (2,019)**, **Cardiology (1,965)**, and **Orthopedics (1,960)** are the highest-volume departments, together representing nearly 60% of the patient base.
*   **Cost Efficiency:** **Neurology** serves as a significant benchmark for cost-saving, correlating with a **$1.74M decrease** in average patient expenditure.
*   **Outcome Patterns:** Across all major departments, approximately **one-third of patients are "Referred"** (e.g., 684 referrals in **Pediatrics** and 674 in **Cardiology**), suggesting a potential gap in specialized in-house care.

---

## **Actionable Recommendations**
*   **Reduce Revenue Leakage:** Investigate why **~34% of patients** are being referred out of high-volume departments like **Pediatrics and Cardiology**. Investing in specialized equipment could keep these patients—and their revenue—in-house.
*   **Audit Branch Expenditures:** Conduct an operational audit of the **Ibadan branch** to align its cost-to-patient ratio with more volume-efficient branches like **Abuja** or **Kano**.
*   **Scale Neurology’s Protocols:** Analyze treatment protocols in **Neurology** to determine if their cost-saving measures can be applied to higher-cost departments like **Cardiology ($993M trend)**.

---

## **Skills Demonstrated**
*   **BI Tools:** Microsoft Power BI (Decomposition Tree, Key Influencers, Q&A)
*   **Data Engineering:** Power Query (ETL), Data Cleaning of 10,000 rows, Data Standardization
*   **Analytics:** DAX (Data Analysis Expressions), Statistical Trend Analysis, AI-driven Insights
*   **Modeling:** Star Schema Design, Relationship Management
*   **Business Communication:** Strategic Recommendations, Data Storytelling
