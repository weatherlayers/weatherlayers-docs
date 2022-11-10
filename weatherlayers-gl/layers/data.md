# Data Loading

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data using load function
const image = await WeatherLayers.loadTextureDataCached(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
      bounds: [-180, -90, 180, 90],
    }),
  ],
});
```

### Example 2

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data manually
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
      bounds: [-180, -90, 180, 90],
    }),
  ],
});
```

