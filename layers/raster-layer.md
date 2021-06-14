# Raster layer

Variables rendered as an overlay, colored by a colormap.

Scalar variables are rendered as-is. Vector variables need to be converted to their length.

```text
import { COORDINATE_SYSTEM, Deck } from '@deck.gl/core';
import { ClipExtension } from '@deck.gl/extensions';
import GL from '@luma.gl/constants';

// build latest https://github.com/kylebarron/deck.gl-raster
import { RasterLayer, linearRescale, vectorLength, colormap, maskImage } from './deck.gl-raster';

const rasterUrl = ...; // string
const colormapUrl = ...; // string
const vector = ...; // boolean

const deckgl = new Deck({
  layers: [
    new RasterLayer({
      id: 'raster',
      images: {
        imageRgba: {
          data: rasterUrl,
          format: GL.RGB,
          parameters: {
            [GL.TEXTURE_MIN_FILTER]: GL.LINEAR,
            [GL.TEXTURE_MAG_FILTER]: GL.LINEAR,
          },
        },
        imageColormap: {
          data: colormapUrl,
          format: GL.RGBA,
          parameters: {
            [GL.TEXTURE_MIN_FILTER]: GL.LINEAR,
            [GL.TEXTURE_MAG_FILTER]: GL.LINEAR,
          },
        },
        imageMask: {
          data: rasterUrl,
          format: GL.ALPHA,
          parameters: {
            [GL.TEXTURE_MIN_FILTER]: GL.LINEAR,
            [GL.TEXTURE_MAG_FILTER]: GL.LINEAR,
          },
        },
      },
      modules: [
        rgbaImage,
        ...(vector ? [
          linearRescale,
          vectorLength,
        ] : []),
        colormap,
        maskImage,
      ],
      moduleProps: {
        linearRescaleScaler: 2,
        linearRescaleOffset: -1,
        colormapScaler: 1,
        colormapOffset: 0,
      },
      opacity: ..., // number
      bounds: [-180, -90, 180, 90],
      _imageCoordinateSystem: COORDINATE_SYSTEM.LNGLAT,
      extensions: [new ClipExtension()],
      clipBounds: [-360, -85.051129, 360, 85.051129],
    }),
  ],
});
```

