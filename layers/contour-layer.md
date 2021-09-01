# Contour layer

Variable rendered as contours

```javascript
import { Deck } from '@deck.gl/core';
import { ContourLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new ContourLayer({
      id: 'contour',
      dataset: ..., // string (STAC Collection id)
      datetime: ..., // string (STAC Item id)
      delta: ..., // number
      color: ..., // [number, number, number]
      width: ..., // number
      opacity: ..., // number
    }),
  ],
});
```

