# Functions

### Library Functions

#### `setLibrary<T>(name: string, library: T): void`

Sets an optional dependency.

By default, optional dependencies are loaded with a dynamic import. If the dynamic import is not supported by your environment, use this function to set the optional dependency explicitly.

### Load Functions

#### `loadTextureData(url: string, options?: CachedLoadOptions<TextureData>): Promise<`[`TextureData`](types.md#texturedata)`>`

Loads the url as texture data. The url should be PNG, WebP or GeoTIFF image.

GeoTIFF requires [geotiff.js ](https://github.com/geotiffjs/geotiff.js/)as an optional dependency if loading GeoTIFF images.

Use in `image`/`image2` property.

#### `loadJson(url: string, options?: CachedLoadOptions<any>): Promise<any>`

Loads the url as JSON. The response should be a JSON file.

#### `CachedLoadOptions`

```typescript
interface CachedLoadOptions<T> {
  headers?: Record<string, string>;
  cache?: Map<string, T | Promise<T>> | false;
}
```

Custom HTTP headers can be provided by `headers`.

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

#### `offsetDatetimeRange(datetime:` [`DatetimeISOString`](types.md#datetimeisostring)`, startHour: number, endHour: number):` [`DatetimeISOStringRange`](types.md#datetimeisostringrange)

Adds start hour and end hour to the given datetime. The returned value is a datetime range.

### Raster functions

#### `getRasterPoints(imageProperties:` [`ImageProperties`](types.md#imageproperties)`, bounds: GeoJSON.BBox, positions: GeoJSON.Position[]): GeoJSON.FeatureCollection<GeoJSON.Point,` [`RasterPointProperties`](types.md#rasterpointproperties)`>`

Gets raster points for the given positions.

