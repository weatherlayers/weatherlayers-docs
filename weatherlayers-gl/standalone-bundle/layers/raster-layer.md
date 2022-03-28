# Raster layer

Variable rendered as a color overlay

### Example

```javascript
import { Deck, COORDINATE_SYSTEM } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
      _imageCoordinateSystem: COORDINATE_SYSTEM.LNGLAT,
      extensions: [new ClipExtension()],
      clipBounds: [-181, -85.051129, 181, 85.051129],
      
      // style properties
      colormapBreaks: [
        [0, [0, 0, 0]],
        [20, [255, 255, 255]],
      ],
    }),
  ],
});
```

### Example: Picking

```javascript
import { Deck, COORDINATE_SYSTEM } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
      _imageCoordinateSystem: COORDINATE_SYSTEM.LNGLAT,
      extensions: [new ClipExtension()],
      clipBounds: [-181, -85.051129, 181, 85.051129],
      
      // style properties
      colormapBreaks: [
        [0, [0, 0, 0]],
        [20, [255, 255, 255]],
      ],

      pickable: true,
    }),
  ],
  onHover: event => console.log(event.raster),
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

Recommended value is `[-181, -85.051129, 181, 85.051129]` for a global image in an equirectangular projection on a [WebMercatorViewport](https://deck.gl/docs/api-reference/core/web-mercator-viewport), to clip the areas of the image beyond a valid Mercator bounding box. There is `181` instead of `180` to avoid a pixel gap at the antimeridian. See [ClipExtension.clipBounds](https://deck.gl/docs/api-reference/extensions/clip-extension#clipbounds).

### Style properties

#### `colormapBreaks`

Type: array of tuples of value and color `[number, [number, number, number, number?]][]`, required

Colormap breaks used to interpolate the colormap between values and colors.

#### `opacity`

Type: number, optional

Default: `1`

Opacity of the layer. See [Layer opacity](https://deck.gl/docs/api-reference/core/layer#opacity).

### Picking info

If `pickable: true`, the picking info passed to callbacks (`onHover`, `onClick`, etc.) provides information on which pixel was picked. It contains an additional `raster` field.

See [BitmapLayer Pixel Picking](https://deck.gl/docs/api-reference/layers/bitmap-layer#pixel-picking).

#### `value`

Type: number, required

Value at the pixel.

#### `direction`

Type: number, optional

Direction at the pixel. Supported for vector data.
