# Raster layer

Variable rendered as a color overlay

```javascript
import { Deck } from '@deck.gl/core';
import { RasterLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new RasterLayer({
      id: 'raster',
      image: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number]
      colormapBreaks: ..., // [number, [number, number, number, number?]][]
      opacity: ..., // number
      pickable: ..., // boolean
    }),
  ],
  onHover: event => console.log(event.raster),
});
```
