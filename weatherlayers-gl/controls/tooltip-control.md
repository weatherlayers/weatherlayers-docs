# Tooltip Control

Tooltip control shows the value (and the direction for vector datasets) at current mouse position on hovering the raster layer

### Example

![Tooltip Control](../../.gitbook/assets/tooltip-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const tooltipControl = new WeatherLayers.TooltipControl({
  deckgl: ..., // deck.gl
  unit: ..., // Unit
});
```
