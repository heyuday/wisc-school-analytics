#  Wisconsin School Data Analytics (Google Cloud)

End-to-end data engineering project using **Google Cloud Platform** to analyze public and private school data across Wisconsin.  
This project integrates **Google Cloud Storage (GCS)**, **BigQuery**, and **Dataform** for scalable ETL and geospatial analytics.

<img width="400" height="300" alt="image" src="https://github.com/user-attachments/assets/37edcaf6-3a37-43dc-a907-aefe4ec6213c" />

---

##Overview

- **Goal:** Build a complete data pipeline for educational data analytics.  
- **Stack:** Python, PyArrow, Google Cloud Storage, Dataform, BigQuery, Pandas.  
- **Dataset:** Wisconsin school records (public + private) enriched with county-level geographic data.

---

##  Architecture

- **Data Ingestion:** Upload raw `.parquet` dataset to GCS.  
- **Transformation:** Create SQLX models in Dataform:
  - `wi_counties.sqlx` — selects Wisconsin counties (FIPS 55)  
  - `schools.sqlx` — loads school data from GCS into BigQuery  
  - `wi_county_schools.sqlx` — joins schools to county polygons via geospatial functions  
- **Analytics:** Run BigQuery queries to derive insights:
  - Count schools per county  
  - Filter by public/private agencies  
  - Compute nearest high schools for each middle school in Dane County  

---

## Sample Outputs

- **Total public schools:** 2,116  
- **Top counties by school count:** Milwaukee, Dane, Waukesha  
- **Geospatial mapping:** Each school mapped to a `ST_GEOGPOINT` location  

##  Highlights

- **Google Cloud Dataform** for modular SQL pipelines  
- **BigQuery GIS** for county–school geospatial joins  
- **PyArrow & GCS** for efficient data serialization  
- **Jupyter-based pipeline orchestration**  
- **Fully reproducible on GCP VM or local Colab setup**
