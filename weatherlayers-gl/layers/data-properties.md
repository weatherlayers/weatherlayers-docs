# Data Properties

Data properties common for all layers.

#### `image`

Type: `TextureData = { data: TypedArray, width: number, height: number }`, required

Data type can be either Uint8 (`Uint8Array`, `Uint8ClampedArray`) or Float32 (`Float32Array`).

Data length must be `width * height * bandsCount`.

Supported bands count is `1`, `2` or `4`. See `imageType` and [Data Sources](../data-sources.md).

For multi-band data, the expected format is that the band values are interleaved by pixel. For example, for vector data with `u`, `v` values, the expected format is `[u1, v1, u2, v2, ...]`. This is also known as [BIP format](https://desktop.arcgis.com/en/arcmap/latest/manage-data/raster-and-images/bip-format-example.htm).

This is the format expected by the library, after decoding the image from the original file format. Decode the original file format either with [`loadTextureData`](../functions.md#loadtexturedata-url-string-cache-map-less-than-string-any-greater-than-or-false-default\_cache-promis) (PNG, GeoTIFF) or yourself.

![Band interleaved by pixel (Source: ArcGIS Documentation)](../../.gitbook/assets/band-interleaved-by-pixel.gif)

#### `image2`

Type: `TextureData = { data: TypedArray, width: number, height: number }`, optional

The subsequent data image. Used if `imageWeight > 0`.

See `image` for details.

#### `imageSmoothing`

Type: number, optional

Default: `0` (no smoothing)

Smoothing applied to the data. Increasing the smoothing is useful in case of rendering artifacts with low resolution data or if high detail is undesired. Maximal smoothing is unlimited.

#### `imageInterpolation`

Type: enum `WeatherLayers.ImageInterpolation`, values: `NEAREST`, `LINEAR`, `CUBIC`, optional

Default: `CUBIC`

`NEAREST` disables any interpolation, renders the data for a particular lng/lat location from the nearest available pixel. Raster layer is pixelizated.

`LINEAR` interpolates the data for a particular lng/lat location from four pixels using a linear interpolation. Provides a balance between smoothness and performance.

`CUBIC` interpolates the data for a particular lng/lat location from sixteen pixels using a cubic interpolation. Provides the best smoothness. Required for Contour layer with byte data format.

#### `imageWeight`

Type: number `0-1`, optional

Default: `0`

Interpolation weight between `image` and `image2`.

#### `imageType`

Type: enum `WeatherLayers.ImageType`, values: `SCALAR`, `VECTOR`, optional

Default: `SCALAR` (for layers that support both scalar and vector data), `VECTOR` (for layers that support vector data only)

#### `imageUnscale`

Type: tuple of lower and upper bound `[number, number]`, optional

Default: `null` (no unscaling)

The original data value bounds, used to unscale the data if the original data are scaled (quantized).

Supported if the data type is Uint8.

#### `bounds`

Type: bounding box of minX, minY, maxX, maxY `[number, number, number, number]`, required

The original data bounding box. Recommended value is `[-180, -90, 180, 90]` for a global image.

#### `minZoom`

Type: number `0-20`, optional

Default: `null` (no minimal limit)

Minimal zoom limit to render the layer.

#### `maxZoom`

Type: number `0-20`, optional

Default: `10` (ContourLayer), `15` (ParticleLayer), `null` (other layers, no maximal limit)

Maximal zoom limit to render the layer.

It's possible to override a lower default value to a higher value, but rendering artifacts may occur in high zoom levels due to a low precision.
