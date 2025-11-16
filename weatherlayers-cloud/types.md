# Types

### Load Types

#### `ClientConfig`

```typescript
interface ClientConfig {
  url?: string;
  accessToken?: string;
  dataFormat?: string;
  unitSystem?: UnitSystem;
  attributionLinkClass?: string;
  datetimeStep?: number;
  datetimeInterpolate?: boolean;
}
```

#### `LoadConfig`

```typescript
export interface LoadConfig extends ClientConfig {
  tile?: { z: number; x: number; y: number };
  signal?: AbortSignal;
}
```

Data request load config.

* `tile` - tile XYZ coordinates for loading tiled data
* `signal` - abort signal for cancelling the request

#### `Dataset`

```typescript
interface Dataset {
  title: string;
  unitFormat: UnitFormat;
  attribution: string;
  bounds: [number, number, number, number];
  datetimeRange: OpenDatetimeISOStringRange;
  datetimes: DatetimeISOString[]; // deprecated, use `loadDatasetSlice` instead
  palette: Palette;
}
```

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
  datetime: DatetimeISOString;
  referenceDatetime: DatetimeISOString;
  horizon: DurationISOString;
  image: TextureData;
  datetime2: DatetimeISOString | null;
  referenceDatetime2: DatetimeISOString | null;
  horizon2: DurationISOString | null;
  image2: TextureData | null;
  imageWeight: number;
  imageType: ImageType;
  imageUnscale: [number, number] | null;
  bounds: [number, number, number, number];
}
```

Dataset data.

* `datetime` - closest start forecast datetime <= requested datetime
* `referenceDatetime` - reference datetime of `datetime`, i.e. datetime of model run
* `horizon` - duration between `referenceDatetime` and `datetime`, e.g. `PT6H` for a 6-hour forecast
* `image` - image at `datetime`
* `datetime2`\* - closest end forecast datetime >= requested datetime
* `referenceDatetime2`\* - reference datetime of `datetime2`, i.e. datetime of model run
* `horizon2`\* - duration between `referenceDatetime2` and `datetime2`, e.g. `PT6H` for a 6-hour forecast
* `image2`\* - image at `datetime2`
* `imageWeight`\* - interpolation weight between `image` and `image2`
* `imageType` - image type, scalar or vector
* `imageUnscale` - original data value bounds, used to unscale the data if the original data are scaled (quantized)
* `bounds` - original data bounding box

\* applicable only if `datetimeInterpolate` is enabled

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
  METRIC_KILOMETERS = 'METRIC_KILOMETERS',
  IMPERIAL = 'IMPERIAL',
  NAUTICAL = 'NAUTICAL',
}
```

Unit system for unit format definition.

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

### Datetime Types

#### `DatetimeISOString`

```typescript
type DatetimeISOString = string;
```

Valid ISO 8601 datetime.

#### `DatetimeISOStringRange`

```typescript
type DatetimeISOStringRange = [start: DatetimeISOString, end: DatetimeISOString];
```

Valid ISO 8601 datetime range.

#### `OpenDatetimeISOStringRange`

```typescript
type OpenDatetimeISOStringRange = [start: DatetimeISOString | null, end: DatetimeISOString | null];
```

Valid ISO 8601 datetime range. Null start/end represent an open end.

#### `DurationISOString`

```typescript
type DurationISOString = string;
```

Valid ISO 8601 duration.
