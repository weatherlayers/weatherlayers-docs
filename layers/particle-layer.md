# Particle layer

Vector variable rendered as animated particle simulation layer.

```javascript
import { Deck } from '@deck.gl/core';
import { ParticleLayer } from 'deck.gl-particle';

const particleUrl = ...; // string

const deckgl = new Deck({
  layers: [
    new ParticleLayer({
      id: 'particle',
      image: particleUrl,
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

