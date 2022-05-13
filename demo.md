# Demo

### deck.gl

<table><thead><tr><th> </th><th data-type="checkbox">Raster</th><th data-type="checkbox">Contour</th><th data-type="checkbox">HighLow</th><th data-type="checkbox">Particle</th><th data-type="checkbox">Grid</th></tr></thead><tbody><tr><td><a href="https://demo.weatherlayers.com/map.html">Map (2D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/map-leaflet.html">Map + Leaflet (2D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/map-google-maps.html">Map + Google Maps (2D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/map-mapbox.html">Map + Mapbox (2D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/map-maplibre.html">Map + MapLibre (2D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/map-arcgis.html">Map + ArcGIS (2D)</a><br>(in development)</td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/map-arcgis-renderer.html">Map + ArcGIS renderer (2D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/globe.html">Globe (3D)</a></td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr><tr><td><a href="https://demo.weatherlayers.com/globe-arcgis-renderer.html">Globe + ArcGIS renderer (2D)</a><br>(in development)</td><td>true</td><td>true</td><td>true</td><td>true</td><td>true</td></tr></tbody></table>

Requires [WebGL 2](https://caniuse.com/webgl2) (Chrome, Firefox, Edge, Safari 15)

### Standalone without deck.gl

<table><thead><tr><th> </th><th data-type="checkbox">Raster</th><th data-type="checkbox">Contour</th><th data-type="checkbox">HighLow</th><th data-type="checkbox">Particle</th><th data-type="checkbox">Grid</th></tr></thead><tbody><tr><td><a href="https://demo.weatherlayers.com/mapbox.html">Mapbox (2D)</a></td><td>true</td><td>true</td><td>true</td><td>false</td><td>false</td></tr><tr><td><a href="https://demo.weatherlayers.com/maplibre.html">MapLibre (2D)</a></td><td>true</td><td>true</td><td>true</td><td>false</td><td>false</td></tr><tr><td><a href="https://demo.weatherlayers.com/mapbox-globe.html">Mapbox Globe (3D)</a></td><td>true</td><td>true</td><td>true</td><td>false</td><td>false</td></tr><tr><td><a href="https://demo.weatherlayers.com/arcgis-globe.html">ArcGIS Globe (3D)</a></td><td>true</td><td>true</td><td>true</td><td>false</td><td>false</td></tr><tr><td><a href="https://demo.weatherlayers.com/cesium-globe.html">Cesium Globe (3D)</a></td><td>true</td><td>true</td><td>true</td><td>false</td><td>false</td></tr></tbody></table>

### Layers and Datasets

| Layer             | Dataset                                                                                                                |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Raster            | all                                                                                                                    |
| Contour           | gfs/pressure\_mean\_sea\_level                                                                                         |
| HighLow           | gfs/pressure\_mean\_sea\_level                                                                                         |
| Particle          | gfs/wind\_10m\_above\_ground, cmems\_phy/currents                                                                      |
| Particle (waves)  | gfswave/waves                                                                                                          |
| Grid (values)     | gfs/temperature\_2m\_above\_ground, gfs/apparent\_temperature\_2m\_above\_ground, cmems\_sst/sea\_surface\_temperature |
| Grid (arrows)     | gfswave/waves, cmems\_phy/currents                                                                                     |
| Grid (wind barbs) | gfs/wind\_10m\_above\_ground                                                                                           |
