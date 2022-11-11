# Data Loading

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load data
const image = await WeatherLayers.loadTextureDataCached(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      image: image,
    }),
  ],
});
```

### Example 2

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

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

