# Raster Layer

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
      // data properties
      dataset: 'gfs/wind_10m_above_ground',
      datetime: '2022-01-01T00:00:00Z',
      
      // style properties
      colormapBreaks: [
        [0, [255, 255, 255]],
        [5, [127, 255, 255]],
        [10, [127, 255, 127]],
        [15, [255, 255, 127]],
        [20, [255, 127, 127]],
        [25, [127, 0, 0]],
      ],
    }),
  ],
});
```

### Example: Picking

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
      // data properties
      dataset: 'gfs/wind_10m_above_ground',
      datetime: '2022-01-01T00:00:00Z',
      
      // style properties
      colormapBreaks: [
        [0, [255, 255, 255]],
        [5, [127, 255, 255]],
        [10, [127, 255, 127]],
        [15, [255, 255, 127]],
        [20, [255, 127, 127]],
        [25, [127, 0, 0]],
      ],

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

[Picking info](../../standalone-bundle/layers/raster-layer.md) is the same as in the standalone bundle.
