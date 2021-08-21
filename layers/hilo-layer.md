# Hilo layer

Variable rendered as highs/lows

```javascript
import { Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import { ContourLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new ContourLayer({
      id: 'contour',
      dataset: ..., // string (STAC Collection id)
      datetime: ..., // string (STAC Item id)
      color: ..., // [number, number, number]
      width: ..., // number
      opacity: ..., // number
      hiloEnabled: ..., // boolean
      extensions: [new ClipExtension()],
      clipBounds: [-360, -85.051129, 360, 85.051129],
    }),
  ],
});
```

