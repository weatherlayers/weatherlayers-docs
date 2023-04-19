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
