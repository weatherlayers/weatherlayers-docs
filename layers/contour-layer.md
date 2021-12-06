# Contour layer

Variable rendered as contours

```javascript
import { Deck } from '@deck.gl/core';
import { ContourLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new ContourLayer({
      id: 'contour',
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      delta: ..., // number
      color: ..., // [number, number, number, number?]
      width: ..., // number
      textColor: ..., // [number, number, number, number?]
      textOutlineColor: ..., // [number, number, number, number?]
      textSize: ..., // number
      opacity: ..., // number
    }),
  ],
});
```
