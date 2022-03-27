# Raster layer

Variable rendered as a color overlay

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// configure WeatherLayers Cloud client
WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      dataset: 'gfs/wind_10m_above_ground',
      datetime: '2022-01-01T00:00:00Z',

      // picking is supported
      pickable: ..., // boolean
    }),
  ],
  onHover: event => console.log(event.raster), // { value: number, direction?: number }
});
```

### Data properties

[Data properties](../data.md) are common for all layers in the cloud bundle.

### Style properties

[Style properties](../../standalone-bundle/layers/raster-layer.md) are the same as in the standalone bundle.
