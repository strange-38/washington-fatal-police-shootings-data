# Washington Fatal Police Shootings Data Analysis

## Overview
This repository contains Python scripts used for analyzing fatal police shootings in Washington using PySpark on the Databricks platform. The analysis consists of multiple steps, each performed using separate scripts, to clean, process, and analyze the data.

## Repository Link
[Washington Fatal Police Shootings Data](https://github.com/strange-38/washington-fatal-police-shootings-data)

## Python Scripts in `python_scripts` Folder
The `python_scripts` folder contains the following Python scripts used in the data analysis pipeline:

### 1. Census Bureau – API Fetch Data
- Fetches population data classified by race from the U.S. Census Bureau website.
- Performs data harmonization and calculates the percentage distribution of races.
- Assigns rankings based on racial distribution from 2015 to 2023.

### 2. Split Filled-Missing Counties
- Splits the fatal police shootings dataset into two files:
  - One containing county information.
  - Another for records with missing county data.

### 3. Correct Misspelled Cities - GeopPy Impute Counties
- Corrects misspelled city names.
- Uses the `geopy` library to impute missing county information based on city and state data.

### 4. Merge All Imputed Data
- Merges imputed data with the original dataset containing county information.
- Computes various statistics, including:
  - Percentage of shootings by race.
  - Race-based shooting rankings.
  - Mean yearly shootings.
  - Other key measures.

### 5. Racial Disparity Analysis
- Performs time-series analysis by year.
- Merges population and shootings data using `county`, `race`, and `year` as key columns.
- Computes and compares:
  - Percentage of racial population vs. percentage of racial shootings.
  - Race population rank vs. race shooting rank.
- Identifies counties facing persistent, intermittent, and multiracial disparities.

## Requirements
The analysis relies on the following key technologies and libraries:
- **PySpark** for big data processing.
- **Databricks** for scalable cloud-based analytics.
- **Geopy** for geographical data processing.
- **U.S. Census Bureau API** for population data retrieval.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/strange-38/washington-fatal-police-shootings-data.git
   ```
2. Navigate to the `python_scripts` folder:
   ```bash
   cd washington-fatal-police-shootings-data/python_scripts
   ```
3. Run individual scripts in a PySpark environment on Databricks as needed.

## Acknowledgments
This project utilizes publicly available data sources, including the U.S. Census Bureau and police shootings datasets, to analyze racial disparities and trends in fatal police shootings.

