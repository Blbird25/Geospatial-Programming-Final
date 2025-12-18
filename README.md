# Geospatial Programming Final Project

This project models relative runoff risk using a weighted overlay approach
implemented in ArcGIS Pro, ModelBuilder, and Python (ArcPy).

## ModelBuilder Workflow
![ModelBuilder workflow](Model_Builder.png)

## Metadata / Data Availability
The data used for this final project originated from a variety of sources. The digital elevation model tiles were pulled from the USGS National Map Viewer. Three, 1/3 Arc Second tiles each with spatial resolution of 9.259259m were used in the projection NAD83. DEM data was collected as recent as November 20, 2021. Fractional impervious surface data was collected from the Multi-Resolution Land Characteristics Consortium. These data were downloaded for 2021, and used the projection AEA_WGS84 with a spatial resolution of 30m. A polygon layer of hydrologic group soils was downloaded via the ArcGIS Online portal and originated from the USDA Web Soil Survey. The polygon feature class has a projected coorinate system of NAD 1983 HARN StatePlane Arizona Central FIPS 0202 (Intl Feet). Watershed data was added from the USGS National Map Services page, filtered to HUC-12 subwatersheds. Data has a projection of NAD83. For Tucson ward boundaries, data was sourced from the City of Tucson Open Data, filtered to boundaries and then ward boundaries. The layer uses the projection WGS 1984 Web Mercator (auxiliary sphere).

## Metadata (Cont.)
After all layers were input to this project, they were set to the projection NAD83 UTM Zone 12N for Arizona. All raster layers were clipped to the extent of the smallest raster layer, the soils layer, for consistent grid snapping. Spatial resolution for raster layers were matched to the DEM (9.259259m in the x and y direction).

## Overview
The model integrates:
- Slope derived from a DEM
- Impervious surface cover
- Soil runoff risk

Each layer is reclassified and combined using a weighted overlay to produce
a relative runoff risk index (1 = low, 5 = high).

## Software
- ArcGIS Pro
- Spatial Analyst
- ArcPy (Python)

## Running the Code
Run the script inside an ArcGIS Pro Notebook:
```python
exec(open("runoff_model.py").read())
