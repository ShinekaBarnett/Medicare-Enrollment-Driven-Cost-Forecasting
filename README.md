# Medicare Enrollment Pipeline A Databricks Healthcare Project

## Overview
This project explores 2021 Medicare enrollment data to simulate reimbursement costs and uncover demographic and geographic trends across U.S. states. Built on Azure Databricks, it showcases scalable data engineering and healthcare analytics using real CMS data.

## Dataset
**Source:** [CMS Program Statistics – Medicare Newly Enrolled](https://data.cms.gov/summary-statistics-on-beneficiary-enrollment/medicare-and-medicaid-reports/cms-program-statistics-medicare-newly-enrolled)  
**File Used:** `CPS MDCR ENROLL AB 24 2021.xlsx`  
**Contents:**  
- Total, Aged, and Disabled Enrollees, by Area of Residence

## Objectives
- Analyze 2021 Medicare Enrollment by state 
- Identify states with high disabled-to-aged ratios  
- Simulate reimbursement costs using static per-beneficiary rates 
 

## Architecture
- **Platform:** Azure Databricks  
- **Storage:** Delta Lake  
- **Tools:** PySpark, MLflow, Pandas, Plotly, Auto Loader 

## Pipeline Structure
### 1. Data Ingestion
- Load MDCR ENROLL AB 24 sheet into Databricks using Auto Loader 
- Clean column names and filter out non-state rows
- Convert nukeric columns and handle suppressed values(*,†) 

### 2. Feature Engineering
- Compute: 
    1.Total enrollment per state
    2.Aged vs. disabled ratios
    3.Part A vs. Part B participation  
- Flag states with above-average disabled enrollment
- Normalize values for visualization

### 3. Simulation
- Apply fixed reimbursement rates  
- Estimate total cost per state  
- Rank states by projected cost burden 

### 4. Visualization
- Build dashboards with:
  - Choropleth map of enrollment by state
  - Bar chart of diabled vs. aged ratios  
  - Cost simulation by state  

## Key Insights
- States with disproportionately high disabled enrollment  
- Cost-heavy regions based on demographic mix  
- States with low Part B uptake (potential gaps in coverage) 

## How to Run
1. Clone this repo and open in Databricks  
2. Upload the Excel sheet to DBFS  
3. Run `01_ingest_and_clean.ipynb` to load and clean the data 
4. Run `02_feature_engineering.ipynb` to compute metrics  
5. Run `03_simulation.ipynb` to estimate costs 
6. Run `04_visualization.ipynb` to explore results 

## Author
**Shineka Barnett** — Data Engineer 
Focused on real-world impact through healthcare and music tech.  
New York | Python, SQL, Azure, Databricks

## License
This project uses publicly available CMS data and is intended for educational and professional portfolio use.