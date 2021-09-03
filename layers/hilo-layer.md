# Hilo layer

Variable rendered as highs/lows

```javascript
import { Deck } from '@deck.gl/core';
import { ContourLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new HiloLayer({
      id: 'hilo',
      dataset: ..., // string (STAC Collection id)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      radius: ..., // number
      color: ..., // [number, number, number]
      outlineColor: // [number, number, number]
      opacity: ..., // number
    }),
  ],
});
```

