# Utilization of Machine Learning to Impute and Better Understand Data on Small Island Developing States (SIDS)



<img src="visualizations/cuh_logo.png" width="120" /> <img src="visualizations/cifal_logo.png" width="210" />





### Data

The data source for this project is the [United Nations SDG Indicator Database](https://unstats.un.org/sdgs/dataportal/database)


## Folder Hierarchy
### Importing, Cleaning, Summarising, and Analyzing

When we first import the data, we can see:
  - There are multiple observations for one country and the same indicator. 
      - This is to account for differences in data by year, age, sex, and geographic context for the same country.
      - This is a great idea, *however*, an extremely significant amount of the data is NA with this specific scope. 
      - So we summarise for two reasons:
        1. Have less NA values in the data we analyze
        2. Create a dataframe with one SIDS per row and one sdg indicator per column.
          - This allows us to perform machine learning analysis including clustering and random forest regression



The data is summarised in **two different ways** in two different folders
  - The **most_recent folder** contains data summarised by taking the most recent year of indicator data avaiable for each SIDS by indicator
    - This allows us to compare SIDS utilizing the most recent data available
    - Most of the output data that results is from 2020
    - viz?
    
    - If there are multiple entries for the same indicator, same SIDS, and same year, then the mean of those values is taken
  
  - The **hitorical folder** contains data summarised by taking the mean value of the indicator data across all years, ages, sexes, and geographic contexts
    - This allows us to compare SIDS from a historical perspective


Within the most_recent and historical folders, there are 3 sub folders
  - cleaning_and_summarising
    - Rmd's that import each goal as a csv file and clean/summarise accoding to the folder they are in
  - data_cleaned_and_summarised
    - Result of the cleaning_and_summarising Rmd's
  - analysis
    - Where imputation, clustering, and random forest regression happen 


### Creating a Heat Map of NA Values, Per Goal for Each SIDS

The code for this step of the project can be found in the na_heat_map.Rmd

The goal of this step is to better understand the mising data because ~ 55 % of the data is NA

With the heat map visualization of NA values, we can see the significance of missing data for each SDG Goal in each SIDS

### Utilizing the missRanger Package for Imputation, then Clustering with K Means and Determining Variable Importance with the randomForest Package

The code for this step of the project can be found in:
  - missRanger.Rmd using historical data
  - mossRanger_most_recent.Rmd using the most recent data available

Code Outline:
  - Impute data with missRanger Random Forest Technique
  - Show "true" vs imputed data with a bar plot of one SDG Indicator for each SIDS with "true" data in black and imputed data in blue
  - Cluster data with k means clustering
  - Visualize with fviz_cluster
  - Determine variable importance with random forest regression

### Utilizing the ClustImpute Package for Imputation, then Clustering with K Means and Determining Variable Importance with the randomForest Package


The code for this step of the project can be found in:
  - clustImpute.Rmd using historical data
  - clustImpute_most_recent.Rmd using the most recent data available


Code Outline:
  - Impute data with ClustImpute
  - Show "true" vs imputed data with a bar plot of one SDG Indicator for each SIDS with "true" data in black and imputed data in blue
  - Cluster data with k means clustering
  - Visualize with fviz_cluster
  - Determine variable importance with random forest regression

