# Data Loading

### Example - supported file formats

```javascript
import { Deck } from '@deck.gl/core';
import WeatherLayers from 'weatherlayers-gl';

// load data
const image = await WeatherLayers.loadTextureData(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
    }),
  ],
});
```

### Example 2 - custom file formats

```javascript
import { Deck } from '@deck.gl/core';
import WeatherLayers from 'weatherlayers-gl';

// load data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
    }),
  ],
});
```

