# Raster layer

Variable rendered as a color overlay

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      image: image,
      
      // picking is supported
      pickable: ..., // boolean
    }),
  ],
  onHover: event => console.log(event.raster), // { value: number, direction?: number }
});
```

### Data properties

[Data properties](../data.md) are common for all layers in the standalone bundle.

### Style properties

#### `colormapBreaks`

Type: array of tuples of value and color `[number, [number, number, number, number?]][]`, required

Colormap breaks used to interpolate the colormap between values and colors.

#### `opacity`

Type: number, optional

Default: `1`

The opacity of the layer. See [Layer opacity](https://deck.gl/docs/api-reference/core/layer#opacity).
