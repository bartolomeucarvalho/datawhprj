# datawhprj

# Sales Data Warehouse & ETL Pipeline
 
A data warehouse project that ingests raw sales data, transforms it through an ETL/ELT pipeline, and models it into a dimensional schema for analytics and reporting.
 
## Overview
 
This project simulates an end-to-end data engineering workflow — from raw sales data ingestion to a query-ready star schema — built to practice real-world data warehousing concepts including dimensional modeling, incremental loading, data quality testing, and orchestration.
 
## Architecture
 
```
Raw Sales Data (CSV/API)
        │
        ▼
   Ingestion Layer  (Python)
        │
        ▼
   Staging Layer  (Raw tables, minimal transformation)
        │
        ▼
   Transformation Layer  (dbt models)
        │
        ▼
   Data Warehouse  (Star Schema: Fact + Dimension tables)
        │
        ▼
   Reporting / Dashboards
```
 
## Tech Stack
 
| Layer | Tool |
|---|---|
| Data Source | ** |
| Ingestion | Python (pandas, requests) |
| Data Warehouse | ** |
| Transformation | dbt |
| Orchestration | ** |
| Version Control | Git / GitHub |
 
## Data Model
 
The warehouse follows a **star schema** design:
 
**Fact Table**
- `fact_sales` — one row per transaction, containing measures such as `quantity_sold`, `sales_amount`, `discount`, `profit`
**Dimension Tables**
- `dim_product` — product details, category, brand
- `dim_customer` — customer attributes
- `dim_date` — calendar attributes (day, month, quarter, year)
- `dim_store` / `dim_region` — location attributes
## Project Structure
 
```
├── data/                # Raw and sample data files
├── ingestion/           # Python scripts for data extraction/loading
├── dbt_project/         # dbt models (staging, intermediate, marts)
│   ├── models/
│   │   ├── staging/
│   │   ├── intermediate/
│   │   └── marts/
├── orchestration/        # DAGs / scheduling scripts
├── tests/                # Data quality tests
└── README.md
```
 
## How to Run
 
1. Clone the repository
```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
```
 
2. Set up a virtual environment and install dependencies
```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
```
 
3. Configure your data warehouse credentials
```bash
   cp .env.example .env
   # add your warehouse connection details
```
 
4. Run the ingestion pipeline
```bash
   python ingestion/load_sales_data.py
```
 
5. Run dbt transformations
```bash
   cd dbt_project
   dbt run
   dbt test
```
 
## Key Features
 
- Automated ingestion of raw sales data into a staging layer
- Dimensional modeling (star schema) for fast, intuitive analytics queries
- Data quality tests to catch nulls, duplicates, and referential integrity issues
- Modular, version-controlled transformation logic using dbt
- **
## Future Improvements
 
- [ ] Add incremental/delta loading instead of full refresh
- [ ] Add orchestration (Airflow) for automated daily runs
- [ ] Build a dashboard (e.g. Power BI / Tableau / Streamlit) on top of the warehouse
- [ ] Add CI/CD for automated dbt testing on pull requests
## Author
 
*Bartolomeu* 
