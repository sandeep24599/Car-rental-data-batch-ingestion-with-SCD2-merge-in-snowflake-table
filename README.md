# Car-rental-data-batch-ingestion-with-SCD2-merge-in-snowflake-table
Data pipeline for processing and ingesting car rental data using PySpark, Airflow, GCP Dataproc, and Snowflake.
# Car Rental Data Batch Ingestion with SCD2 Merge in Snowflake

This project is designed to create a comprehensive data pipeline for ingesting and processing car rental data. The pipeline is implemented using a combination of Python, PySpark, GCP Dataproc, Airflow, and Snowflake. The primary objectives of this project are to build a dimensional data model, perform SCD2 (Slowly Changing Dimension Type 2) merge on the `customer_dim` table, and populate the `rentals_fact` table with processed data.

## Project Overview

### Tech Stack
- **Python**
- **PySpark**
- **GCP Dataproc**
- **Airflow**
- **Snowflake**

### Data Model
The project includes the following dimensional tables:
1. **`location_dim`**: Stores location details for pickup and dropoff.
2. **`car_dim`**: Stores car details including make, model, and year.
3. **`date_dim`**: Stores date details to facilitate time-based analysis.
4. **`customer_dim`**: Stores customer details with SCD2 merge support.
5. **`rentals_fact`**: Fact table that stores rental transactions with foreign keys to the dimensions.

### Pipeline Steps
1. **Snowflake Table Creation**: Create static tables (`location_dim`, `date_dim`, `car_dim`) in Snowflake and define the `customer_dim` and `rentals_fact` tables with the necessary schema to support data ingestion and SCD2.
   
2. **Data Ingestion**: The raw data is ingested using PySpark and processed on GCP Dataproc.

3. **Airflow Orchestration**: Use Apache Airflow to orchestrate the entire data pipeline, from ingestion to transformation, and loading into Snowflake.

4. **SCD2 Merge**: Implement SCD2 merge logic in PySpark for the `customer_dim` table to maintain historical data. This ensures that changes in customer data over time are tracked accurately.

5. **Fact Table Population**: Populate the `rentals_fact` table with the processed data, ensuring that it references the correct dimension records.

## Getting Started

### Prerequisites
- **Python**: Ensure Python is installed on your local machine.
- **PySpark**: Install PySpark using pip.
- **GCP Account**: Set up GCP with Dataproc and Airflow.
- **Snowflake Account**: Ensure you have access to a Snowflake instance.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repository.git
