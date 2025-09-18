# Medicare Enrollment Pipeline A Databricks Healthcare Project

## Overview
This project explores 2021 Medicare enrollment data to analyze enrollment metrics and normalize data. Built on Azure Databricks, it showcases scalable data engineering and healthcare analytics using real CMS data.

## Dataset
**Source:** [CMS Program Statistics – Medicare Newly Enrolled](https://data.cms.gov/summary-statistics-on-beneficiary-enrollment/medicare-and-medicaid-reports/cms-program-statistics-medicare-newly-enrolled)  
**File Used:** `CPS MDCR ENROLL AB 24 2021.xlsx`  
**Contents:**  
- Total Enrollees by Area of Residence
 

## Architecture
- **Platform:** Azure Databricks  
- **Storage:** Delta Lake  
- **Tools:** PySpark, Auto Loader 

## Pipeline Structure Bronze Layer
### 1. Data Ingestion
- Load MDCR ENROLL AB 24 sheet into Databricks using Auto Loader 
- Clean column names and filter out non-state rows

### 2. Feature Engineering / Silver Layer
- Compute enrollment ratios & totals.
- Clean & normalize the data.
- Range Calculation

### 3. Visualization /Gold Layer
- Choropleth map of enrollment by state

## Author
**Shineka Barnett** — Data Engineer 
Focused on real-world impact through healthcare and music tech.  
New York | Python, SQL, Azure, Databricks, DataStage

## License
This project uses publicly available CMS data and is intended for educational and professional portfolio use.