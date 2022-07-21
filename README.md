# Utilization of Machine Learning to Impute and Better Understand Data on Small Island Developing States (SIDS)



<img src="visualizations/cuh_logo.png" width="120" /> <img src="visualizations/cifal_logo.png" width="210" />





### Data

The data source for this project is the [United Nations SDG Indicator Database](https://unstats.un.org/sdgs/dataportal/database)

### Importing, Cleaning, and Summarising

The code for this step of the project can be found in the import_tidy_join.Rmd

The goal of this step is to end up with a dataframe that has one SIDS per row and one sustainable development goal indicator (ex: proportion of population living below the international poverty line) per column.

The initial data contains columns for age, sex, urban vs rural, and year (spanning from 2005 to 2021), however, most these columns have significant numbers of NA values (> 70%) so we summarise the data by taking the median value of age, sex, year, and urban vs rural geography. This allows us to have as little NA values as possible, although the number of NA's is still significant, and keep the dataframe to one SIDS per row and one sdg indicator per column.


### Creating a Heat Map of NA Values, Per Goal for Each SIDS

The code for this step of the project can be found in the na_heat_map.Rmd

The goal of this step is to better understand the mising data because ~ 55 % of the data is NA

With the heat map visualization of NA values, we can see the significance of missing data for each SDG Goal in each SIDS

### Utilizing the missRanger Package for Imputation, then Clustering with K Means and Determining Variable Importance with the randomForest Package

The code for this step of the project can be found in the missRanger.Rmd

Code Outline:
  - Impute data with missRanger Random Forest Technique
  - Show "true" vs imputed data with a bar plot of one SDG Indicator for each SIDS with "true" data in black and imputed data in blue
  - Cluster data with k means clustering
  - Visualize with fviz_cluster

### Utilizing the ClustImpute Package for Imputation, then Clustering with K Means and Determining Variable Importance with the randomForest Package


The code for this step of the project can be found in the clustImpute.Rmd

Code Outline:
  - Impute data with ClustImpute
  - Show "true" vs imputed data with a bar plot of one SDG Indicator for each SIDS with "true" data in black and imputed data in blue
  - Cluster data with k means clustering
  - Visualize with fviz_cluster

