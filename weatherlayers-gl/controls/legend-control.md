# Legend Control

Legend control shows the color legend for the raster layer

### Example

![Legend Control](../../.gitbook/assets/legend-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const legendControl = new WeatherLayers.LegendControl({
  dataset: ..., // string (STAC Collection ID)
  width: ..., // number
  ticksCount: ..., // number
});
```
