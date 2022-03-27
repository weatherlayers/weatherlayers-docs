# Data

Data properties are common for all layers in the standalone bundle.

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
    }),
  ],
});
```

### Example: GeoTIFF

```javascript
import * as GeoTIFF from 'geotiff';
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

async function loadGeotiff(url) {
  const geotiff = await GeoTIFF.fromUrl(url, { allowFullFile: true });
  const geotiffImage = await geotiff.getImage(0);

  const sourceData = await geotiffImage.readRasters({ interleave: true });
  const nodata = geotiffImage.getGDALNoData();
  const data = nodata != undefined ?
    new sourceData.constructor(Array.from(sourceData).map(value => value !== nodata ? value : NaN)) :
    sourceData;

  const width = geotiffImage.getWidth();
  const height = geotiffImage.getHeight();

  const textureData = { data, width, height };
  return textureData;
}

// load custom self-hosted data
const image = await loadGeoTiff(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
    }),
  ],
});
```

### Data properties

#### `image`

Type: object `{ data: TypedArray, width: number, height: number }`, required

Data type can be either Uint8 (`Uint8Array`, `Uint8ClampedArray`) or Float32 (`Float32Array`).

Data length must be `width * height * bandsCount`.

Supported bands count is `1` (scalar) or `2` (vector). See `imageType`.

If there are multiple data bands (e.g. vector u, v), the pixel values must be interleaved (e.g. \[u1, v1, u2, v2, ...]).

#### `image2`

Type: object `{ data: TypedArray, width: number, height: number }`, optional

The subsequent data image. Used if `imageWeight > 0`.

See `image` for details.

#### `imageInterpolate`

Type: boolean, optional

Default: `true`

If on, the data are interpolated using the nearest available pixels.

#### `imageWeight`

Type: number `0-1`, optional

Default: `0`

Interpolation weight between `image` and `image2`.

#### `imageType`

Type: enum `WeatherLayers.ImageType`, values: `SCALAR`, `VECTOR`, optional

Default: `SCALAR` (for layers that support both scalar and vector data), `VECTOR` (for layers that support vector data only)

#### `imageUnscale`

Type: tuple of lower and upper bound `[number, number]`, optional

The original data bounds, used to unscale the data if the original data are scaled (quantized).

Supported if the data type is Uint8.
