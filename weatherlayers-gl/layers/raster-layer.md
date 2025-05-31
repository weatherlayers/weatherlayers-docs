# Raster Layer

Variable rendered as a color overlay

### Example

![Raster Layer](../../.gitbook/assets/raster-layer.png)

```javascript
import { Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from 'weatherlayers-gl';

// load data
const image = await WeatherLayers.loadTextureData(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      id: 'raster',
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
      // style properties
      palette: [
        [0, [255, 255, 255]],
        [5, [127, 255, 255]],
        [10, [127, 255, 127]],
        [15, [255, 255, 127]],
        [20, [255, 127, 127]],
        [25, [127, 0, 0]],
      ],
      extensions: [new ClipExtension()],
      clipBounds: [-181, -85.051129, 181, 85.051129],
    }),
  ],
});
```

### Example: Picking

```javascript
import { Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from 'weatherlayers-gl';

// load data
const image = await WeatherLayers.loadTextureDataCached(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
      extensions: [new ClipExtension()],
      clipBounds: [-181, -85.051129, 181, 85.051129],
      // style properties
      palette: [
        [0, [255, 255, 255],
        [5, [127, 255, 255],
        [10, [127, 255, 127],
        [15, [255, 255, 127],
        [20, [255, 127, 127],
        [25, [127, 0, 0],
      ],
      pickable: true,
    }),
  ],
  onHover: event => console.log(event.raster),
});
```

### Data Properties

See [Data properties](data.md#data-properties) common for all layers.

### Style Properties

See [Style properties](style-properties.md) common for all layers.

#### `palette`

Type: color palette text or array, required

Palette used to interpolate values to colors.

Formats:

* text (`string`) - see [Text format](https://github.com/weatherlayers/cpt2js#text-format) for details
* array (`[number, PaletteColor][]`) - `PaletteColor` is any object accepted by [Chroma.js constructor](https://vis4.net/chromajs/#chroma)

#### `gridEnabled`

Type: boolean, optional

Default: `false`

Displays a grid of points to allow for verification how the rendered data aligns to the grid.

### Picking Info

Type: [`RasterPointProperties`](../types.md#rasterpointproperties)

If `pickable: true`, the picking info passed to callbacks (`onHover`, `onClick`, etc.) provides information on which pixel was picked. It contains an additional `raster` field.

Float32 data are recommended for the best precision.

See [Tooltip control](../controls/tooltip-control.md) and [BitmapLayer Pixel Picking](https://deck.gl/docs/api-reference/layers/bitmap-layer#pixel-picking).
