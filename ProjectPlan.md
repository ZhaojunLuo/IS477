# ProjectPlan.md

## Overview  

The overall objective of this project is to investigate the relationship between **urban traffic mobility** and **environmental conditions**, with a particular focus on how transportation patterns influence air quality and weather conditions. In numerous cities, traffic congestion and environmental pollution have become pressing issues, prompting this project to explore the data correlations between human activities and environmental conditions. This project aims to establish a reproducible workflow that integrates and organizes multi-source open datasets, cleans them, and ultimately uncovers the underlying mechanisms behind these correlations.

We will explicitly use the data lifecycle model introduced in class (Module 1) as the framework for our work. This means that we will:  
- Collect or acquire data from multiple sources (Module 3).  
- Store and organize them using structured schemas and conventions (Modules 4-5).  
- Integrate and enrich the datasets to align them in terms of time and space (Modules 6-8).  
- Assess and clean the quality of the data (Modules 9-10).  
- Automate the workflow to ensure reproducibility and provenance (Modules 11-12).  
- Document metadata and provide transparency for reuse (Modules 13-15).  

---

## Research Questions  

1. **Mobility and Air Quality:** Does variation in bike-sharing activity or traffic volume correlate with changes in air quality (e.g., PM2.5 or ozone levels)?  
2. **Weather Effects:** How do weather conditions such as temperature, humidity, or wind speed influence both urban mobility and air quality?  
3. **Prediction:** Can we predict pollution peaks using combined data on mobility and weather, and how accurate are such models?  

---

## Team  

This project is collaborated by Jimmy Qiu and Frankie Luo. Both members in our group has clearly defined responsibilities.  

Jimmy Qiu: Collects datasets from APIs and portals; Writes scripts for merging, handles missing values and outliers, building automation.
Frankie Luo: Defines database schemas, repository structures, and naming conventions. Ensures compliance with licensing and ethics, and reproducibility, and prepares metadata and documentation.

---

## Datasets  

We will integrate **two heterogeneous datasets** from trustworthy sources:  

1. **Air Quality Dataset**  
   - **Source:** EPA AirNow API (JSON).  
   - **Link:** https://docs.airnowapi.org/
   - **Contents:** Air quality index, PM2.5, ozone, timestamp, and location.  
   - **Acquisition:** Retrieved via API queries with filters.  
   - **Ethical/Legal:** Licensed for public research.  

2. **Urban Mobility Dataset**  
   - **Source:** NYC CitiBike trips dataset (CSV).  
   - **Link:** https://citibikenyc.com/system-data
   - **Contents:** Trip start/end times, station IDs, coordinates, and ride durations.  
   - **Acquisition:** Downloaded from the official open data portal.  
   - **Ethical/Legal:** Publicly available, anonymized data.  

These datasets are chosen because they differ in **format (JSON vs CSV)** and **access method (API vs bulk download)**.

---

## Timeline  

| Week | Task | Responsible | Related Module |
|------|------|-------------|----------------|
| 1 | Finalize datasets, review licensing/ethics | Frankie Luo | Modules 2-3 |
| 2 | Define repository structure and schema | Frankie Luo | Modules 4-5 |
| 3 | Acquire datasets (API queries, downloads) | Jimmy Qiu | Module 3 |
| 4 | Load into database/filesystem, organize | Jimmy Qiu | Modules 4-5 |
| 5 | Write integration scripts (joins, merges) | Jimmy Qiu | Modules 7-8 |
| 6 | Perform data quality assessment | Jimmy Qiu | Module 9 |
| 7 | Apply cleaning and enrichment | Jimmy Qiu | Module 10 |
| 8 | Build workflow automation (scripts/Makefile) | Jimmy Qiu | Modules 11-12 |
| 9 | Prepare metadata and documentation | Frankie Luo | Module 15 |
| 10 | Final analysis, visualizations, and report | All | Modules 13-15 |

---

## Constraints  

- **API rate limits**: AirNow API may limit daily requests.  
- **Data availability**: Historical air quality records may be restricted.  
- **Integration complexity**: Aligning different temporal/spatial resolutions may require advanced joins.  
- **Team schedules**: Requires coordination through GitHub issues and PRs.  

---

## Gaps  

1. **Metadata standards**: Need to confirm whether to adopt Dublin Core or schema.org.  
2. **Additional datasets**: Considering weather data from NOAA to strengthen integration.  
3. **Predictive analysis scope**: Final decision depends on dataset quality and completeness.  

---

## Compliance with Course Modules  

- **Module 1 (Lifecycle):** Workflow aligned with lifecycle model.  
- **Module 2 (Ethics):** Licensing and anonymization verified.  
- **Module 3 (Acquisition):** Two heterogeneous datasets acquired.  
- **Modules 4-5 (Storage/Organization):** Database schema + filesystem conventions.  
- **Modules 7-8 (Integration):** Dataset merging with Pandas/SQL.  
- **Module 9 (Quality):** Quality assessment documented.  
- **Module 10 (Cleaning):** Cleaning steps applied and recorded.  
- **Modules 11-12 (Automation):** Automated, end-to-end workflow.  
- **Module 13 (Reproducibility):** Repo contains sufficient documentation for reproduction.  
- **Module 15 (Metadata):** Metadata and data documentation prepared.  

---

## Conclusion  

This project plan establishes a structured and reproducible path for analyzing the relationship between urban mobility and environmental conditions. By integrating heterogeneous datasets, applying cleaning and quality checks, and automating the workflow, we will produce insights into urban-environmental interactions and a reusable framework for future data science efforts.  

