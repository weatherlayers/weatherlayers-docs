# Data

Source data from GRIB2 and NetCDF formats are processed automatically in a periodical schedule into multiple formats suitable for visualization:

* PNG - 8-bit per each color channel
  * scalar variable - encoded into R channel
  * vector variable \(wind, waves, currents\) - u component encoded into R channel, v component encoded into G channel
* GeoTIFF - 32-bit float values

PNG is a great choice for visualization-only use cases, because of the best compression ratio. However, quantization into 8-bit means that there is an implicit precision error. For use cases where exact values are needed \(e.g. picking an exact value at user mouse position\), data formats supporting 32-bit float values are more suitable, such as GeoTIFF.

