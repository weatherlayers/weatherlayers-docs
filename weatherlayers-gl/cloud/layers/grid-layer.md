# Grid layer

Variable rendered as grid of values or symbols (wind barbs, arrows)

```
import { Deck } from '@deck.gl/core';
import { GridLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new GridLayer({
      id: 'grid',
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      style: ..., // GridStyle (VALUE, WIND_BARB, ARROW)
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
