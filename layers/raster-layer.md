# Raster layer

Variables rendered as an overlay, colored by a colormap.

Scalar variables are rendered as-is. Vector variables need to be converted to their length.

```javascript
import { COORDINATE_SYSTEM, Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import GL from '@luma.gl/constants';
import { IMAGE_TYPE, RasterLayer } from 'deck.gl-weatherlayers';

const dataUrl = ...; // string
const dataUrl2 = ...; // string
const vector = ...; // boolean
const colormapUrl = ...; // string

const deckgl = new Deck({
  layers: [
    new RasterLayer({
      id: 'raster',
      image: dataUrl,
      image2: dataUrl2,
      imageWeight: ..., // number
      imageType: vector ? IMAGE_TYPE.VECTOR : IMAGE_TYPE.SCALAR,
      colormapImage: colormapUrl,
      opacity: ..., // number
      bounds: [-180, -90, 180, 90],
      _imageCoordinateSystem: COORDINATE_SYSTEM.LNGLAT,
      extensions: [new ClipExtension()],
      clipBounds: [-360, -85.051129, 360, 85.051129],
    }),
  ],
});
```

