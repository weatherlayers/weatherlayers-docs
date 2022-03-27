# Data

Data properties are common for all layers in the cloud bundle.

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// configure WeatherLayers Cloud client
WeatherLayers.setClientConfig({
  accessToken: 'xxx',
});

const deckgl = new Deck({
  layers: [
    new WeatherLayers.XxxLayer({
      dataset: 'gfs/wind_10m_above_ground',
      datetime: '2022-01-01T00:00:00Z',
    }),
  ],
});
```

### Data properties

#### `dataset`

Type: string (STAC Collection ID), required

See [WeatherLayers Browser](https://browser.weatherlayers.com) for the list of available datasets.

#### `datetime`

Type: string (ISO 8601 datetime), required

See [WeatherLayers Browser](https://browser.weatherlayers.com) for the list of available datasets and their datetimes.

#### `datetimeInterpolate`

Type: boolean, optional

Default: `true`

If on and the datetime is missing, the data are interpolated using the nearest available datetimes.

#### `imageInterpolate`

Type: boolean, optional

Default: `true`

If on, the data are interpolated using the nearest available pixels.
