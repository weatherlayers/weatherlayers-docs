# Raster layer

Variable rendered as a color overlay

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new WeatherLayers.RasterLayer({
      id: 'raster',
      
      // data properties
      image: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      imageInterpolate: ..., // boolean
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number] (unscale Uint8Array)
      
      // style properties
      colormapBreaks: ..., // [number, [number, number, number, number?]][]
      opacity: ..., // number
      
      // picking is supported
      pickable: ..., // boolean
    }),
  ],
  onHover: event => console.log(event.raster), // { value: number, direction?: number }
});
```
