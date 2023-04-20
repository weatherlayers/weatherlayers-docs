# Client

Client providing access to weather data from WeatherLayers Cloud or a compatible catalog

### Example

Configure client with your WeatherLayers Cloud access token created in [WeatherLayers Account](https://account.weatherlayers.com/).

```javascript
import * as WeatherLayersClient from 'weatherlayers-gl/client';

// use your WeatherLayers Cloud access token
const client = new WeatherLayersClient.Client({
  accessToken: 'xxx',
  datetimeInterpolate: true,
});

// load dataset slice, the most recent reference datetime with 24-hour forecast
const dataset = 'gfs/wind_10m_above_ground';
const {title, unitFormat, attribution, referenceDatetimeRange, palette} = await client.loadDataset(dataset);
const datetimeRange = [referenceDatetimeRange[1], WeatherLayers.addHoursToDatetime(referenceDatetimeRange[1], 24)];
const {datetimes} = await client.loadDatasetSlice(dataset, datetimeRange);
const datetime = datetimes[0];
const {image, image2, imageWeight, imageType, imageUnscale, bounds} = await client.loadDatasetSliceData(dataset, datetimeRange, datetime);
```

### Constructor

#### `Client(config: ClientConfig = {})`

### Config properties

#### `url`

Type: string, optional

Default: `https://catalog.weatherlayers.com` (WeatherLayers Cloud)

Catalog url

#### `accessToken`

Type: string, optional

Default: none (but required for WeatherLayers Cloud)

Catalog access token

#### `dataFormat`

Type: string, optional

Default: `byte.png`

GeoTIFF requires [geotiff.js ](https://github.com/geotiffjs/geotiff.js/)as a peer dependency.

#### `attributionLinkClass`

Type: string, optional

Attribution link class, used in `Dataset`, `attribution` field

#### `datetimeInterpolate`

Type: boolean, optional

Enable datetime interpolation.

For example, if a datetime 6:30 is requested, but 6:00 and 7:00 exist, `{ image: 6:00, image2: 7:00, imageWeight: 0.5 }` is returned by `loadDatasetSliceData`.

### Methods

#### `loadCatalog(): Promise<string[]>`

Loads dataset ids from the catalog.

#### `loadDataset(dataset: string, config: ClientConfig = {}): Promise<Dataset>`

Loads dataset metadata from the catalog.

#### `loadDatasetSlice(dataset: string, datetimeRange: DatetimeISOStringRange, config: ClientConfig = {}): Promise<DatasetSlice>`

Loads dataset slice with available datetimes in the given datetime range from the catalog.

#### `loadDatasetData(dataset: string, datetime: DatetimeISOString, config: ClientConfig = {}): Promise<DatasetData>`

Loads dataset data at the given datetime from the catalog.

Use when requesting a static datetime.

The current data can be loaded by providing `datetime = new Date().toISOString()`.

Doesn't support datetime interpolation.

#### `loadDatasetSliceData(dataset: string, datetimeRange: DatetimeISOStringRange, datetime: DatetimeISOString, config: ClientConfig = {}): Promise<DatasetData>`

Loads dataset data at the given datetime from a dataset slice defined by the given datetime range. from the catalog.

Use when requesting a dynamic datetime from a larger static datetime range.

The current data can be loaded by providing `datetime = new Date().toISOString()`.

Supports datetime interpolation, needs to be enabled with `config = { datetimeInterpolate: true }`.
