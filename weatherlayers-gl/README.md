# WeatherLayers GL

WeatherLayers GL is a library of high-performance interactive weather visualization layers and controls, which can be customized in real-time and supports integration with major mapping libraries. The library can be used either with custom self-hosted data or with [WeatherLayers Cloud](../weatherlayers-cloud/).

Peer dependencies:

* [deck.gl](https://deck.gl) >= 9.0.7
* [luma.gl](https://luma.gl/) >= 9.0.10
* [geotiff.js](https://github.com/geotiffjs/geotiff.js/) >= 2.1.3 (if loading texture data from GeoTIFF)
* [maplibre-gl-js](https://github.com/maplibre/maplibre-gl-js) >= 3.0.0 (if using MapLibre with deck.gl interleaved to support WebGL2)
* [mapbox-gl-js](https://github.com/mapbox/mapbox-gl-js) >= 3.0.0 (if using Mapbox with deck.gl interleaved to support WebGL2)

### Versioning

WeatherLayers GL uses [Calendar Versioning](https://calver.org/) schema `YYYY.MM.MICRO`, e.g. `2022.4.0`.
