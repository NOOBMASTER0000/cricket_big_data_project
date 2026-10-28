# 🏏 Cricket Data Pipeline with PySpark and Databricks

A learning project that processes cricket match data from an API using Python, PySpark, and Databricks.

The pipeline follows a Bronze, Silver, and Gold architecture to organize data from raw API responses into clean tables and analytics.

## Architecture

Cricket API → Raw JSON → Bronze Layer → Silver Layer → Gold Layer → Insights

| Layer | Purpose |
|-------|---------|
| Bronze | Store raw API responses |
| Silver | Convert raw JSON into a structured match table |
| Gold | Prepare summaries for analysis |

## Technologies

- Python — JSON parsing and data handling
- PySpark — Data transformation and aggregation
- Databricks — Notebook development and table processing
- GitHub — Version control and project documentation
- draw.io — Pipeline architecture diagram

## Data Processing Flow

1. Retrieve cricket match data from the API.
2. Store the raw JSON response in the Bronze layer.
3. Extract match records from the JSON.
4. Structure and clean the records in the Silver layer.
5. Build Gold tables for analysis.
6. Explore the results to generate insights.

## Project Tables

The project uses these Databricks tables:

- `workspace.default.cricket_bronze_current_matches`
- `workspace.default.cricket_silver_current_matches`

## Getting Started

1. Open the project notebooks in Databricks.
2. Configure access to your cricket API.
3. Update table names to match your catalog and schema.
4. Run the Bronze ingestion notebook.
5. Run the Silver transformation notebook.
6. Run the Gold analysis notebook when available.

Keep API keys in a secret store rather than committing them to GitHub.

## Example: View Silver Data

```python
silver_df = spark.table(
    "workspace.default.cricket_silver_current_matches"
)

display(silver_df)
