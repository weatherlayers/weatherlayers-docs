# Attribution Control

Attribution control shows the attribution for the data producer

### Example

![Attribution Control](../../.gitbook/assets/attribution-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const attributionControl = new WeatherLayers.AttributionControl({
  attribution: 'Data by NOAA / GFS',
});
```

### Constructor

#### `LegendControl(config: LegendConfig = {})`

### Config Properties

#### `attribution`

Type: string, required

Attribution to be displayed.

### Methods

See [Control methods](control-methods.md) common for all controls.

