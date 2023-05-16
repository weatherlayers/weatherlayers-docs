# Attribution Control

Attribution control shows the attribution for the data producer

### Example

![Attribution Control](../../.gitbook/assets/attribution-control.png)

```javascript
import * as WeatherLayers from 'weatherlayers-gl';

const attributionControl = new WeatherLayers.AttributionControl({
  attribution: 'Data by NOAA / GFS',
});
attributionControl.addTo(document.getElementById('controls'));
```

### Constructor

#### `AttributionControl(config: AttributionConfig = {})`

### Config Properties

#### `attribution`

Type: string, required

Attribution to be displayed.

### Methods

See [Control](control.md) for common Control methods.

