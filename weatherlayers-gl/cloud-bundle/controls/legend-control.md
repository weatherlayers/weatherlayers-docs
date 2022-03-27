# Legend control

Legend control shows the color legend for the raster layer

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const legendControl = new WeatherLayers.LegendControl({
  dataset: ..., // string (STAC Collection ID)
  width: ..., // number
  ticksCount: ..., // number
});
```

![](../../../.gitbook/assets/legend-control.png)
