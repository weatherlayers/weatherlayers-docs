# Contour layer

Variable rendered as contours

```javascript
import { Deck } from '@deck.gl/core';
import { ContourLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new ContourLayer({
      id: 'contour',
      image: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number]
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
