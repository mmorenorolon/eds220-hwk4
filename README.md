# Visualizing Wildfire Scars: False Color Analysis of the Eaton and Palisades Fires (2025)
This project was completed as part of EDS 220: Working With Environmental Datasets in the Master of Environmental Data Science (MEDS) program at UC Santa Barbara.

<img width="764" height="428" alt="image" src="https://github.com/user-attachments/assets/07e86dc8-1a5e-4ceb-8050-b0de84cb5402" />

## About

This repository documents the process of creating a false-color Landsat image to visualize burn scars from the Palisades and Eaton fires in Southern California. Using shortwave infrared (SWIR), near-infrared (NIR), and red bands from Landsat 8, the project highlights burned areas by exploiting their unique spectral signatures and overlays official CAL FIRE fire-perimeter polygons for comparison.

## Repository Structure
```
C:.
│   .gitignore
│   hwk4-task2-false-color-MORENOROLON.ipynb
│   README.md
```

## Data

### Landsat Data:
The NetCDF dataset `landsat8-2025-02-23-palisades-eaton.nc` contains atmospherically corrected surface reflectance data from the Landsat 8 satellite, published on February 23, 2025 through the [Microsoft Planetary Computer](https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2). It includes key spectral bands (red, green, blue, near-infrared, and shortwave infrared) clipped to the perimeters of the Eaton and Palisades Fires in Los Angeles County. The dataset stores geospatial metadata in the `spatial_ref` variable. With a spatial resolution of 30 meters, this dataset supports the creation of true color and false color composites to assess vegetation health, burn severity and the extent of fire scars. 

Date Accessed: 11/19/2025

### Fire Perimeter Data:
The Palisades and Eaton Dissolved Fire Perimeters (2025) dataset, published on January 21, 2025 by the County of Los Angeles, provides dissolved boundary polygons for the Eaton and Palisades Fires. Derived from the NIFC FIRIS fire service, which originally contained daily perimeter snapshots, the boundaries were merged to create a single burn perimeter for each fire. One Eaton record (mission 2025-CALAC-009087) was excluded because buffered “destroyed” points did not reliably represent burned areas. The dataset is hosted on [ArcGIS Hub](https://hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about) and includes geospatial layers for both fire perimeters, which supports wildfire impact analysis, mapping and environmental monitoring.

Date Accessed: 11/19/2025

## References:
Microsoft. (2025). *landsat8-2025-02-23-palisades-eaton.nc (Version 1.0) [Dataset]*. Microsoft Planetary Computer. https://planetarycomputer.microsoft.com

County of Los Angeles. (2025). *Palisades and Eaton dissolved fire perimeters (Version 1.0) [Dataset]*. ArcGIS Hub. https://hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about
