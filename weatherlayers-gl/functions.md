# Functions

#### `getClosestStartDatetime(datetimes: String[], datetime: String): String`

Gets the closest start (i.e. lower or equal) datetime for the given datetime from the given datetimes.

Use to find the correct start image to load, to be used as `image` input if `imageInterpolate` is enabled in [Data Properties](layers/data-properties.md).

#### `getClosestEndDatetime(datetimes: String[], datetime: String): String`

Gets the closest end (i.e. greater or equal) datetime for the given datetime from the given datetimes.

Use to find the correct end image to load, to be used as `image2` input if `imageInterpolate` is enabled in [Data Properties](layers/data-properties.md).

#### `getDatetimeWeight(startDatetime: String, endDatetime: String, datetime: String): number`

Gets the datetime weight between the given start and end datetime for the given datetime. The returned value is a number `0-1`.

Use as `imageWeight` input  if `imageInterpolate` is enabled in [Data Properties](layers/data-properties.md).

#### `loadTextureData(url: String): Promise<TextureData>`

Loads the url (PNG or GeoTIFF) to TextureData.

Use as `image` input in [Data Properties](layers/data-properties.md).

```typescript
type TextureDataArray = Uint8Array | Uint8ClampedArray | Float32Array;

interface TextureData {
  data: TextureDataArray;
  width: number;
  height: number;
}
```
