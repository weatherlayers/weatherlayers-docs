# Functions

#### `getClosestStartDatetime(datetimes: String[], datetime: String): String`

Gets the closest start (i.e. lower or equal) datetime for the given datetime from the given datetimes.

Use to find the correct start image to load, to be used in `image` property if `imageInterpolate` is enabled in [Data Properties](layers/data-properties.md).

#### `getClosestEndDatetime(datetimes: String[], datetime: String): String`

Gets the closest end (i.e. greater or equal) datetime for the given datetime from the given datetimes.

Use to find the correct end image to load, to be used in `image2` property if `imageInterpolate` is enabled in [Data Properties](layers/data-properties.md).

#### `getDatetimeWeight(startDatetime: String, endDatetime: String, datetime: String): number`

Gets the datetime weight between the given start and end datetime for the given datetime. The returned value is a number `0-1`.

Use in `imageWeight` property if `imageInterpolate` is enabled in [Data Properties](layers/data-properties.md).

#### `loadTextureData(url: String): Promise<TextureData>`

Loads the url (PNG or GeoTIFF) to TextureData.

Use in `image`/`image2` property in [Data Properties](layers/data-properties.md).

```typescript
type TextureDataArray = Uint8Array | Uint8ClampedArray | Float32Array;

interface TextureData {
  data: TextureDataArray;
  width: number;
  height: number;
}
```
