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

Valid ISO 8601 datetime range. Single datetime means an exact datetime instead of a range.

#### `ImageInterpolation`

```typescript
enum ImageInterpolation {
  NEAREST = 'NEAREST',
  LINEAR = 'LINEAR',
  CUBIC = 'CUBIC',
}
```

Image interpolation method.

* `NEAREST` - no interpolation, fastest
* `LINEAR` - medium interpolation quality
* `CUBIC` - best interpolation quality, slowest

#### `ImageType`

```typescript
enum ImageType {
  SCALAR = 'SCALAR',
  VECTOR = 'VECTOR',
}
```

Image type.

* `SCALAR` - contains a single variable
* `VECTOR` - contains two variables, `u` and `v` vector components

#### `ImageUnscale`

```typescript
type ImageUnscale = readonly [min: number, max: number] | null;
```

Value bounds to unscale image data to original data, or null if image contains original data already and no unscaling is needed.

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

#### `RasterPointProperties`

```typescript
interface RasterPointProperties {
  value: number;
  direction?: number;
}
```

Raster point properties for a particular position.
