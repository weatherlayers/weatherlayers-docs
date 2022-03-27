# Contour layer

Variable rendered as contours

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ContourLayer({
      id: 'contour',
      
      // data properties
      image: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      imageInterpolate: ..., // boolean
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number] (unscale Uint8Array)
      
      // style properties
      delta: ..., // number
      color: ..., // [number, number, number, number?]
      width: ..., // number
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
