# Particle layer

Vector variable rendered as animated particle simulation layer

```javascript
import { Deck } from '@deck.gl/core';
import { ParticleLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new ParticleLayer({
      id: 'particle',
      dataset: ..., // string (STAC Collection id)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
      numParticles: ..., // number
      maxAge: ..., // number
      speedFactor: ..., // number
      color: ..., // [number, number, number]
      width: ..., // number
      opacity: ..., // number
    });
  ],
});
```

