# Contour layer

Variable rendered as contours

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
    new WeatherLayers.ContourLayer({
      dataset: 'gfs/pressure_mean_sea_level',
      datetime: '2022-01-01T00:00:00Z',
    }),
  ],
});
```

### Data properties

[Data properties](../data.md) are common for all layers in the cloud bundle.

### Style properties

[Style properties](../../standalone-bundle/layers/contour-layer.md) are the same as in the standalone bundle.
