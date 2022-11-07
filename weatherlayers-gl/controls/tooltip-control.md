# Tooltip Control

Tooltip control shows the value (and the direction for vector datasets) at current mouse position on hovering the raster layer

### Example

![Tooltip Control](../../.gitbook/assets/tooltip-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const tooltipControl = new WeatherLayers.TooltipControl({
  unitFormat: {
    unit: 'm/s',
  }
});
tooltipControl.addTo(document.getElementById('controls'));
deckgl.setProps({ onHover: event => tooltipControl.update(event.raster) });
```

### Constructor

#### `TooltipControl(config: TooltipConfig = {})`

### Config Properties

#### `unitFormat`

Type: `UnitFormat = { unit: string; scale?: number; offset?: number; decimals?: number }`, required

Unit definition to be used for formatting numbers.

### Methods

See [Control](control.md) for common Control methods.

#### `update(rasterValue: RasterPickingInfo | undefined)`

Type: `RasterPickingInfo = { value: number, direction?: number }`

Updates the tooltip displayed with the given `rasterValue` or hides the tooltip.
