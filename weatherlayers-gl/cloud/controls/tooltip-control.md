# Tooltip control

Tooltip control shows the value (and the direction for vector datasets) at current mouse position on hovering the raster layer

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const tooltipControl = new WeatherLayers.TooltipControl({
  dataset: ..., // string (STAC Collection ID)
  deckgl: ..., // deck.gl instance
});
```

![](../../../.gitbook/assets/tooltip-control.png)
