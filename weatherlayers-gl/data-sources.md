# Data Sources

WeatherLayers GL can be used either with custom self-hosted data or with WeatherLayers Cloud.

For integrating any custom data (NetCDF, GRIB), the data needs to be transformed by your backend server to a supported data type, data format and map projection.

### Data sources

* [WeatherLayers Cloud](../weatherlayers-cloud/) public data sources - NOAA (GFS, GFS Wave), Copernicus (CMEMS, CAMS)
* other public data sources - ECMWF, ICON, Copernicus (ERA5), ...
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

* PNG, WebP (Uint8)
  * scalar - R channel
    * nodata - `0` in A channel
  * vector - RG channels
    * nodata - `0` in A channel
* GeoTIFF (Uint8)
  * scalar - band 1
    * nodata - `0` in band 2
  * vector - bands 1 and 2
    * nodata - `0` in band 4
* GeoTIFF (Float32)
  * scalar - band 1
    * nodata - `NaN` in band 1
  * vector - bands 1 and 2
    * nodata - `NaN` in bands 1 and 2

### Supported projections

* equirectangular projection (EPSG:4326)

### Data transformation

Data transformation into a supported format can be done on your servers with GDAL.

See [gdal\_translate](https://gdal.org/programs/gdal_translate.html) for transformations between data types and data formats.

See [gdalwarp](https://gdal.org/programs/gdalwarp.html) for transformations between map projections.

See [gdal\_calc](https://gdal.org/en/stable/programs/gdal_calc.html) for calculations and [gdalbuildvrt](https://gdal.org/en/stable/programs/gdalbuildvrt.html) for merging files.

### Example – Temperature from GRIB to PNG

Scale from \[213.15, 325.15] to \[0, 255], disable GDAL unit normalization from K to C:

{% code overflow="wrap" %}
```sh
gdal_translate -ot Byte -scale 213.15 325.15 0 255 --config GRIB_NORMALIZE_UNITS=NO temperature.grib temperature.png
```
{% endcode %}

WeatherLayers GL configuration:

* `imageType: WeatherLayers.ImageType.SCALAR`
* `imageUnscale: [213.15, 325.15]`

### Example – Wind from GRIB to PNG

Calculate vector magnitude:

{% code overflow="wrap" %}
```sh
gdal_calc --calc='sqrt(A * A + B * B)' -A wind_u.grib --A_band=1 -B wind_v.grib --B_band=1 --outfile wind_magnitude.tif
```
{% endcode %}

Merge files:

{% code overflow="wrap" %}
```sh
gdalbuildvrt -separate wind.vrt wind_magnitude.tif wind_u.grib wind_v.grib
```
{% endcode %}

Scale from \[-128, 127] to \[0, 255]:

{% code overflow="wrap" %}
```sh
gdal_translate -ot Byte -scale -128 127 0 255 wind.vrt wind.png
```
{% endcode %}

WeatherLayers GL configuration:

* `imageType: WeatherLayers.ImageType.VECTOR`
* `imageUnscale: [-128, 127]`
