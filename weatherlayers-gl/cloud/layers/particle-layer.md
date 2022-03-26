# Particle layer

Vector variable rendered as animated particle simulation layer

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ParticleLayer({
      id: 'particle',
      dataset: ..., // string (STAC Collection ID)
      datetime: ..., // string (ISO 8601 datetime)
      datetimeInterpolate: ..., // boolean
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
