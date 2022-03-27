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
    }),
  ],
});
```

### Example: picking

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
      picking: true,
    }),
  ],
  onHover: event => console.log(event.raster),
});
```

### Data properties

[Data properties](../data.md) are common for all layers in the cloud bundle.

### Style properties

[Style properties](../../standalone-bundle/layers/raster-layer.md) are the same as in the standalone bundle.

### Picking info

Picking info is the same as in the standalone bundle.
