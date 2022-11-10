# Timeline Control

Timeline control allows playing datetimes as animation with linear interpolation between two subsequent datetimes

### Example

![Timeline Control](../../.gitbook/assets/timeline-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const files = [
  { datetime: '2021-09-01T20:00:00Z',  url: '...' },
  { datetime: '2021-09-01T21:00:00Z',  url: '...' },
  { datetime: '2021-09-01T22:00:00Z',  url: '...' },
];
let currentDatetime = datetimes[0];
const timelineControl = new WeatherLayers.TimelineControl({
  datetimes: datetimes,
  datetime: datetime,
  onPreload: datetimes => {
    // preload requested data
    return Promise.all(datetimes.map(datetime => files))
  },,
  onUpdate: datetime => {
    // update displayed data
    currentDatetime = datetime;
    update();
  },
});
timelineControl.addTo(document.getElementById('controls'));

async function update() {
  
}
```

### Constructor

#### `TimelineControl(config: TimelineConfig = {})`

### Config Properties

#### `width`

Type: number, optional

Default: 300

Width of the control.

#### `datetimes`

Type: array of strings (ISO 8601 datetime), required

Datetimes to be displayed in the timeline.

#### `datetimeInterpolate`

Type: boolean, optional

Default: true

#### `datetime`

Type: string (ISO 8601 datetime), required

Current datetime selected in the timeline.

#### `onPreload`

Type: `(datetimes: string[]) => Promise<void>`, optional

Preload callback, use for preloading requested data.

#### `onUpdate`

Type: `(datetime: string) => void`, optional

Update callback, use for updating displayed data.

### Methods

See [Control](control.md) for common Control methods.
