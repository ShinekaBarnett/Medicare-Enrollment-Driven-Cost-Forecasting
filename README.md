# Medicare Enrollment-Driven Cost Forecasting

## Overview
This project analyzes historical Medicare enrollment data (2016–2021) to forecast future service demand and simulate reimbursement costs across U.S. states and demographic groups. Built on Databricks, it demonstrates scalable data engineering, predictive modeling, and strategic healthcare insights using real CMS data.

## Dataset
**Source:** [CMS Program Statistics – Medicare Newly Enrolled](https://data.cms.gov/summary-statistics-on-beneficiary-enrollment/medicare-and-medicaid-reports/cms-program-statistics-medicare-newly-enrolled)  
**File Used:** `CPS MDCR ENROLL AB 21-32 2021.xlsx`  
**Contents:**  
- Monthly and annual enrollment counts  
- Breakdown by age, disability status, race, sex, and geography  
- Plan types: Original Medicare vs. Medicare Advantage  

## Objectives
- Forecast Medicare enrollment trends by state and demographic group  
- Simulate reimbursement costs based on projected enrollment  
- Identify high-growth regions and underserved populations  
- Support strategic planning for providers and policymakers  

## Architecture
- **Platform:** Azure Databricks  
- **Storage:** Delta Lake  
- **Tools:** PySpark, MLflow, Auto Loader, Pandas, Plotly  

## Pipeline Structure
### 1. Data Ingestion
- Load Excel sheets into Databricks using Auto Loader  
- Normalize column formats and unify schema across years  

### 2. Feature Engineering
- Calculate growth rates, aged vs. disabled ratios, and regional flags  
- Create rolling averages and seasonal indicators  

### 3. Forecasting & Simulation
- Train time series models (ARIMA, Prophet) on monthly enrollment  
- Estimate future reimbursement costs using synthetic per-beneficiary rates  
- Track model performance with MLflow  

### 4. Visualization
- Interactive dashboards showing:
  - Top states by projected enrollment growth  
  - Estimated reimbursement burden by demographic  
  - Seasonal spikes in service demand  

## Key Insights
- Enrollment growth hotspots for Medicare Advantage  
- Cost burden projections for disabled beneficiaries  
- Equity gaps in coverage by race and sex  

## How to Run
1. Clone this repo and open in Databricks  
2. Upload the CMS dataset to DBFS  
3. Run `01_ingest_and_clean.ipynb` to prepare the data  
4. Run `02_feature_engineering.ipynb` to generate features  
5. Run `03_forecasting_and_simulation.ipynb` to build models  
6. Run `04_visualization.ipynb` to explore insights  

## Author
**Shineka Barnett** — Data Engineer 
Focused on real-world impact through healthcare and music tech.  
New York | Python, SQL, Azure, Databricks

## License
This project uses publicly available CMS data and is intended for educational and professional portfolio use.