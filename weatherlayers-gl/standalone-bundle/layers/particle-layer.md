# Particle layer

Vector variable rendered as animated particle simulation layer

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ParticleLayer({
      image: image,
    }),
  ],
});
```

### Data properties

[Data properties](../data.md#data-properties) are common for all layers in the standalone bundle.

### Style properties

#### numParticles

Type: number, optional

Default: `5000`

Number of the particles. The greater number of particles, the denser particle trails.

#### `maxAge`

Type: number, optional

Default: `100`

Max age of the particles in frames. The greater max age, the longer particle trails.

#### `speedFactor`

Type: number `0-1`, optional

Default: `1`

Speed factor of the particles. The greater speed factor, the longer particle trails.

#### `width`

Type: `number`, optional

Default: `1`

Width of the line. See [LineLayer getWidth](https://deck.gl/docs/api-reference/layers/line-layer#getwidth).

#### `color`

Type: color `[number, number, number, number?]`, optional

Default: `[255, 255, 255, 51]`

Color of the line. See [LineLayer getColor](https://deck.gl/docs/api-reference/layers/line-layer#getcolor).

#### `opacity`

Type: number, optional

Default: `1`

The opacity of the layer. See [Layer opacity](https://deck.gl/docs/api-reference/core/layer#opacity).