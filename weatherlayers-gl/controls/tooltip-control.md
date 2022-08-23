# Tooltip Control

Tooltip control shows the value (and the direction for vector datasets) at current mouse position on hovering the raster layer

### Example

![Tooltip Control](../../.gitbook/assets/tooltip-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const tooltipControl = new WeatherLayers.TooltipControl({
  deckgl: ...,
  unit: {
    unit: 'm/s',
  },
});
tooltipControl.addTo(document.getElementById('controls'));
```

### Constructor

#### `TooltipControl(config: TooltipConfig = {})`

### Config Properties

#### `deckgl`

Type: deck.gl instance, required

deck.gl instance to register the control events to.

#### `unit`

Type: `{ unit: string; scale?: number; offset?: number; decimals?: number }`, required

Unit definition to be used for formatting numbers.

### Methods

See [Control methods](control-methods.md) common for all controls.
