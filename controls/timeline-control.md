# Timeline control

Timeline control allows playing datetimes as animation with linear interpolation between two subsequent datetimes

```javascript
import { TimelineControl } from 'weatherlayers';

const timelineControl = new TimelineControl({
  dataset: ..., // string (STAC Collection id)
  width: ..., // number
  onUpdate: event => {
    console.log(event.datetime); // string (STAC Item id)
    console.log(event.datetime2); // string (STAC Item id)
    console.log(event.datetimeWeight); // number
  },
});
```

![](../.gitbook/assets/timeline-control.png)

