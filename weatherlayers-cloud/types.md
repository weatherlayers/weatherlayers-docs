# Types

### Load Types

#### `Dataset`

```typescript
interface Dataset {
  title: string;
  unitFormat: UnitFormat;
  attribution: string;
  datetimeRange: DatetimeISOStringRange;
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

#### `TextureData`

```typescript
interface TextureData {
  data: Uint8Array | Uint8ClampedArray | Float32Array;
  width: number;
  height: number;
}
```

Texture data to be used as input to raster rendering layers.

#### `UnitSystem`

```typescript
enum UnitSystem {
  METRIC = 'METRIC',
  IMPERIAL = 'IMPERIAL',
  NAUTICAL = 'NAUTICAL',
}
```

Unit system for unit format definition.

#### `UnitFormat`

```typescript
interface UnitFormat {
  system: UnitSystem;
  unit: string;
  scale?: number;
  offset?: number;
  decimals?: number;
}
```

Format definition to be used for formatting raw values with units.

### Datetime Types

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
