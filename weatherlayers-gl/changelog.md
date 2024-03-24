# Changelog

### 2024.3.0

_March 24, 2024_

New features:

* Add `directionOrigin`, `followCursorOffset`, `followCursorPlacement` to Tooltip control

Minor changes:

* Slow down particles in higher latitudes to make the particle speed constant, generate more particles in higher latitudes to keep the particle density uniform

Bug fixes:

* Fix detecting NaN in Float data, so that they are ignored for rendering

### 2024.2.3

_February 13, 2024_

Minor changes:

* Allow array in `iconSize`, merge `iconSize` and `iconMinSize` in Grid layer
  * ⚠️ Use an array value in `iconSize` instead of `iconMinSize`

### 2024.2.2

_February 12, 2024_

New features:

* Add `iconMinSize` to Grid layer, enables smooth scaled icon sizes
  * ⚠️ Set `iconMinSize` for the original behavior of scaled icon sizes by values

Bug fixes:

* Fix refreshing Grid and HighLow layer properties

### 2024.2.1

_February 8, 2024_

New features:

* Add `majorInterval` to Contour layer
  * ⚠️ Set `majorInterval` to `5 * interval` for the original behavior of every 5th contour line to be a major contour line

### 2024.2.0

_February 6, 2024_

New features:

* Add `palette` to Particle, Contour, Grid, HighLow layers
* Add `imageMinValue` and `imageMaxValue` to Particle, Raster, Contour, Grid, HighLow layers

Minor changes:

* Improve Particle layer performance
  * ⚠️ Use `ClipExtension` to hide particles outside of Mercator bounds
* Merge `getRasterPoints` function arguments to `ImageProperties` type
* Update default colors to remove opacity, prefer separate opacity

Peer dependencies:

* Update deck.gl to 8.9.34
* Update geotiff.js to 2.1.2

### 2024.1.1

_January 23, 2024_

Bug fixes:

* Fix rendering of regional data at left/right bound

### 2024.1.0

_January 14, 2024_

Minor changes:

* Update TooltipControl `followCursor` position origin between value and direction
* Update TooltipControl direction icon

Bug fixes:

* Fix interpolating nodata values at data edges

Peer dependencies:

* Update deck.gl to 8.9.33
* Update geotiff.js to 2.1.1

### 2023.12.1

_December 21, 2023_

New features:

* Add `density` to GridLayer

### 2023.12.0

_December 2, 2023_

New features:

* Add WebP support for custom data
* Enable picking in OpenLayers
* Add `minZoom`, `maxZoom` to all layers
  * ContourLayer has default `maxZoom = 10`. ParticleLayer has default `maxZoom = 15`. Other layers have no default values.
  * It's possible to override a lower default value to a higher value, but rendering artifacts may occur in high zoom levels due to a low precision.

Bug fixes:

* Fix parsing hex colors in RasterLayer palette\
  [https://github.com/weatherlayers/cpt2js/issues/3](https://github.com/weatherlayers/cpt2js/issues/3)
* Fix TooltipControl z-index for Leaflet

### 2023.11.1

_November 3, 2023_

Bug fixes:

* Drop grid points out of bounds

### 2023.11.0

_November 3, 2023_

New features:

* Add direction arrow icon to TooltipControl
* Add `directionFormat` to TooltipControl
* Add `followCursor` to TooltipControl

Peer dependencies:

* Update deck.gl to 8.9.32
* Update geotiff.js to 2.1.0

### 2023.10.3

_October 14, 2023_

New features:

* Enable picking in Mapbox/MapLibre interleaved mode

Bug fixes:

* Fix rendering incorrect nodata pixels in Safari

### 2023.10.2

_October 14, 2023_

Bug fixes:

* Use scoped CSS class names to avoid conflicts with global CSS class names

### 2023.10.1

_October 14, 2023_

Bug fixes:

* Fix basemap flickering due to ParticleLayer animation in MapLibre/Mapbox interleaved mode

Dependencies:

* Update deck.gl to 8.9.31

### 2023.10.0

_October 5, 2023_

New features:

* Add support for single-band Uint8 data format

### 2023.9.0

_September 30, 2023_

Bug fixes:

* Fix disabling layers in MapLibre/Mapbox interleaved mode
* Discard displaying obsolete points in HighLowLayer
* Download GeoTIFF file in a single request

Dependencies:

* Update deck.gl to 8.9.30

### 2023.8.1

_September 5, 2023_

Bug fixes:

* Fix corrupted build

### 2023.8.0

_September 5, 2023_

Minor changes:

* Add support for license development domains

Bug fixes:

* Fix controls to be clickable when added as MapLibre/Mapbox control

Dependencies:

* Update deck.gl to 8.9.27

### 2023.5.1

_May 21, 2023_

Bug fixes:

* Fix bundling with Webpack

### 2023.5.0

_May 16, 2023_

Minor changes:

* Add loader to TimelineControl
* Add LogoControl

### 2023.4.3

_May 5, 2023_

Bug fixes:

* Fix TimelineControl compatibility with older browsers

### 2023.4.2

_May 4, 2023_

Minor changes:

* Add `fps` config property to TimelineControl

### 2023.4.1

_May 4, 2023_

Bug fixes:

* Fix TimelineControl compatibility with older browsers

### 2023.4.0

_April 30, 2023_

New features:

* Add `getRasterPoints` function to get raster points for the given positions

Minor changes:

* Add `offsetDatetime` and `offsetDatetimeRange` functions to add hours to the given datetime
* Remove unused `loadText` function

Bug fixes:

* Verify that the library is deployed on a secure origin
* Verify that the license has an expected type before verifying the signature
* Log image URL if image decoding fails

Dependencies:

* Update deck.gl to 8.9.9

### 2023.3.4

_April 4, 2023_

Bug fixes:

* Fix broken build

### 2023.3.3

_April 4, 2023_

Bug fixes:

* Fix browser crash when ESM build is used with Vite

Dependencies:

* Update deck.gl to 8.9.6

### 2023.3.2

_March 31, 2023_

Minor changes:

* Update selected datetime in TimelineControl when updating the datetime from outside
* Add `pause` and `reset` methods to TimelineControl
* Add `datetimeFormatFunction` to TimelineControl
* Add `DatetimeISOString` type

### 2023.3.1

_March 31, 2023_

Minor changes:

* Optimize bundle size

Bug fixes:

* Update package exports to expose a default export for TS moduleResolution = node and unpkg.com
* Update TS typings to enable arbitrary layer props such as layer extensions

### 2023.3.0

_March 29, 2023_

New features:

* Publish as npm package
  * Install the library with `npm install weatherlayers-gl`
  * Use the library with `import WeatherLayers from 'weatherlayers-gl'`
* Update licensing approach to a separate `license.json` file
  * [Contact us](mailto:support@weatherlayers.com) to receive your license file
  * Provide the license file to the library with `WeatherLayers.setLicense(license)`
* Migrate to TypeScript
  * Typing files are provided as part of the distribution package
* Add [Front layer](layers/front-layer.md)

Minor changes:

* Add `image2`, `imageSmoothing` and `imageWeight` to HighLow layer
* Improve HighLow layer performance when zooming in/out
* Add `toggle`, `start`, `stop`, `stepBackward` and `stepForward` methods to TimelineControl

Bug fixes:

* Prefer default values over provided `undefined` values
* Remove references to `worker_threads` Node dependency

Peer dependencies:

* Update deck.gl to 8.9.4

### 2023.2.1

_March 20, 2023_

Bug fixes:

* Remove references to `worker_threads` Node dependency

### 2023.2.0

_February 16, 2023_

New features:

* Add cubic interpolation for smoother visualization\
  Rename `imageInterpolate` data property to `imageInterpolation`, change type from boolean to enum\
  Add `imageSmoothing` data property

Bug fixes:

* Fix parsing palettes with values in scientific notation\
  [https://github.com/weatherlayers/cpt2js/issues/2](https://github.com/weatherlayers/cpt2js/issues/2)
* Clamp to edge data on poles

### 2022.11.0

_November 17, 2022_

Minor changes:

* Add `unitFormat` to Grid and HighLow layer for consistent value formatting across layers and controls
* Add [Load Functions](functions.md#load-functions) for loading custom data

### 2022.10.0

_October 14, 2022_

New features:

* Add [Controls](controls/)

Bug fixes:

* Fix Particle layer to drop particles out of bounds, to support regional vector data\
  [https://github.com/weatherlayers/deck.gl-particle/issues/10](https://github.com/weatherlayers/deck.gl-particle/issues/10)

Minor changes:

* Rename HighLow and Grid layer `textFunction` style property to `textFormatFunction`

Peer dependencies:

* Update deck.gl to 8.8.4

### 2022.6.0

_July 8, 2022_

New features:

* Add [Contour layer](layers/contour-layer.md) computed on GPU for animation support\
  Replace previous Contour layer computed on CPU

Bug fixes:

* Fix half-pixel data rendering misalignment

Minor changes:

* Remove deprecated Raster layer `colormapBreaks` style property, use `palette` instead
* [Demo](https://demo.weatherlayers.com/) - separate overlaid and interleaved demos

Peer dependencies:

* Update deck.gl to 8.8.2

### 2022.5.0

_June 3, 2022_

New features:

* Add support for color palette text format\
  Deprecate raster layer `colormapBreaks` style property, use `palette` instead\
  [https://github.com/weatherlayers/cpt2js](https://github.com/weatherlayers/cpt2js)[\
  https://github.com/stac-extensions/raster/issues/17](https://github.com/stac-extensions/raster/issues/17)\
  [https://github.com/radiantearth/stac-spec/pull/1181](https://github.com/radiantearth/stac-spec/pull/1181)

### 2022.4.0

_May 11, 2022_

New features:

* Use [Calendar Versioning](https://calver.org/)
* Add [Grid layer](layers/grid-layer.md)

Bug fixes:

* Fix particle layer breaking in deck.gl auto-offset mode at zoom >= 12 on Mac M1\
  [https://github.com/weatherlayers/deck.gl-particle/issues/5](https://github.com/weatherlayers/deck.gl-particle/issues/5)
* Fix raster layer opacity with Google Maps vector basemap\
  [https://github.com/visgl/deck.gl/issues/6296](https://github.com/visgl/deck.gl/issues/6296)\
  [https://github.com/visgl/deck.gl/pull/6804](https://github.com/visgl/deck.gl/pull/6804)
* Fix raster layer disappearing in deck.gl auto-offset mode at zoom >= 12\
  [https://github.com/visgl/deck.gl/issues/6798](https://github.com/visgl/deck.gl/issues/6798)\
  [https://github.com/visgl/deck.gl/pull/6801](https://github.com/visgl/deck.gl/pull/6801)

Minor changes:

* [Demo](https://demo.weatherlayers.com/) - add standalone demos without deck.gl (experimental)

Peer dependencies:

* Update deck.gl to 8.7.5
