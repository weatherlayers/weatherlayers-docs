# Particle layer

Vector variable rendered as animated particle simulation layer

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ParticleLayer({
      id: 'particle',
      image: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Float32Array, width: number, height: number }
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number] (unscale Uint8Array)
      numParticles: ..., // number
      maxAge: ..., // number
      speedFactor: ..., // number
      color: ..., // [number, number, number, number?]
      width: ..., // number
      opacity: ..., // number
    });
  ],
});
```
