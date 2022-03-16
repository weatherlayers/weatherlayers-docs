# Grid layer

```
import { Deck } from '@deck.gl/core';
import { GridLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new HighLowLayer({
      id: 'high-low',
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      style: ..., // string (VALUE, WIND_BARB, ARROW)
      textFontFamily: ..., // string
      textSize: ..., // number
      textColor: ..., // [number, number, number, number?]
      textOutlineWodth: ..., // number
      textOutlineColor: ..., // [number, number, number, number?]
      iconSize: ..., // number
      iconColor: ..., // [number, number, number, number?]
      opacity: ..., // number
    }),
  ],
});
```
