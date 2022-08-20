# Timeline Control

Timeline control allows playing datetimes as animation with linear interpolation between two subsequent datetimes

### Example

![Timeline Control](../../.gitbook/assets/timeline-control.png)

```javascript
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const timelineControl = new WeatherLayers.TimelineControl({
  datetimes: [
    '2021-09-01T20:00:00Z',
    '2021-09-01T21:00:00Z',
    '2021-09-01T22:00:00Z',
  ],
  datetime: '2021-09-01T21:00:00Z',
  onStart: async () => {
    // preload available data
  },,
  onUpdate: ({datetime}) => {
    // update displayed data
  },
});
```

### Properties

#### `width`

Type: number, optional

Default: 250

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

#### `onStart`

Type: `() => Promise<void>`, optional

Playback start callback, use for preloading available data.

#### `onUpdate`

Type: `({datetime: string}) => void`, optional

Update callback, use for updating displayed data.

#### `onStop`

Type: `() => void`, optional

Playback stop callback
