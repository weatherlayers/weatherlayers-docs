# Timeline Control

Timeline control allows playing datetimes as animation with linear interpolation between two subsequent datetimes

### Example

![Timeline Control](../../../.gitbook/assets/timeline-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// configure WeatherLayers Cloud client
WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const timelineControl = new WeatherLayers.TimelineControl({
  dataset: ..., // string (STAC Collection ID)
  datetime: ..., // string (ISO 8601 datetime)
  datetimeInterpolate: ..., // boolean
  width: ..., // number
  onUpdate: event => {
    console.log(event.datetime); // string (ISO 8601 datetime)
  },
});
```
