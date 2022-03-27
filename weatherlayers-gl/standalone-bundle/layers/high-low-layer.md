# HighLow layer

Variable rendered as highs/lows

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new WeatherLayers.HighLowLayer({
      id: 'high-low',
      image: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      imageInterpolate: ..., // boolean
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number] (unscale Uint8Array)
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
