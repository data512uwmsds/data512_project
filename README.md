# Wildland Fire Analysis for West Valley City, UT

## Introduction
The goal of this project is to analyze the impact of widespread wildland fires in West Valley City, UT. The project aims to inform policy makers, city managers, city councils, and other civic institutions, to mitigate future impacts from wildfires.

## License
The source data and example code for this dataset is licensed under:
- [Creative Commons Attribution-ShareAlike 3.0 (CC-BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/deed.en)

## Data Sources
### Raw data
1. **Wildland Fires Dataset**   
This analysis uses the [USGS_Wildland_Fire_Combined_Dataset.json](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) dataset from the United States Geological Survey (USGS),
which consolidates multiple records of wildland fire occurences across the U.S. and its territories, spanning from the 1800s to the present. 
The schema:
    - `displayFieldName`
    - `fieldAliases`
    - `geometryType`
    - `spatialReference`
    - `fields`
    - `features`

2. **AQI Data**     
This analysis obtains the [Air Quality Service (AQS) API](https://aqs.epa.gov/aqsweb/documents/data_api.html) from the US Environmental Protection Agency (EPA). The data obtained through the monitoring stations in Salt Lake County. The data collection requests data related to gaseous (CO, SO2, NO2, and O2) & particulate data (PM10, PM2.5, and acceptable PM2.5).

3. **IHME Data**
This analysis also obtain data from [Global Burden of Disease Study](https://vizhub.healthdata.org/gbd-results/) from the Institute for Health Metrics and Evaluation (IHME). The Global Burden of Disease Study provides estimates of the burden of diseases, injuries, and risk factors. It includes data on mortality, morbidity, and risk factors for various diseases and injuries. It is stratified by age, sex, and geography, allowing for detailed analysis of health trends and disparities. The dataset is used to understand the health impacts of wildland fires on the population of West Valley City, UT, by correlating health outcomes with smoke and air quality data. The data, however, is at state-level and not on the same county level as AQI data. I minimize access to sensitive healthcare data by querying only the data related respiratory illnesses and risk causes related to air pollution.
Data is stored as `data/IHME-GBD_2021_DATA-Utah.csv`.
Significant columns from this dataset used in the analysis:
- `cause_name`: Name of the disease or injury.
- `metric_name`: Metric (e.g., deaths, DALYs) used for the `val`, `upper`, and `lower` columns.
- `val`: Value of the metric.
- `upper`: Upper bound of the confidence interval.
- `lower`: Lower bound of the confidence interval.
- `year`: Year of the data.

### Output 
The `data/figure` folder contains the following figures used in the report:
1. `fires_histogram.png`: A histogram showing the distribution of wildland fires over the years in West Valley City, UT.
2. `annual_acres_burned.png`: A line chart depicting the annual acres burned by wildland fires in West Valley City, UT within 650 miles.
3. `smoke_gas_particulate.png`: A multi-line chart illustrating the levels of gaseous and particulate pollutants over time in West Valley City, UT.
4. `acres_burned_cumulative_smoke.png`: A multi-line chart showing the relationship between cumulative smoke estimates and acres burned by wildland fires.
5. `utah_data_dist.png`: A bar chart of various health metrics distribution related to respiratory illnesses in Utah from IHME data.
6. `death_by_illnesses.png`: A line chart representing the number of deaths by different respiratory illnesses with shaded confidence interval in Utah.

These figures provide visual insights into the data analysis conducted in the project.

### Intermediate Data
Find intermediate data [here](https://drive.google.com/drive/folders/1y2Y7d4Ub1OpWUXfFkIDTmYiJFBVUp7zg?usp=sharing).
- `fire_distance_data.csv`: contains distance calculations between fires and West Valley, UT.
- `nearby_fires.csv`: lists fires within the 650-mile range to West Valley, UT.
- `cumulative_smoke.csv`: contains yearly cumulative smoke estimates for the city.
- `gas_aqi_data.csv` or `gas_aqi_data.json`: gaseous AQI pollutant data (CO, SO2, NO2, and O2).
- `part_aqi_data.csv` or `part_aqi_data.json`: particulate AQI pollutant data (PM10, PM2.5, and acceptable PM2.5).
- `gas_df_filtered.csv`: filtered data for gaseous pollutants to non-null values and only columns of interest.
- `part_df_filtered.csv`: filtered data for particulate pollutants to non-null values and only columns of interest.

### Code
- `part_1_smoke.ipynb`: code for calculating fire distances from the city and predictive model.
- `part_1_aqi.ipynb`: code for querying and analyzing AQI data for the city.
- `part_1_visual.ipynb`:  code for generating visualizations of the fire and AQI data.
- `part_2`: code for transforming IHME data and building regression between smoke, fire, AQI data and IHME data.

## Final Report
The final report consolidates the findings from the analysis of wildland fires, air quality, and health impacts in West Valley City, UT. It includes detailed descriptions of the data sources, methodologies, and results. 
The report is stored as `data/output/Project Report.pdf`.