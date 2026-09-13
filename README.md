# Middle-Mile Logistics Exception & Root-Cause SQL Analytics

## Overview
This repository contains production-ready Amazon Athena / SQL queries developed to analyze **32,065 logistics shipments** across middle-mile transportation networks. The objective of this analysis is to identify systemic network risks, quantify delivery-deviation hours, and pinpoint operational bottlenecks across port congestion and carrier corridors.

## Key Project Results
* **32,065 Shipments Analyzed**: Evaluated fleet telemetry using SQL CTEs and window functions.
* **74.67% High-Risk Exposure**: Identified 23,944 shipments exceeding disruption risk thresholds.
* **166,021 Deviation Hours**: Quantified cumulative delivery delays across high-risk corridors.
* **13,507 Exception Prioritizations**: Isolated shipments with >5.0 hours of delivery deviation for immediate operational intervention.

## Query Architecture & Repository Structure
The SQL scripts in this repository are organized sequentially:

1. `queries/01_data_cleaning_eda.sql`  
   * Deduplication, null value handling, and baseline distribution checks across telemetry features.
2. `queries/02_risk_classification.sql`  
   * Employs Common Table Expressions (CTEs) and `RANK()` / `SUM() OVER()` window functions to categorize risk tiers (`High-Risk` vs `Baseline`).
3. `queries/03_root_cause_analysis.sql`  
   * Multi-variable diagnostic queries analyzing port congestion indices (>7.0), driver fatigue flags (>0.70), and high-risk route corridors.
4. `queries/04_exception_filtering.sql`  
   * Queries supporting automated exception reporting pipelines and Control Tower operational reviews.

## Tech Stack
* **SQL Dialect**: AWS Athena / ANSI SQL
* **Techniques Used**: CTEs, Window Functions (`ROW_NUMBER`, `DENSE_RANK`, `SUM OVER`), Multi-Table Joins, Conditional Aggregations (`CASE WHEN`), Subqueries.
* **Integration**: Consumed by Excel VBA and Power BI dashboards.

## License
MIT License - feel free to adapt and reference these query patterns.
