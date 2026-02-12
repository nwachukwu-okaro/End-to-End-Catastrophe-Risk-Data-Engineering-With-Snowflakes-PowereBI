# End-to-End-Catastrophe-Risk-Data-Engineering-With-Snowflakes-PowereBI
# Project Overview
This project demonstrates a complete End-to-End Data Engineering and Analytics pipeline. I engineered a synthetic dataset of 10,000 UK properties to simulate £10.79bn in Total Insured Value (TIV). The goal was to identify financial exposure within the Thames flood zones by building a scalable data architecture in Snowflake and delivering executive-level insights via Power BI.

# Step-by-Step Approach1.

**Database Architecture (Snowflake)**

I implemented a Medallion Architecture (Raw $\rightarrow$ Analytics) to ensure data integrity and separation of concerns:

**Raw Layer:** Ingested primary property data including Policy IDs, Segments (High Net Worth, Mid Market, Standard), and financial values.

**Analytics Layer:** Developed a specialized FACT_EXPOSURE_SUMMARY view. I used Spatial SQL to perform a "Point-in-Polygon" intersection, determining which properties fell within high-risk flood boundaries


**Security & Data Governance**

To mirror a real-world enterprise environment, I implemented a robust Role-Based Access Control (RBAC) model:

**INS_ENGINEER_ROLE:** Granted full administrative rights to develop the architecture.

**ANALYST_READ_ROLE:** A restricted role created for BI tools, ensuring the "Principle of Least Privilege.

**Delegated Administration:** Configured the Engineering role with the GRANT OPTION to manage downstream analyst access autonomously.


**Business Intelligence & DAX (Power BI)**
I connected Power BI to Snowflake via DirectQuery to ensure real-time data freshness. Key technical steps included:

**Complex DAX Measures:** Developed advanced measures for Loss Exposure % and Risk Concentration.

**Error Resolution:** Debugged syntax errors by replacing informal "filtered by" logic with professional CALCULATE and FILTER functions to handle Boolean data types.

**UI/UX Design:** Implemented a high-contrast dark theme with Conditional Formatting to highlight "Flooded" properties in red for immediate executive action.

# Key Outcomes & Insights

Total Exposure Identified: Identified that 9.95% of the portfolio (1,000 properties) is at risk.

**Financial Impact:** Successfully isolated £1.07bn in Total Flooded Value from the total £10.79bn portfolio.

**Segment Analysis:** Revealed that High Net Worth and Mid Market segments carry a proportional 0.10 exposure ratio, indicating a uniform risk distribution across customer tiers.

**Executive Actionability:** The final dashboard allows underwriters to see the Average Flooded Value (£1.08M) and the Max Segment Exposure (£814.25M) at a single glance.


# Tech Stack

**Data Warehouse:** Snowflake (SQL, Spatial Functions, RBAC Security)

**BI Tool:** Power BI Desktop (DAX, DirectQuery, Data Modeling)

**Languages:** SQL, Python (Streamlit), DAX

**Cloud Platform:** AWS (Snowflake Hosting)
