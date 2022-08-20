# Timeline Control

Timeline control allows playing datetimes as animation with linear interpolation between two subsequent datetimes

### Example

![Timeline Control](../../.gitbook/assets/timeline-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const timelineControl = new WeatherLayers.TimelineControl({
  width: ..., // number
  datetimes: ..., // string[] (ISO 8601 datetime)
  datetimeInterpolate: ..., // boolean
  datetime: ..., // string (ISO 8601 datetime)
  onStart: ..., // () => Promise<void>
  onStop: ..., // () => void
  onUpdate: ..., // ({datetime: string}) => void
});
```
