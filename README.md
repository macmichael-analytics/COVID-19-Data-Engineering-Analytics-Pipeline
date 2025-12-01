# COVID-19-Data Engineering Analytics Pipeline

## End-to-End Azure Solution — Ingestion → Transformation → Analytics → ML → Reporting

## 📌 Project Overview
COVID-19 created a global need for accurate, near–real-time reporting of cases, mortality numbers, vaccination trends, and population-normalized metrics. Many organizations struggled with fragmented data sources, inconsistent reporting formats, and lacked the ability to generate timely dashboards for public health stakeholders.

This project builds a real-world enterprise-grade analytics pipeline  using Microsoft Azure to ingest, transform, store, model, and visualize global COVID-19 statistics.

----

## ❗ Business Problem
Public health agencies and analysts require a single source of truth to answer key questions:

- How fast are cases rising across countries/regions?

- Which countries have the highest death rates relative to population?

- What are the weekly/monthly pandemic trends?

- How can machine learning help detect future surges?

- However, the challenges include:

- Multiple external data sources (API, CSV, public datasets).

- Data updated daily requiring automated ingestion.

- Complex transformations (date alignment, aggregation, normalization).

- Need for scalable analytics + centralized data store.

- Need for dashboards accessible by leadership in real-time.
---

## 💡 Solution Summary

This project delivers a fully automated Azure data pipeline that:

1. Ingests COVID-19 case and population data from APIs & Blob Storage.

2. Stores raw datasets in Azure Data Lake Storage Gen2.

3. Transforms & cleans data using Azure Data Factory, Azure Synapse Notebook / Databricks, and SQL transformations.

4. Loads analytics-ready data into Azure SQL Database.

5. Generates ML predictions for case surges (optional).

6. Publishes dashboards to Power BI for public health reporting.
---
# 🏗️ Solution Architecture (Explained)

## 1. Data Sources

- ECDC COVID-19 API → Daily case & death data.

- Population Dataset (CSV) stored in Azure Blob Storage.

2. Ingestion Layer

Azure Data Factory pipeline pulls:

- HTTP API data → Raw zone

- Blob data → Raw zone

- Data stored in Azure Data Lake Gen2 (/raw/covid/)

3. Transformation Layer

Azure Data Factory + Synapse/Databricks used for:

Cleaning & reformatting

Standardizing date fields

Aggregating case numbers

Joining with population datasets

Creating surrogate keys

Generating fact & dimension tables

4. Storage Layer

Azure Data Lake (Raw → Curated Zones)

Azure SQL Database:

dim_country

fact_covid_daily

fact_covid_weekly

fact_population

5. Machine Learning Layer (Optional)

Store features in ADLS

Train ML models (Azure ML):

Time-series forecasting (ARIMA/Prophet)

Hotspot detection

Predict next 7–14 days of cases

6. Reporting Layer

Power BI dashboards connected to Azure SQL Database

Auto-refresh daily
