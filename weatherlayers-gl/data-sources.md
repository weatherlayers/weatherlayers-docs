# Data Sources

WeatherLayers GL can be used either with custom self-hosted data or with WeatherLayers Cloud.

For integrating any custom data, the data needs to be transformed by your backend server to a supported data type, data format and map projection.

### Data sources

* [WeatherLayers Cloud](../weatherlayers-cloud/) public data sources - NOAA, Copernicus
* other public data sources - ECMWF, ICON, ...
* commercial data sources
* custom data sources - your own data from scientific research

### Supported data types

* Uint8 - lower quantized precision, higher compression ratio for lower file size, recommended for visualization purposes
  * `imageUnscale` ...
* Float32 - better precision, lower compression ratio and larger file size, recommended for scientific purposes

### Supported data formats

* PNG - Uint8
  * scalar - R channel
  * vector - u/v in R/G channels
* GeoTIFF - Uint8, Float32

### Supported projections

* equirectangular projection (EPSG:4326)

### Data transformation

Data transformation into a supported format can be done on your servers with GDAL.

See [gdal\_translate](https://gdal.org/programs/gdal\_translate.html) for transformations between data types and data formats.

See [gdalwarp](https://gdal.org/programs/gdalwarp.html) for transformations between map projections.
