# Particle layer

Vector variable rendered as animated particle simulation layer

```javascript
import { Deck } from '@deck.gl/core';
import { ParticleLayer } from '@weatherlayers/weatherlayers-gl';

const deckgl = new Deck({
  layers: [
    new ParticleLayer({
      id: 'particle',
      image: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      image2: ..., // { data: Uint8Array | Uint8ClampedArray | Float32Array, width: number, height: number }
      imageWeight: ..., // number (0-1)
      imageType: ..., // ImageType (SCALAR, VECTOR)
      imageUnscale: ..., // [number, number]
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
