# Particle layer

Vector variable rendered as animated particle simulation layer.

```javascript
import { Deck } from '@deck.gl/core';
import { ParticleLayer } from 'deck.gl-weatherlayers';

const dataUrl = ...; // string
const dataUrl2 = ...; // string

const deckgl = new Deck({
  layers: [
    new ParticleLayer({
      id: 'particle',
      image: dataUrl,
      image2: dataUrl2,
      imageWeight: ..., // number
      numParticles: ..., // number
      maxAge: ..., // number
      speedFactor: ..., // number
      color: ..., // [number, number, number]
      width: ..., // number
      opacity: ..., // number
    });
  ],
  _animate: true,
});
```

