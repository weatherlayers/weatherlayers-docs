# Tooltip Control

Tooltip control shows the value (and the direction for vector datasets) at current mouse position on hovering the raster layer

### Example

![Tooltip Control](../../.gitbook/assets/tooltip-control.png)

```javascript
import * as WeatherLayers from 'weatherlayers-gl';

const tooltipControl = new WeatherLayers.TooltipControl({
  unitFormat: {
    unit: 'm/s',
  },
  directionFormat: WeatherLayers.DirectionFormat.CARDINAL3,
  followCursor: true,
});
tooltipControl.addTo(deckgl.getCanvas().parentElement);
deckgl.setProps({ onHover: event => tooltipControl.updatePickingInfo(event) });
```

### Constructor

#### `TooltipControl(config: TooltipConfig = {})`

### Config Properties

#### `unitFormat`

Type: [`UnitFormat`](../types.md#unitformat), required

Unit definition to be used for formatting.

#### `directionType`

Type: [`DirectionType`](../types.md#directiontype), optional

Default value: `INWARD`

Direction type to be used for formatting.

#### `directionFormat`

Type: [`DirectionFormat`](../types.md#directionformat), optional

Default value: `VALUE`

Direction format to be used for formatting.

#### `followCursor`

Type: boolean, optional

Default value: false

Follow the mouse cursor position.

#### `followCursorOffset`

Type: number, optional

Default value: `16`

Offset from the mouse cursor position.

#### `followCursorPlacement`

Type: [`Placement`](../types.md#placement), optional

Default value: `BOTTOM`

Placement from the mouse cursor position.

### Methods

See [Control](control.md) for common Control methods.

#### `update(rasterPointProperties:` [`RasterPointProperties`](../types.md#rasterpointproperties) `| undefined): void`

Updates the tooltip displayed with the given `rasterPointProperties` or hides the tooltip.

#### `updatePickingInfo(pickingInfo: PickingInfo & { raster?:` [`RasterPointProperties`](../types.md#rasterpointproperties) `}): void`

Updates the tooltip displayed with the given `pickingInfo` or hides the tooltip.
