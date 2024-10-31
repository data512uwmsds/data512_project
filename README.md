# Wildland Fire Analysis for West Valley City, UT

## Introduction
The goal of this project is to analyze the impact of widespread wildland fires in West Valley City, UT. The project aims to inform policy makers, city managers, city councils, and other civic institutions, to mitigate future impacts from wildfires.

## License
The source data and example code for this dataset is licensed under:
- [Creative Commons Attribution-ShareAlike 3.0 (CC-BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/deed.en)

## Data Sources
### Raw data
1. Wildland Fires Dataset
This analysis uses the [USGS_Wildland_Fire_Combined_Dataset.json](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) dataset from the United States Geological Survey (USGS),
which consolidates multiple records of wildland fire occurences across the U.S. and its territories, spanning from the 1800s to the present. 
The schema:
    - `displayFieldName`
    - `fieldAliases`
    - `geometryType`
    - `spatialReference`
    - `fields`
    - `features`

2. AQI Data
This analysis obtains the [Air Quality Service (AQS) API](https://aqs.epa.gov/aqsweb/documents/data_api.html) from the US Environmental Protection Agency (EPA). The data obtained through the monitoring stations in Salt Lake County. The data collection requests data related to gaseous (CO, SO2, NO2, and O2) & particulate data (PM10, PM2.5, and acceptable PM2.5).


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
#### Part 1 Common Analysis
- `part_1_distance.ipynb`: code for calculating fire distances from the city and predictive model.
- `part_1_aqi.ipynb`: code for querying and analyzing AQI data for the city.
- `part_1_visual.ipynb`:  code for generating visualizations of the fire and AQI data.
