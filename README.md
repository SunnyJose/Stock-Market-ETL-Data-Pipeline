# Stock-Market-ETL-Data-Pipeline
## Objective 
The main objective of this project was to design and implement an automated ETL (Extract, Transform, Load) data pipeline to retrieve historical stock data for a specified ticker, process it, validate its quality, and store it in a PostgreSQL database for analysis. This pipeline enables reliable, repeatable data ingestion and prepares the dataset for downstream analytics and visualization.

## Skills Learned
   - Python programming for data extraction and transformation.
   - SQL and PostgreSQL database management.
   - Data validation and quality checks to ensure completeness and consistency.
   - Building ETL pipelines that integrate external data sources with a relational database.
   - Using yfinance for historical financial data extraction.
   - Use of environment variables for secure management of database credentials.
   - Handling errors and edge cases, such as missing or delisted data.

## Tools Used
   - Python
   - PostgreSQL
   - Pandas
   - SQLAlchemy
   - Jupyter Notebook
   - yfinance

## Procedures
### Data Extraction
   - Historical stock data was retrieved using yfinance for a specified Apple stock (AAPL) with certain data range.
   - Raw data was reset with proper indexing for further processing.
### Data Transformation
   - Columns were standardized and renamed for consistency with the database schema.
   - Missing values in critical fields like adjusted close were handled.
   - Additional fields such as daily_return and 20-day moving averages (ma_20) were computed.
### Data Validation
   - Checks were implemented to ensure no null trade dates or closing prices existed.
   - Empty datasets or extraction failures raised explicit errors for troubleshooting.
   - Volumes were checked to prevent negative values.
### Data Loading
   - Validated and transformed data was inserted into a PostgreSQL database table named daily_prices.
   - Metadata tracking (etl_metadata) was implemented to store the last loaded date for incremental updates.
     
     <img width="567" height="367" alt="Screen Shot 2026-01-27 at 1 34 02 AM" src="https://github.com/user-attachments/assets/ec6ee212-26c7-489b-8be6-393c6c0323aa" />
### Pipeline Automation
   - The ETL pipeline was wrapped in a Python function that executes extraction, transformation, validation, loading, and metadata update in a single run.
   - Environment variables were used to secure database credentials and enable easy reconfiguration across environments.
     
## Conclusion
  This project successfully built a python based ETL data pipeline that extracts historical stock data from Yahoo Finance for downstream analytics.

