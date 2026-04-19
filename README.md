# GeoCrash

A geospatial analysis project that validates the location data accuracy of traffic collision records by matching them against their nearest feature (intersection or address) in the Toronto street network.

There is also an Airflow ETL pipeline that applies the findings of this project. You can find it [here](https://github.com/imadsyed333/crashlog-geocode).

## Overview

Collision datasets often include textual street-name fields (e.g., `stname1`, `stname2`) alongside coordinate data. This project investigates whether those two representations agree — i.e., whether the coordinates of a collision actually place it at the intersection or address named in the record.

## Data

| File                     | Description                                                                                   |
| ------------------------ | --------------------------------------------------------------------------------------------- |
| `collisions.csv`         | Traffic collision records with street names, coordinates, ward, and contributing-factor flags |
| `intersections.csv`      | City intersection centreline features with geometry and intersection descriptions             |
| `addresses.csv`          | Toronto address features with geometry and other metadata                                     |

NOTE: You will have to obtain this data yourself through the [Toronto Open Data Portal](https://open.toronto.ca/).
## Project Structure

```
geocrash/
├── data/raw/
│   ├── collisions.csv
│   ├── intersections.csv
|   └── addresses.csv
├── notebooks/
│   ├── analysis.ipynb
|   ├── exploration.ipynb
|   └── pipeline.ipynb
└── README.md
```

## Requirements

- Python 3.x
- [geopandas](https://geopandas.org/)
- [pandas](https://pandas.pydata.org/)
- [shapely](https://shapely.readthedocs.io/)
- [rapidfuzz](https://github.com/rapidfuzz/RapidFuzz)
- [matplotlib](https://matplotlib.org/)
