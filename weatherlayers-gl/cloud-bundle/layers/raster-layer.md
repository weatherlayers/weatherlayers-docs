# Raster layer

Variable rendered as a color overlay

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      id: 'raster',

      // data properties
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      imageInterpolate: ..., // boolean

      // style properties are the same as in the standalone bundle
      
      // picking is supported
      pickable: ..., // boolean
    }),
  ],
  onHover: event => console.log(event.raster), // { value: number, direction?: number }
});
```
