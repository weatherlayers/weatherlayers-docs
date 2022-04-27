# Changelog

### 2022.4.0

Changes:

* Update deck.gl dependency to 8.7.5
* Add standalone demos without deck.gl (experimental)\
  [Mapbox](https://demo.weatherlayers.com/mapbox.html), [MapLibre](https://demo.weatherlayers.com/maplibre.html), [Mapbox Globe](https://demo.weatherlayers.com/mapbox-globe.html), [ArcGIS Globe](https://demo.weatherlayers.com/arcgis-globe.html), [Cesium Globe](https://demo.weatherlayers.com/cesium-globe.html)

Bug fixes:

* Fix particle layer breaking in deck.gl auto-offset mode at zoom >= 12 on Mac M1\
  [https://github.com/weatherlayers/deck.gl-particle/issues/5](https://github.com/weatherlayers/deck.gl-particle/issues/5)
* Fix raster layer opacity with Google Maps vector basemap\
  [https://github.com/visgl/deck.gl/issues/6296](https://github.com/visgl/deck.gl/issues/6296)\
  [https://github.com/visgl/deck.gl/pull/6804](https://github.com/visgl/deck.gl/pull/6804)
* Fix raster layer disappearing in deck.gl auto-offset mode at zoom >= 12\
  [https://github.com/visgl/deck.gl/issues/6798](https://github.com/visgl/deck.gl/issues/6798)\
  [https://github.com/visgl/deck.gl/pull/6801](https://github.com/visgl/deck.gl/pull/6801)

### 2022.3.0

New features:

* [Grid layer](standalone-bundle/layers/grid-layer.md)
