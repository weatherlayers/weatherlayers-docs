# Types

#### `DatetimeISOString`

Type: string

Valid ISO 86001 datetime.

#### `TextureData`

Type: `{ data: GeoTIFF.TypedArray | Uint8ClampedArray, width: number, height: number }`

Texture data to be used as input to raster rendering layers.

#### `UnitFormat`

Type: `{ unit: string; scale?: number; offset?: number; decimals?: number }`

Format definition to be used for formatting raw values with units.
