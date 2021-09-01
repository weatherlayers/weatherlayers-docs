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
      datetime: ..., // string (STAC Item id)
      radius: ..., // number
      delta: ..., // number
      color: ..., // [number, number, number]
      outlineColor: // [number, number, number]
      opacity: ..., // number
    }),
  ],
});
```

