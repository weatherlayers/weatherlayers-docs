# Functions

### License Functions

#### `setLicense(license: License): void`

Sets the license to authorize library usage.

### Load Functions

#### `loadTextureData(url: String, cache?: Map<string, any> | false = DEFAULT_CACHE): Promise<TextureData>`

Loads the url as texture data. The response should be a PNG or GeoTIFF image.

GeoTIFF requires [geotiff.js ](https://github.com/geotiffjs/geotiff.js/)as a peer dependency.

The response is cached to the given cache, or to the default global cache, or caching can be disabled by `false`.

Use in `image`/`image2` property.

#### `loadJson(url: String, cache?: Map<string, any> | false = DEFAULT_CACHE): Promise<string>`

Loads the url as JSON. The response should be a JSON file.

The response is cached to the given cache, or to the default global cache, or caching can be disabled by `false`.

#### `loadText(url: String, cache?: Map<string, any> | false = DEFAULT_CACHE): Promise<string>`

Loads the url as text. The response should be a plain text file.

The response is cached to the given cache, or to the default global cache, or caching can be disabled by `false`.

### Datetime Functions

#### `getClosestStartDatetime(datetimes: DatetimeISOString[], datetime: DatetimeISOString): DatetimeISOString | undefined`

Gets the closest start datetime (i.e. lower or equal) for the given datetime from the given datetimes.

Use to find the correct start image to load, to be used in `image` property.

#### `getClosestEndDatetime(datetimes: DatetimeISOString[], datetime: DatetimeISOString): DatetimeISOString | undefined`

Gets the closest end datetime (i.e. greater or equal) for the given datetime from the given datetimes.

Use to find the correct end image to load, to be used in `image2` property. Applicable only if `datetimeInterpolate` is enabled.

#### `getDatetimeWeight(startDatetime: DatetimeISOString, endDatetime: DatetimeISOString, datetime: DatetimeISOString): number`

Gets the datetime weight between the given start and end datetime for the given datetime. The returned value is a number `0-1`.

Use in `imageWeight` property. Applicable only if `datetimeInterpolate` is enabled.

#### `addHoursToDatetime(datetime: DatetimeISOString, hour: number): DatetimeISOString`

Adds hours to the given datetime.

### Raster functions

#### `getRasterPoints(image: TextureData, image2: TextureData | null, imageSmoothing: number, imageInterpolation: ImageInterpolation, imageWeight: number, imageType: ImageType, imageUnscale: ImageUnscale, bounds: GeoJSON.BBox, positions: GeoJSON.Position[]): GeoJSON.FeatureCollection<GeoJSON.Point, RasterPointProperties>`

Gets raster points for the given positions.

