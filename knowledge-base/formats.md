# Data Formats

### Data Types

#### Float32

* original data
* suitable for use cases where exact values are needed, e.g. picking an exact value at user mouse position

#### Uint8

* implicit precision error because of quantization of the original data into 256 possible values
* suitable for visualization-only use cases, because of better compression ratio

### File Types

#### PNG

* data types - Uint8

#### GeoTIFF

* data types - Float32 or Uint8
