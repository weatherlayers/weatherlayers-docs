# Data properties

Data properties common for all layers.

#### `image`

Type: object `{ data: TypedArray, width: number, height: number }`, required

Data type can be either Uint8 (`Uint8Array`, `Uint8ClampedArray`) or Float32 (`Float32Array`).

Data length must be `width * height * bandsCount`.

Supported bands count is `1` (scalar) or `2` (vector). See `imageType`.

For multi-band data, the expected format is that the band values are interleaved by pixel. For example, for vector data with `u`, `v` values, the expected format is `[u1, v1, u2, v2, ...]`. This is known as [BIP file format](https://desktop.arcgis.com/en/arcmap/latest/manage-data/raster-and-images/bip-format-example.htm).

![Band interleaved by pixel (Source: ArcGIS Documentation)](../.gitbook/assets/band-interleaved-by-pixel.gif)

#### `image2`

Type: object `{ data: TypedArray, width: number, height: number }`, optional

The subsequent data image. Used if `imageWeight > 0`.

See `image` for details.

#### `imageInterpolate`

Type: boolean, optional

Default: `true`

If on, the data for a particular lng/lat location are computed from the four nearest available pixels using bilinear interpolation.

If off, the data for a particular lng/lat location are read from the nearest available pixel.

#### `imageWeight`

Type: number `0-1`, optional

Default: `0`

Interpolation weight between `image` and `image2`.

#### `imageType`

Type: enum `WeatherLayers.ImageType`, values: `SCALAR`, `VECTOR`, optional

Default: `SCALAR` (for layers that support both scalar and vector data), `VECTOR` (for layers that support vector data only)

#### `imageUnscale`

Type: tuple of lower and upper bound `[number, number]`, optional

The original data value bounds, used to unscale the data if the original data are scaled (quantized).

Supported if the data type is Uint8.

#### `bounds`

Type: bounding box of minX, minY, maxX, maxY `[number, number, number, number]`, required

The original data bounding box. Recommended value is `[-180, -90, 180, 90]` for a global image.
