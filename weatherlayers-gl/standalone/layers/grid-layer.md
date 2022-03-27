# Grid layer

Variable rendered as grid of values or symbols (wind barbs, arrows)

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new WeatherLayers.GridLayer({
      id: 'grid',
      image: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      imageInterpolate: ..., // boolean
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number] (unscale Uint8Array)
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
