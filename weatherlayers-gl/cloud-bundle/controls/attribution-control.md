# Attribution control

Attribution control shows the attribution for the data producer

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const attributionControl = new WeatherLayers.AttributionControl({
  dataset: ..., // string (STAC Collection ID)
});
```

![](../../../.gitbook/assets/attribution-control.png)
