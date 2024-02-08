# Contour Layer

Variable rendered as contours

### Example

![Contour Layer](../../.gitbook/assets/contour-layer.png)

```javascript
import { Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from 'weatherlayers-gl';

// load data
const image = await WeatherLayers.loadTextureData(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ContourLayer({
      id: 'contour',
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
      // style properties
      interval: 200,
      extensions: [new ClipExtension()],
      clipBounds: [-181, -85.051129, 181, 85.051129],
    }),
  ],
});
```

### Data Properties

See [Data properties](data.md#data-properties) common for all layers.

### Style Properties

See [Style properties](style-properties.md) common for all layers.

#### `interval`

Type: number, required

Interval between contour lines in the data units. The greater interval, the less contour lines are rendered.

The value must be in the same units as the data image.

#### `majorInterval`

Type: number, optional

Interval between major contour lines in the data units. The greater interval, the less major contour lines are rendered.

The value must be in the same units as the data image.

#### `width`

Type: `number`, optional

Default: `1`

Width of the contour line. See [LineLayer getWidth](https://deck.gl/docs/api-reference/layers/line-layer#getwidth).

#### `color`

Type: color `[number, number, number, number?]`, optional

Default: `[255, 255, 255]`

Color of the contour line. See [LineLayer getColor](https://deck.gl/docs/api-reference/layers/line-layer#getcolor).

Major contour lines are rendered with full opacity, minor contour lines are rendered with half opacity.

#### `palette`

Type: color palette text or array, optional

Palette used to interpolate values to colors.

Formats:

* text (`string`) - see [Text format](https://github.com/weatherlayers/cpt2js#text-format) for details
* array (`[number, PaletteColor][]`) - `PaletteColor` is any object accepted by [Chroma.js constructor](https://vis4.net/chromajs/#chroma)
