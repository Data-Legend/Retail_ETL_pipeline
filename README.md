# ETL Pipeline for E-Commerce Data

## Project Overview

This project involves building an ETL (Extract, Transform, Load) pipeline to handle e-commerce data. The pipeline extracts data from multiple sources, transforms it by cleaning and aggregating, and then loads the processed data into CSV files for further analysis.

## Steps Overview

### 1. Extract Data

- **Function:** `extract()`
- **Description:** Combines data from the `grocery_sales` table and `extra_data.parquet` file.
- **Output:** `merged_df` - A DataFrame containing data from both sources.

### 2. Transform Data

- **Function:** `transform()`
- **Description:** Cleans the merged data:
  - Fills missing numerical values.
  - Adds a "Month" column.
  - Filters rows where weekly sales exceed $10,000.
  - Drops unnecessary columns.
- **Output:** `clean_data` - The transformed DataFrame.

### 3. Aggregate Data

- **Function:** `avg_monthly_sales()`
- **Description:** Aggregates `clean_data` to compute the average monthly sales:
  - Returns a DataFrame with "Month" and "Avg_Sales" (rounded to 2 decimal places).
- **Output:** `agg_data` - The aggregated DataFrame.

### 4. Load Data

- **Function:** `load()`
- **Description:** Saves the cleaned and aggregated DataFrames as CSV files.
  - `clean_data` is saved as `clean_data.csv`.
  - `agg_data` is saved as `agg_data.csv`.
- **Parameters:**
  - `cleaned_df`: The cleaned DataFrame.
  - `aggregated_df`: The aggregated DataFrame.
  - `cleaned_path`: Path to save the cleaned data CSV.
  - `aggregated_path`: Path to save the aggregated data CSV.

### 5. Validate Files

- **Function:** `validation()`
- **Description:** Checks whether `clean_data.csv` and `agg_data.csv` exist in the current working directory.
