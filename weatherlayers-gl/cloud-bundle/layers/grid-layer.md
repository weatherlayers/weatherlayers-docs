# Grid layer

Variable rendered as grid of values or symbols (arrows, wind barbs)

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
    new WeatherLayers.GridLayer({
      dataset: 'gfs/wind_10m_above_ground',
      datetime: '2022-01-01T00:00:00Z',
    }),
  ],
});
```

### Data properties

[Data properties](../data.md) are common for all layers in the cloud bundle.

### Style properties

[Style properties](../../standalone-bundle/layers/grid-layer.md) are the same as in the standalone bundle.
