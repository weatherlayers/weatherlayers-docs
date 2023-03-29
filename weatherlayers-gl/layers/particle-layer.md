# Particle Layer

Vector variable rendered as animated particle simulation layer

### Example

![Particle Layer](../../.gitbook/assets/particle-layer.png)

```javascript
import { Deck } from '@deck.gl/core';
import WeatherLayers from 'weatherlayers-gl';

// load data
const image = await WeatherLayers.loadTextureData(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.ParticleLayer({
      id: 'particle',
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
    }),
  ],
});
```

### Data Properties

See [Data properties](data.md#data-properties) common for all layers.

### Style Properties

See [Style properties](style-properties.md) common for all layers.

#### `numParticles`

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
