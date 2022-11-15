# Timeline Control

Timeline control allows playing datetimes as animation with linear interpolation between two subsequent datetimes

### Example

![Timeline Control](../../.gitbook/assets/timeline-control.png)

<pre class="language-javascript"><code class="lang-javascript">import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

const files = [
  { datetime: '2021-09-01T20:00:00Z',  url: '...' },
  { datetime: '2021-09-01T21:00:00Z',  url: '...' },
  { datetime: '2021-09-01T22:00:00Z',  url: '...' },
];
const datetimes = files.map(file => file.datetime);
let currentDatetime = datetimes[0];
const timelineControl = new WeatherLayers.TimelineControl({
  datetimes: datetimes,
  datetime: currentDatetime,
  onPreload: datetimes => {
    // preload requested data
    return Promise.all(datetimes.map(datetime => {
      return WeatherLayers.loadTextureData(files.find(file => file.datetime === datetime).url);
    });
  },
  onUpdate: datetime => {
    // update displayed data
    currentDatetime = datetime;
    update();
  },
});
timelineControl.addTo(document.getElementById('controls'));

async function update() {
  const startDatetime = WeatherLayers.getClosestStartDatetime(datetimes, currentDatetime);
  const endDatetime = WeatherLayers.getClosestEndDatetime(datetimes, currentDatetime);
  const imageWeight = WeatherLayers.getDatetimeWeight(startDatetime, endDatetime, currentDatetime);
<strong>  const image = await WeatherLayers.loadTextureData(files.find(file => file.datetime === startDatetime).url);
</strong>  const image2 = await WeatherLayers.loadTextureData(files.find(file => file.datetime === endDatetime).url);
  
  // update layers
  deckgl.setProps({
    layers: [
      new WeatherLayers.XxxLayer({
        image: image,
        image2: image2,
        imageWeight: imageWeight,
      }),
    ],
  });
}
update();</code></pre>

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
