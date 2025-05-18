# Chicago Crime Analysis (2019–2023)

**Author:** Yu-Hsuan (Monica) Ko  
**Course Project - Applied Data Science**

## Overview

This project investigates crime patterns in Chicago from 2019 to 2023 using a dataset of over 1.1 million records from the [City of Chicago Data Portal](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2). The analysis includes:

- Temporal and spatial crime trends  
- Crime type distributions  
- Predictive modeling of arrest likelihood  

Project goal is to uncover patterns that could help inform public safety decisions and resource allocation.

## Dataset

- Size: 1,185,534 records  
- Time Range: 2019–2023  
- Features: Date, location, crime type, arrest status, coordinates, etc.

### Data Cleaning

- Removed duplicates (based on `Case Number`)  
- Handled missing values in location-related columns  
- Renamed columns for clarity  
- Converted timestamps into year, month, day, and hour  
- Created dummy variables for categorical features  

Final cleaned dataset contains 1,166,663 rows and 264 columns.

## Exploratory Data Analysis (EDA)

- Temporal Patterns: Crimes dropped in early 2020 (likely due to COVID-19), then rose again with seasonal fluctuations  
- Spatial Patterns: Downtown and high-density areas show higher crime rates  
- Hourly Trends: Crimes peak around midnight, with lowest activity from 4–6 AM  
- Top Crime Types: Theft, battery, criminal damage, and assault dominate

## Predictive Modeling

### Objective

Predict the probability of an arrest based on crime characteristics.

### Model: Logistic Regression

- Response Variable: `Arrest`  
- Sample Size: 100,000 rows  
- Predictors: Crime type, time, longitude, etc.  
- Final Features: 23 variables after cleaning and selection

### Performance

- Precision: 0.80  
- Recall: 0.39  
- AUC: 0.81  

### Key Findings

- High-Arrest Predictors: Narcotics, weapons violations, prostitution  
- Low-Arrest Predictors: Criminal damage, deceptive practices, and geography (longitude)

## Limitations

- Low recall suggests the model misses many actual arrests  
- Limited contextual features (e.g., officer behavior, suspect profile) affect model performance  
- Data may reflect underreporting or systemic enforcement biases


## Future Work

- Explore advanced models (Random Forest, XGBoost)  
- Incorporate socioeconomic and police deployment data  
- Address class imbalance and explore oversampling techniques  
- Perform neighborhood-level policy simulations
