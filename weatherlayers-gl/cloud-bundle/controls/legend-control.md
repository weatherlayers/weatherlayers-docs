# Legend Control

Legend control shows the color legend for the raster layer

### Example

![Legend Control](<../../../.gitbook/assets/legend-control (1).png>)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// configure WeatherLayers Cloud client
WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const legendControl = new WeatherLayers.LegendControl({
  dataset: ..., // string (STAC Collection ID)
  width: ..., // number
  ticksCount: ..., // number
});
```
