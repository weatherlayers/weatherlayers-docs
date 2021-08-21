# Raster layer

Variable rendered as a color overlay

```javascript
import { COORDINATE_SYSTEM, Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import GL from '@luma.gl/constants';
import { RasterLayer } from 'weatherlayers';

const deckgl = new Deck({
  layers: [
    new RasterLayer({
      id: 'raster',
      dataset: ..., // string (STAC Collection id)
      datetime: ..., // string (STAC Item id)
      colormapBreaks: ..., // [number, [number, number, number]][]
      opacity: ..., // number
      bounds: [-180, -90, 180, 90],
      _imageCoordinateSystem: COORDINATE_SYSTEM.LNGLAT,
      extensions: [new ClipExtension()],
      clipBounds: [-360, -85.051129, 360, 85.051129],
    }),
  ],
});
```

Linear interpolation between two subsequent datetimes

```javascript
new RasterLayer({
  ...
  datetime: ..., // string (STAC Item id)
  datetime2: ..., // string (STAC Item id)
  datetimeWeight: ..., // number
})
```

