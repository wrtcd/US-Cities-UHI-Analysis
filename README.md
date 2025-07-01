# US-Cities-UHI-Analysis

This repository provides monthly Urban Heat Island (UHI) intensity data for five major U.S. cities from 2015 to 2022. UHI is calculated as the temperature difference between urban and surrounding rural areas using MODIS land surface temperature and land cover datasets. The analysis was conducted using Google Earth Engine.

## Study Area

The analysis covers the following metropolitan regions, each buffered by 25 kilometers:

- Atlanta, Georgia
- Phoenix, Arizona
- Chicago, Illinois
- Los Angeles, California
- New York City, New York

## Data Sources

- MODIS Land Surface Temperature (MOD11A2, 8-day, 1 km resolution)
- MODIS Land Cover Type (MCD12Q1, annual, 500 m resolution)

## Temporal Coverage

- January 2015 through December 2022

## Methodology

1. Monthly composites of daytime land surface temperature (LST) were generated using the MOD11A2 product.
2. Land cover classifications from the MCD12Q1 dataset were used to define urban pixels (LC_Type1 = 13) and rural surroundings (LC_Type1 = 10, 12, 14).
3. For each city and month, the mean daytime LST was computed separately for urban and rural areas.
4. UHI intensity was calculated as the difference:  
   `UHI = Urban Temperature - Rural Temperature`
5. Monthly UHI values were compiled into a structured dataset.

## Output

- `UHI_Cities_2015_2022.csv`: Contains the following columns:
  - `city`
  - `month`
  - `urban_temp_C` (mean daytime temperature over urban areas)
  - `rural_temp_C` (mean daytime temperature over rural areas)
  - `UHI_C` (urban–rural temperature difference in °C)

- A sample time-series chart is viewable in the Earth Engine Console for visual inspection.

## Applications

This dataset supports research and analysis in:

- Urban climate and heat risk studies
- Environmental monitoring and resilience planning
- Land use and land cover change assessment
- Evidence-based urban policy design

## License

This repository distributes derived outputs based on publicly available NASA datasets. Original data are provided under NASA's open data policy:

- MODIS LST (MOD11A2): https://lpdaac.usgs.gov/products/mod11a2v061/
- MODIS Land Cover (MCD12Q1): https://lpdaac.usgs.gov/products/mcd12q1v061/

All outputs are shared for academic, research, and public-interest use. Users are responsible for citing original sources where appropriate.

## Citation

If using this dataset or its methodology in your work, please cite the original NASA MODIS products:

- Wan, Z. (2021). MOD11A2 MODIS/Terra Land Surface Temperature/Emissivity 8-Day L3 Global 1km SIN Grid V061. NASA EOSDIS Land Processes DAAC.
- Friedl, M. et al. (2021). MCD12Q1 MODIS/Terra+Aqua Land Cover Type Yearly L3 Global 500m SIN Grid V061. NASA EOSDIS Land Processes DAAC.

You may also cite this repository and acknowledge the Google Earth Engine processing framework used to generate the dataset.
