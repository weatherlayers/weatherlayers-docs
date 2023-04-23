# Changelog

### 2023.4.0

New features:

* Add `getRasterPoints` function to get raster points for the given positions

Minor changes:

* Add `addHoursToDatetime` function to add hours to the given datetime
* Remove unused `loadText` function
* Update deck.gl dependency to 8.9.9

Bug fixes:

* Verify that the library is deployed on a secure origin
* Verify that the license has an expected type before verifying the signature
* Log image URL if image decoding fails

### 2023.3.4

Minor changes:

* Update deck.gl dependency to 8.9.6

Bug fixes:

* Fix browser crash when ESM build is used with Vite

### 2023.3.2

Minor changes:

* Update selected datetime in Timeline control when updating the datetime from outside
* Add `pause` and `reset` methods to Timeline control
* Add `datetimeFormatFunction` to Timeline control
* Add `DatetimeISOString` type

### 2023.3.1

Minor changes:

* Optimize bundle size

Bug fixes:

* Update package exports to expose a default export for TS moduleResolution = node and unpkg.com
* Update TS typings to enable arbitrary layer props such as layer extensions

### 2023.3.0

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
* Add `toggle`, `start`, `stop`, `stepBackward` and `stepForward` methods to Timeline control
* Update deck.gl dependency to 8.9.4

Bug fixes:

* Prefer default values over provided `undefined` values
* Remove references to `worker_threads` Node dependency

### 2023.2.1

Bug fixes:

* Remove references to `worker_threads` Node dependency

### 2023.2.0

New features:

* Add cubic interpolation for smoother visualization\
  Rename `imageInterpolate` data property to `imageInterpolation`, change type from boolean to enum\
  Add `imageSmoothing` data property

Bug fixes:

* Fix parsing palettes with values in scientific notation\
  [https://github.com/weatherlayers/cpt2js/issues/2](https://github.com/weatherlayers/cpt2js/issues/2)
* Clamp to edge data on poles

### 2022.11.0

Minor changes:

* Add `unitFormat` to Grid and HighLow layer for consistent value formatting across layers and controls
* Add [Load Functions](functions.md#load-functions) for loading custom data

### 2022.10.0

New features:

* Add [Controls](controls/)

Bug fixes:

* Fix Particle layer to drop particles out of bounds, to support regional vector data\
  [https://github.com/weatherlayers/deck.gl-particle/issues/10](https://github.com/weatherlayers/deck.gl-particle/issues/10)

Minor changes:

* Rename HighLow and Grid layer `textFunction` style property to `textFormatFunction`
* Update deck.gl dependency to 8.8.4

### 2022.6.0

New features:

* Add [Contour layer](layers/contour-layer.md) computed on GPU for animation support\
  Replace previous Contour layer computed on CPU

Bug fixes:

* Fix half-pixel data rendering misalignment

Minor changes:

* Remove deprecated Raster layer `colormapBreaks` style property, use `palette` instead
* Update deck.gl dependency to 8.8.2
* [Demo](https://demo.weatherlayers.com/) - separate overlaid and interleaved demos

### 2022.5.0

New features:

* Add support for color palette text format\
  Deprecate raster layer `colormapBreaks` style property, use `palette` instead\
  [https://github.com/weatherlayers/cpt2js](https://github.com/weatherlayers/cpt2js)[\
  https://github.com/stac-extensions/raster/issues/17](https://github.com/stac-extensions/raster/issues/17)\
  [https://github.com/radiantearth/stac-spec/pull/1181](https://github.com/radiantearth/stac-spec/pull/1181)

### 2022.4.0

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

* Update deck.gl dependency to 8.7.5
* [Demo](https://demo.weatherlayers.com/) - add standalone demos without deck.gl (experimental)

### 2022.3.0

New features:

* Add [Grid layer](layers/grid-layer.md)
