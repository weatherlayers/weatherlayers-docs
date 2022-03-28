# HighLow Layer

Variable rendered as highs/lows

### Example

![HighLow Layer](../../../.gitbook/assets/high-low-layer.png)

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// configure WeatherLayers Cloud client
WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const deckgl = new Deck({
  layers: [
    new WeatherLayers.HighLowLayer({
      // data properties
      dataset: 'gfs/pressure_mean_sea_level',
      datetime: '2022-01-01T00:00:00Z',
      
      // style properties
      radius: 1000, // km
    }),
  ],
});
```

### Data Properties

[Data properties](../data.md#data-properties) are common for all layers in the cloud bundle.

### Style Properties

[Style properties](../../standalone-bundle/layers/raster-layer.md#style-properties) are the same as in the standalone bundle.
