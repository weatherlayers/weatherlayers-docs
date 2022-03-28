# Particle layer

Vector variable rendered as animated particle simulation layer

### Example

```javascript
import { Deck, COORDINATE_SYSTEM } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ParticleLayer({
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
      _imageCoordinateSystem: COORDINATE_SYSTEM.LNGLAT,
      extensions: [new ClipExtension()],
      clipBounds: [-181, -85.051129, 181, 85.051129],
    }),
  ],
});
```

### Data properties

[Data properties](../data.md#data-properties) are common for all layers in the standalone bundle.

#### `_imageCoordinateSystem`

Type: enum `COORDINATE_SYSTEM`, values: `CARTESIAN`, `LNGLAT`, optional

Default: `CARTESIAN`

Use `COORDINATE_SYSTEM.LNGLAT` for an image in an equirectangular projection. See [BitmapLayer.\_imageCoordinateSystem](https://deck.gl/docs/api-reference/layers/bitmap-layer#\_imagecoordinatesystem).

#### `extensions`

Type: array of extensions

Use `[new ClipExtension()]` for a global image in an equirectangular projection on a [WebMercatorViewport](https://deck.gl/docs/api-reference/core/web-mercator-viewport), to clip the areas of the image beyond a valid Mercator bounding box. See [ClipExtension](https://deck.gl/docs/api-reference/extensions/clip-extension).

#### `clipBounds`

Type: bounding box of minX, minY, maxX, maxY `[number, number, number, number]`, required for `ClipExtension`

Use `[-181, -85.051129, 181, 85.051129]` for a global image in an equirectangular projection on a [WebMercatorViewport](https://deck.gl/docs/api-reference/core/web-mercator-viewport), to clip the areas of the image beyond a valid Mercator bounding box. There is `181` instead of `180` to avoid a pixel gap at the antimeridian. See [ClipExtension.clipBounds](https://deck.gl/docs/api-reference/extensions/clip-extension#clipbounds).

### Style properties

#### numParticles

Type: number, optional

Default: `5000`

Number of the particles. The greater number of particles, the denser particle trails.

#### `maxAge`

Type: number, optional

Default: `100`

Max age of the particles in frames. The greater max age, the longer particle trails.

#### `speedFactor`

Type: number `0-1`, optional

Default: `1`

Speed factor of the particles. The greater speed factor, the longer particle trails.

#### `width`

Type: `number`, optional

Default: `1`

Width of the line. See [LineLayer getWidth](https://deck.gl/docs/api-reference/layers/line-layer#getwidth).

#### `color`

Type: color `[number, number, number, number?]`, optional

Default: `[255, 255, 255, 51]`

Color of the line. See [LineLayer getColor](https://deck.gl/docs/api-reference/layers/line-layer#getcolor).

#### `opacity`

Type: number, optional

Default: `1`

Opacity of the layer. See [Layer opacity](https://deck.gl/docs/api-reference/core/layer#opacity).
