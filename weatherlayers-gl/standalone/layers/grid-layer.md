# Grid layer

Variable rendered as grid of values or symbols (wind barbs, arrows)

```
import { Deck } from '@deck.gl/core';
import { GridLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new GridLayer({
      id: 'grid',
      image: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number]
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
