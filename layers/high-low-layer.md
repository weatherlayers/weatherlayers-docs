# HighLow layer

Variable rendered as highs/lows

```javascript
import { Deck } from '@deck.gl/core';
import { HighLowLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new HighLowLayer({
      id: 'high-low',
      dataset: ..., // string (STAC Collection id)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      radius: ..., // number
      textColor: ..., // [number, number, number, number?]
      textOutlineColor: ..., // [number, number, number, number?]
      textSize: ..., // number
      opacity: ..., // number
    }),
  ],
});
```
