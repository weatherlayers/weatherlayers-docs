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
      datetime: ..., // string (STAC Item id)
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

Linear interpolation between two subsequent datetimes

```javascript
new ParticleLayer({
  ...
  datetime: ..., // string (STAC Item id)
  datetime2: ..., // string (STAC Item id)
  datetimeWeight: ..., // number
});
```

