# Functions

### License Functions

#### `setLicense(license: License): void`

Sets the license to authorize library usage.

### Load Functions

#### `loadTextureData(url: string, cache?: Map<string, any> | false = DEFAULT_CACHE): Promise<`[`TextureData`](types.md#texturedata)`>`

Loads the url as texture data. The url should be PNG, WebP or GeoTIFF image.

GeoTIFF requires [geotiff.js ](https://github.com/geotiffjs/geotiff.js/)as a peer dependency.

The response is cached to the given cache, or to the default global cache, or caching can be disabled by `false`.

Use in `image`/`image2` property.

#### `loadJson(url: string, cache?: Map<string, any> | false = DEFAULT_CACHE): Promise<string>`

Loads the url as JSON. The response should be a JSON file.

The response is cached to the given cache, or to the default global cache, or caching can be disabled by `false`.

### Datetime Functions

#### `getClosestStartDatetime(datetimes:` [`DatetimeISOString`](types.md#datetimeisostring)`[], datetime:` [`DatetimeISOString`](types.md#datetimeisostring)`):` [`DatetimeISOString`](types.md#datetimeisostring) `| undefined`

Gets the closest start datetime (i.e. lower or equal) for the given datetime from the given datetimes.

Use to find the correct start image to load, to be used in `image` property.

#### `getClosestEndDatetime(datetimes:` [`DatetimeISOString`](types.md#datetimeisostring)`[], datetime:` [`DatetimeISOString`](types.md#datetimeisostring)`):` [`DatetimeISOString`](types.md#datetimeisostring) `| undefined`

Gets the closest end datetime (i.e. greater or equal) for the given datetime from the given datetimes.

Use to find the correct end image to load, to be used in `image2` property. Applicable only if `datetimeInterpolate` is enabled.

#### `getDatetimeWeight(startDatetime:` [`DatetimeISOString`](types.md#datetimeisostring)`, endDatetime:` [`DatetimeISOString`](types.md#datetimeisostring)`, datetime:` [`DatetimeISOString`](types.md#datetimeisostring)`): number`

Gets the datetime weight between the given start and end datetime for the given datetime. The returned value is a number `0-1`.

Use in `imageWeight` property. Applicable only if `datetimeInterpolate` is enabled.

#### `offsetDatetime(datetime:` [`DatetimeISOString`](types.md#datetimeisostring)`, hour: number):` [`DatetimeISOString`](types.md#datetimeisostring)

Adds hours to the given datetime.

#### `offsetDatetimeRange(datetime:` [`DatetimeISOString`](types.md#datetimeisostring)`, start: number, end: number):` [`DatetimeISOStringRange`](types.md#datetimeisostringrange)

Adds start hour and end hours to the given datetime. The returned value is a datetime range.

### Raster functions

#### `getRasterPoints(imageProperties:` [`ImageProperties`](types.md#imageinterpolation)`, bounds: GeoJSON.BBox, positions: GeoJSON.Position[]): GeoJSON.FeatureCollection<GeoJSON.Point,` [`RasterPointProperties`](types.md#rasterpointproperties)`>`

Gets raster points for the given positions.

