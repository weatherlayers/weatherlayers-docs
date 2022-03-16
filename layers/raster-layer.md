# Raster layer

Variable rendered as a color overlay

```javascript
import { Deck } from '@deck.gl/core';
import { RasterLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new RasterLayer({
      id: 'raster',
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      colormapBreaks: ..., // [number, [number, number, number, number?]][]
      opacity: ..., // number
    }),
  ],
});
```
