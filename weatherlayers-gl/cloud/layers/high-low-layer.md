# HighLow layer

Variable rendered as highs/lows

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new WeatherLayers.HighLowLayer({
      id: 'high-low',
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      radius: ..., // number
      textFontFamily: ..., // string
      textSize: ..., // number
      textColor: ..., // [number, number, number, number?]
      textOutlineWodth: ..., // number
      textOutlineColor: ..., // [number, number, number, number?]
      opacity: ..., // number
    }),
  ],
});
```
