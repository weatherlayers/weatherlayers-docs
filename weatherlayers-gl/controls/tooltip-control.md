# Tooltip Control

Tooltip control shows the value (and the direction for vector datasets) at current mouse position on hovering the raster layer

### Example

![Tooltip Control](../../.gitbook/assets/tooltip-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const tooltipControl = new WeatherLayers.TooltipControl({
  unit: {
    unit: 'm/s',
  },
});
tooltipControl.addTo(document.getElementById('controls'));
deckgl.setProps({ onHover: event => tooltipControl.update(event.raster) });
```

### Constructor

#### `TooltipControl(config: TooltipConfig = {})`

### Config Properties

#### `unit`

Type: `StacRasterUnit = { unit: string; scale?: number; offset?: number; decimals?: number }`, required

Unit definition to be used for formatting numbers.

### Methods

See [Control methods](control-methods.md) common for all controls.

#### `update(event: TooltipHoverEvent | undefined)`

Type: `TooltipHoverEvent = { value: number, direction?: number }`

Updates the tooltip displayed or hides it.
