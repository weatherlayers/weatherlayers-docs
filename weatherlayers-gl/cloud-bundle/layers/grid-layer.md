# Grid layer

Variable rendered as grid of values or symbols (wind barbs, arrows)

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const deckgl = new Deck({
  layers: [
    new WeatherLayers.GridLayer({
      id: 'grid',
      
      // data properties
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      imageInterpolate: ..., // boolean

      // style properties are the same as in the standalone bundle
    }),
  ],
});
```
