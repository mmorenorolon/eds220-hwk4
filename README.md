# A Geospatial Assessment of Burn Severity and Social Vulnerability in the 2025 LA Wildfires
*This project was completed as part of EDS 220: Working With Environmental Datasets in the Master of Environmental Data Science (MEDS) program at UC Santa Barbara.*

<img width="764" height="428" alt="image" src="https://github.com/user-attachments/assets/07e86dc8-1a5e-4ceb-8050-b0de84cb5402" />

## About

This repository documents the workflow for creating a false-color Landsat image to visualize burn scars from the Palisades and Eaton fires in Southern California. Using shortwave infrared (SWIR), near-infrared (NIR), and red bands from Landsat 8, the analysis highlights burned areas by leveraging their distinct spectral signatures and comparing them against official CAL FIRE fire-perimeter polygons.

This project also incorporates an Environmental Justice (EJ) assessment using existing EJ Index data. Specifically, we identify which census tracts intersect the Eaton and Palisades fire perimeters and examine the percentage of people with disabilities reported for each census tract. Together, this analysis contextualizes wildfire impacts alongside social vulnerability indicators to offer insights into which communities may have faced heightened risks during evacuation, emergency response, and recovery.

## Repository Structure

<details> <summary><strong>Click to expand the repository tree</strong></summary>
eaton-palisades-eji-false-imagery
│   .gitignore
│   hwk4-task2-false-color-MORENOROLON.ipynb     # Landsat false-color processing workflow
│   index.html                                   # HTML rendering of main notebook
│   index.ipynb                                  # Main analysis notebook
│   README.md
│   week8-social-dimensions-eaton-palisades.ipynb # EJ/disability intersection analysis
│
├───data
│   │   landsat8-2025-02-23-palisades-eaton.nc   # Landsat 8 surface reflectance dataset
│   │
│   ├───Eaton_Perimeter_20250121                 # Eaton Fire CAL FIRE perimeter shapefile
│   │
│   ├───EJI_2024_California_GDB                  # 2024 California EJI geodatabase
│   │       └───EJI_2024_California.gdb
│   │
│   └───Palisades_Perimeter_20250121             # Palisades Fire CAL FIRE perimeter shapefile
<details>

## Data Sources

### Environmental Justice Index (EJI) Data:

The Environmental Justice Index (EJI), developed by the [Agency for Toxic Substances and Disease Registry (ATSDR)](https://www.atsdr.cdc.gov/place-health/php/eji/eji-data-download.html), provides metrics to identify communities that may experience higher cumulative impacts from environmental burdens and social vulnerabilities. For this project, the 2024 California EJI dataset was downloaded and used to obtain census-tract–level indicators relevant to vulnerability assessments. This dataset is stored in the `data/EJI_2024_California_GDB/` directory and is loaded directly in the analysis notebooks. This analysis focuses on the variable `E_DISABL`, which represents the percentage of people with a disability in each census tract. This variable is used to highlight communities that may face additional challenges during wildfire events, such as evacuation, access to emergency services, and recovery support. By identifying which tracts intersect the Eaton and Palisades fire perimeters, the project situates burn-area mapping within the broader context of social vulnerability and community resilience.
 

Date Accessed: 11/19/2025

### Fire Perimeter Data:

The Palisades and Eaton Dissolved Fire Perimeters dataset, published on January 21, 2025 by the County of Los Angeles, provides dissolved boundary polygons for the Eaton and Palisades Fires. These shapefiles are included in the `data/Eaton_Perimeter_20250121/` and `data/Palisades_Perimeter_20250121/` folders of the repository. Derived from the NIFC FIRIS fire service, which originally contained daily perimeter snapshots, the boundaries were merged to create a single burn perimeter for each fire. One Eaton record (mission 2025-CALAC-009087) was excluded because buffered “destroyed” points did not reliably represent burned areas. The dataset is hosted on [ArcGIS Hub](https://hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about) and includes geospatial layers for both fire perimeters, which supports wildfire impact analysis, mapping and environmental monitoring.

Date Accessed: 11/19/2025

### Landsat Data:

The NetCDF dataset `landsat8-2025-02-23-palisades-eaton.nc` contains atmospherically corrected surface reflectance data from the Landsat 8 satellite, published on February 23, 2025 through the [Microsoft Planetary Computer](https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2). It includes key spectral bands (red, green, blue, near-infrared (NIR), and shortwave infrared (SWIR)) clipped to the perimeters of the Eaton and Palisades Fires in Los Angeles County. The dataset stores geospatial metadata in the `spatial_ref` variable. With a spatial resolution of 30 meters, this dataset supports the creation of true color and false color composites to assess vegetation health, burn severity and the extent of fire scars. The Landsat NetCDF file is included in `data/landsat8-2025-02-23-palisades-eaton.nc` and is accessed by the notebooks via `xarray`.

Date Accessed: 11/19/2025

## References:

Centers for Disease Control and Prevention and Agency for Toxic Substances Disease Registry. (2024). *Environmental Justice Index [Dataset]*. https://atsdr.cdc.gov/place-health/php/eji/eji-data-download.html

County of Los Angeles. (2025). *Palisades and Eaton dissolved fire perimeters (Version 1.0) [Dataset]*. ArcGIS Hub. https://hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about

Galaz García, C. (2025). *Final project*. EDS - 220 Working with Environmental Datasets. Retrieved from https://meds-eds-220.github.io/MEDS-eds-220-course/assignments/final-project.html

Microsoft. (2025). *landsat8-2025-02-23-palisades-eaton.nc (Version 1.0) [Dataset]*. Microsoft Planetary Computer. https://planetarycomputer.microsoft.com