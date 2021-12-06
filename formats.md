# Formats

| Format            | Data type | File type | Projection      |
| ----------------- | --------- | --------- | --------------- |
| tif               | Float32   | GeoTIFF   | Equirectangular |
| cog.tif           | Float32   | COG       | Equirectangular |
| byte.tif          | Byte      | GeoTIFF   | Equirectangular |
| byte.cog.tif      | Byte      | COG       | Equirectangular |
| byte.png          | Byte      | PNG       | Equirectangular |
| mercator.byte.png | Byte      | PNG       | Mercator        |

## Data types

### Float32

* original data
* suitable for use cases where exact values are needed, e.g. picking an exact value at user mouse position

### Byte

* Uint8 (0-255)
* implicit precision error because of quantization of the original data into 256 possible values
* suitable for visualization-only use cases, because of better compression ratio

## File types

### PNG

* data types - Byte

### GeoTIFF

* data types - Float32 or Byte

