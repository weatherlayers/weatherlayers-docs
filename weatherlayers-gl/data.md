# Data loading

### Example

```javascript
import { Deck, COORDINATE_SYSTEM } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
    }),
  ],
});
```

### Example: GeoTIFF

```javascript
import { Deck, COORDINATE_SYSTEM } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import * as GeoTIFF from 'geotiff';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

async function loadGeotiff(url) {
  const geotiff = await GeoTIFF.fromUrl(url, { allowFullFile: true });
  const geotiffImage = await geotiff.getImage(0);

  const data = await geotiffImage.readRasters({ interleave: true });
  const nodata = geotiffImage.getGDALNoData();
  const maskedData = nodata != undefined ?
    new data.constructor(Array.from(data).map(value => value !== nodata ? value : NaN)) :
    data;

  const width = geotiffImage.getWidth();
  const height = geotiffImage.getHeight();

  const image = { data: maskedData, width, height };
  return image;
}

// load custom self-hosted data
const image = await loadGeoTiff(url);

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      // data properties
      image: image,
      bounds: [-180, -90, 180, 90],
    }),
  ],
});
```

