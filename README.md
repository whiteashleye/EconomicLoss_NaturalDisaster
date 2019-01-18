# Natural Disasters and Estimated Economic  Impact

---
## Project Authors: 

Drew Hoppes  - [LinkedIn](https://www.linkedin.com/in/drew-hoppes)

Tri Nguyen   - [LinkedIn](https://www.linkedin.com/in/tri2bnguyen)

Chris Shaw   - [LinkedIn](https://www.linkedin.com/in/christopherjshaw982)

Ashley White - [LinkedIn](https://www.linkedin.com/in/aewhite5/)

---
## Introduction

Every year there are a number of natural disasters that effect a local population in the United States.  The ability to predict potential wage loss from certain natural disasters around the US would provide real time support for future natural disasters.  Allowing government response and intervention to ensure that the local economy can recover with minimal impact to the displaced.   

In order to take the initial step for a proof of concept. A method was created to collect employment information and sector-specific wage estimations (such as Glassdoor and Indeed) to predict the potential wage loss due to a natural disaster.  Based on the dataset, the tool will provide an estimation about the projected economic loss in a given locality based on the reported or estimated wage loss in the locality.

---
## Data Collection

| Data Name | Description | Link |
| --- | --- | --- |
| US Census QWI Data (QWI) | Collection of US Census Quarterly Work Force Indicator data in the US by state and county | [Link](https://www.census.gov/data/developers/data-sets/qwi.html)|
| FEMA Disaster Data (FEMA) | All FEMA declared disaster since 1953 data set by state and county | [Link](https://www.fema.gov/openfema-dataset-disaster-declarations-summaries-v1) |
| US Unemployment Claims (ETA) | US Labor and Statistics searchable database for all US Weekly unemployment claims by state and county | [Link](https://workforcesecurity.doleta.gov/unemploy/claims.asp) |
| US Disaster Unemployment Assistance (DUA)| US Labor and Statistics searchable database for all US Weekly assistnace claims by state and county due to a natural disaster | [Link](https://workforcesecurity.doleta.gov/unemploy/dua_activities.asp)|

--- 
## Methodology 

#### FEMA and QWI Data 
- Analyzed FEMA data and Quarterly Work Force data to examine trends in the data set to get an initial bearing of the data sets and identify key areas to investigate 
    - ARIMA and SARIMAX to plot to the trends over a time series with the QWI dataset based on monthly quarterly earnings
    
#### FEMA with QWI Data
- Combined FEMA and QWI datasets to evalue the predictive abilities of quarterly earnings and natural disasters
    - Logisitic Regression and Random Forrest Regressor to see if there wer any correlation with the two datasets.  
    
#### HUA - ETA - FEMA Data     
- Analyzed HUA and ETA datasets in order to identify trends on a weekly and monthly view of specific county to examine trends in relation to natural disasters in the area
    - Calculated economic loss using the SARIMAX model to predict expected trends in timeseries and difference in actual economic data at disaster event.  

---
## Executive Summary

### Problem Statement
- Can we use public / private data sources to estimate the expected economic wage loss due to a disaster

### Data Collection and Analysis

A number of resources were utilized in order to collect the necessary datasets for analysis. The US Labor and Statistics, US Census QWI Data, US Unemployment Claims datasets were gather using webscrapping and APIs in order to get the datasets that aligns with the core objective. FEMA Disaster Data was easily accessible as a CSV file. 

Initial analysis of QWI there were positive trends with the major states with seasonal fluctuations over quarterly reports.  The top 10 states were examined to see if the fluctuations coincided with natural disasters reported for the state.  The high-level view showed that there quarterly occurrence of natural disasters but a clear correlation with the natural disasters weren’t apparently clear. 

Combining the datasets QWI and FEMA data based on quarterly time, state, and county.  Analysis of the quarterly data based on the natural disaster occurrence showed a low correlation between the expected average quarterly earnings for specified county. Quarterly perspective of data meant that there were too many factors to accurate correlate the two datasets and a more granular approach had to be taken. 
Examination of Houston, TX and unemployment claims provided clear visualization of a natural disasters impact on the employment and economic outlook over time.  

### Conclusion 

There are multiple research and studies indicating that there is an economic impact on areas effected by a FEMA designated natural disaster.  A quarterly view of economic data and earnings are too broad to model and predict a possible economic impact due to a natural disaster.  Since it is a quarterly view of economic output for a specific county and state there are too many factors to contend with in addition to a natural disaster.  The initial result of the FEMA and QWI data together showed a low correlation less than 10% and low predictive capabilities. 
A more granular approach to economic loss due to a natural disaster would be more advantageous to creating a tool to calculate wage loss and possibly predict economic impact of future natural disasters.  On average a natural disaster displaces residences for less than 30 days, meaning that the local impact should only be examined on a time series where economic data is on a week or a monthly basis. 
When examining Houston, TX between 2016-2018 for unemployment claims on a weekly basis, there is a downward trends of unemployment claims.  The 2017 Hurricane Harvey event saw a spike in unemployment claims.  There is a delta from expected unemployment claims and actual unemployment claim in the month that Hurricane Harvey occurred. 
 This provides a proof of concept that the economic wage can be calculated as well capabilities to model and predict.  However, the important criteria will have to be the granular level of the timeseries data in terms of week or month.  

### Next Step

1. Standardize disaster metrics (fatalities or severity scales) in corporate more robust data for the FEMA natural disaster data
2. Migration rates for affected areas to provide a comprehensive economic loss or gain due to employee migration 
3. Incorporate Current Population Survey to track evacuees and displaced workers to get granular level data
4. Scale for counties nationally for a more predictive models that include other natural disasters around the US
