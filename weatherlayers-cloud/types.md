# Types

#### `DatetimeISOString`

```typescript
type DatetimeISOString = string;
```

Valid ISO 8601 datetime.

#### `DatetimeISOStringRange`

```typescript
type DatetimeISOStringRange = [DatetimeISOString, DatetimeISOString] | DatetimeISOString;ty
```

Valid ISO 8601 datetime range.

A single datetime means an exact datetime instead of a range.

#### `TextureData`

```typescript
interface TextureData {
  data: GeoTIFF.TypedArray | Uint8ClampedArray;
  width: number;
  height: number;
}
```

Texture data to be used as input to raster rendering layers.

#### `UnitFormat`

```typescript
interface UnitFormat {
  unit: string;
  scale?: number;
  offset?: number;
  decimals?: number;
}
```

Format definition to be used for formatting raw values with units.

#### `Dataset`

```typescript
interface Dataset {
  title: string;
  unitFormat: UnitFormat;
  attribution: string;
  datetimes: DatetimeISOString[]; // deprecated, use `loadDatasetSlice` instead
  palette: Palette;
}
```

Dataset metadata.

#### `DatasetSlice`

```typescript
interface DatasetSlice {
  datetimes: DatetimeISOString[];
}
```

Dataset slice with available datetimes in the requested datetime range.

#### `DatasetData`

```typescript
interface DatasetData {
  image: TextureData;
  image2: TextureData | null; // applicable if `datetimeInterpolate` is enabled
  imageWeight: number; // applicable if `datetimeInterpolate` is enabled
  imageType: ImageType;
  imageUnscale: [number, number] | null; // applicable if original data was scaled to fit image data format and needs to be unscaled back
  bounds: [number, number, number, number];
}
```

Dataset data.

* `image` - the closest available datetime <= the given datetime
* `image2` - the closest available datetime >= the given datetime
* `imageWeight` - datetime interpolation weight between `image` and `image2`
