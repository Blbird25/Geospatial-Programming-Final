# Geospatial Programming Final Project

This project models relative runoff risk using a weighted overlay approach
implemented in ArcGIS Pro, ModelBuilder, and Python (ArcPy).

## ModelBuilder Workflow
![ModelBuilder workflow](Model_Builder.png)

## Metadata / Data Availability
The data used for this final project originated from a variety of sources. The digital elevation model

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
