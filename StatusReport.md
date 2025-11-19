# Interim Status Report - Milestone 3
**Course:** IS477  
**Project Title:** Air Quality & Urban Mobility Trends in New York City  
**Team Members:** Frankie Luo, Jimmy Qiu  
**Date:** November 2025  

---

## 1. Update on Project Tasks

This project investigates how environmental conditions, particularly OZONE and PM2.5 concentrations, may be associated with patterns of human mobility in New York City. The project integrates two distinct datasets: AirNow air quality data and CitiBike ride-level mobility data. Our goal is to identify whether short-term air quality fluctuations correspond to observable changes in mobility behavior. The following sections outline the progress made on each major component described in the original project plan and reference the artifacts that have been committed to the repository.

### Data Acquisition  
The acquisition phase for both datasets has been fully completed. AirNow pollutant observations for June 1-14, 2023 were retrieved manually from the AirNow Historical Observation portal. While the initial project plan intended to use the AirNow API, repeated connection and authentication failures in the PrairieLearn environment led to a switch to manual downloads. This approach ensured that pollutant observations for each of the 14 days were complete and accurately formatted. Each file includes hourly OZONE and PM2.5 readings, associated pollutant categories, and metadata about the reporting region.

CitiBike data for June 2023 was downloaded directly from the official open-data website. The dataset was provided across four large CSV files, each containing thousands of ride entries. These entries include start and end times, station locations, rider types, and trip duration. The four files were placed in the data/raw/citibike/ directory and served as the foundation for the preprocessing tasks that followed.

### Data Cleaning and Preprocessing  
Data cleaning and preprocessing were implemented in two notebooks: Airnow_dataset.ipynb and CitiBike_dataset.ipynb. These notebooks contain the complete reproducible workflow.

For the AirNow dataset, preprocessing steps included column standardization, timestamp normalization, pollutant filtering, handling missing values, and aggregating hourly readings into daily averages. After processing, we verified that each day in the June 1-14 window contained complete pollutant information, ensuring that no gaps would compromise the merged dataset later in the project. The processed outputs were exported to the data/processed/ directory.

For the CitiBike dataset, the four raw CSV files were merged and cleaned to remove incomplete or erroneous entries. We standardized timestamp formats, extracted relevant fields (such as date and hour), and produced two analytical datasets: a daily aggregated dataset that captures overall mobility trends, and an hourly dataset that allows for more granular analysis. Both processed versions align with the AirNow time window and have been stored in the processed directory.

### Repository Organization and Documentation  
The repository now follows a clean and transparent structure to support full reproducibility. Raw data, processed outputs, preprocessing notebooks, and documentation are clearly separated and labeled. This structure makes it possible for an external reviewer to rebuild the processed datasets entirely from the raw data and provided notebooks. The decision to maintain strict separation between raw and processed files reinforces data integrity and prevents accidental overwriting. The repository is now fully prepared for the analytical phase.

### Preparation for Integration  
Having completed preprocessing, we evaluated the datasets for alignment. The AirNow and CitiBike datasets share the same 14-day period, and both include date fields in a consistent format. This makes merging straightforward and ensures that each day's pollutant measurements line up directly with the corresponding mobility data. The preparation completed in Weeks 11-12 has positioned the project to proceed smoothly into analytical tasks once Week 13 begins.

---

## 2. Updated Timeline and Task Status

### Weeks 1-6 (Completed)  
During the early phase of the project, the team finalized the research topic, constructed the project plan, examined initial samples of both datasets, and developed the repository structure. Time was also spent identifying the key variables required for the analysis, confirming that the necessary data was publicly available, and outlining the preliminary analytical strategy.

### Weeks 7-10 (Completed)  
The middle portion of the timeline focused heavily on data collection and data cleaning. All raw AirNow and CitiBike files were successfully downloaded, reviewed, and prepared for further processing. Each dataset required unique cleaning steps, including restructuring columns, merging files, validating timestamps, and producing aggregated outputs. By the end of Week 10, both datasets had been transformed into clean, analysis-ready forms.

### Weeks 11-12 (Completed)  
During these weeks, the team verified data quality, performed detailed checks to ensure both datasets aligned perfectly in time, and organized the repository to meet reproducibility standards. Additional refinements were made to both cleaning workflows. This status report was drafted, and all necessary files for Milestone 3 were committed to the repository.

### Weeks 13-15 (Upcoming)  
The remaining timeline includes merging the datasets, conducting exploratory data analysis, producing visualizations, and examining daily and hourly patterns. We will explore whether short-term changes in pollutant levels correspond with observable shifts in CitiBike usage. The final report and presentation materials will also be produced during this period. All remaining milestones are expected to be completed before the end of Week 15.

---

## 3. Changes to the Project Plan

### Adjustment of Analysis Window  
The initial plan proposed analyzing the entirety of June 2023. However, after reviewing completeness across datasets, the team selected the June 1-14 window because these dates had fully aligned and high-quality observations for both AirNow and CitiBike. This adjustment improves the reliability of the analysis while reducing unnecessary processing overhead.

### Revision of AirNow Download Method  
API access was originally intended for collecting the AirNow data, but technical restrictions in the PrairieLearn environment made this unfeasible. Manual downloads were adopted instead, ensuring the accuracy and completeness of all pollutant observations.

### Addition of Hourly Mobility Aggregation  
To strengthen the analytical possibilities, the team expanded the CitiBike preprocessing pipeline to include an hourly aggregated dataset. This addition was not part of the original plan but now provides an opportunity to explore finer-grained relationships between air quality and mobility behavior.

These changes improve the project's analytical potential while remaining consistent with the original research goals.

---

## 4. Team Member Contributions

Both team members contributed to completing the tasks required for this milestone. 

Frankie Luo worked on acquiring the datasets, performing data cleaning and preprocessing for both AirNow and CitiBike, generating the processed outputs, preparing documentation, and organizing the repository. 

Jimmy Qiu contributed by reviewing the raw files, checking the data quality during cleaning, validating timestamp conversions, helping refine the analysis window, working on dataset exploration, and providing feedback on the project structure and workflow. 

Through these combined efforts, all tasks outlined for Milestone 3 were successfully completed on schedule.
