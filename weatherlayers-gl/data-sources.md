# Data Sources

WeatherLayers GL can be used either with custom self-hosted data or with WeatherLayers Cloud.

For integrating any custom data (NetCDF, GRIB), the data needs to be transformed by your backend server to a supported data type, data format and map projection.

### Data sources

* [WeatherLayers Cloud](../weatherlayers-cloud/) public data sources - NOAA, Copernicus
* other public data sources - ECMWF, ICON, ...
* commercial data sources
* custom data sources - your own data from scientific research

### Supported data types

* Uint8
  * quantized data into 256 possible values
  * lower precision, higher compression ratio for lower file size
  * recommended for visualization purposes
  * original data bounds need to be provided to unscale the data into the original data, see [Data Properties imageUnscale](layers/data-properties.md#imageunscale)
* Float32
  * original data
  * better precision, lower compression ratio and larger file size
  * recommended for scientific purposes, or for use cases where exact values with no quantization errors are needed

### Supported data formats

* PNG Uint8
  * scalar - R channel
  * vector - RG channels
  * nodata - `0` in A channel
* GeoTIFF Uint8
  * scalar - band 1
  * vector - bands 1 and 2
  * nodata - `0` in band 4
* GeoTIFF Float32
  * scalar - band 1
  * vector - bands 1 and 2
  * nodata - `NaN` in band 1 (scalar) or in bands 1 and 2 (vector)

### Supported projections

* equirectangular projection (EPSG:4326)

### Data transformation

Data transformation into a supported format can be done on your servers with GDAL.

See [gdal\_translate](https://gdal.org/programs/gdal\_translate.html) for transformations between data types and data formats.

See [gdalwarp](https://gdal.org/programs/gdalwarp.html) for transformations between map projections.
