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

// load dataset slice, load data in the first available datetime
const dataset = 'gfs/wind_10m_above_ground';
const {title, unitFormat, attribution, referenceDatetimeRange, palette} = await client.loadDataset(dataset);
const {datetimes} = await client.loadDatasetSlice(dataset, datetimeRange);
const datetime = datetimes[0];
const {image, image2, imageWeight, imageType, imageUnscale, bounds} = await client.loadDatasetData(dataset, datetime);
```

### Example: Load current data

```javascript
// load current data
const dataset = 'gfs/wind_10m_above_ground';
const {title, unitFormat, attribution, referenceDatetimeRange, palette} = await client.loadDataset(dataset);
const {image, image2, imageWeight, imageType, imageUnscale, bounds} = await client.loadDatasetData(dataset);
```

### Example: Load data by datetime

```javascript
// calculate the datetime range for visualization as 0-24 forecast
const datetimeRange = WeatherLayers.offsetDatetimeRange(new Date().toISOString(), 0, 24);

// load dataset slice, load data in the first available datetime
const dataset = 'gfs/wind_10m_above_ground';
const {title, unitFormat, attribution, referenceDatetimeRange, palette} = await client.loadDataset(dataset);
const {datetimes} = await client.loadDatasetSlice(dataset, datetimeRange);
const datetime = datetimes[0];
const {image, image2, imageWeight, imageType, imageUnscale, bounds} = await client.loadDatasetData(dataset, datetime);
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

#### `unitSystem`

Type: [`UnitSystem`](types.md#unitsystem), optional

Default: `METRIC`

Unit system for unit format definition.

#### `attributionLinkClass`

Type: string, optional

Attribution link class, used in `Dataset`, `attribution` field

#### `datetimeStep`

Type: number, optional

Default: `1`

Minimal step in hours between datetimes.

#### `datetimeInterpolate`

Type: boolean, optional

Enable datetime interpolation.

For example, if a datetime 6:30 is requested, but 6:00 and 7:00 exist, `{ image: <6:00>, image2: <7:00>, imageWeight: 0.5 }` is returned by `loadDatasetData`.

### Methods

#### `loadCatalog(): Promise<string[]>`

Loads dataset ids from the catalog.

#### `loadDataset(dataset: string, config: ClientConfig = {}): Promise<`[`Dataset`](types.md#dataset)`>`

Loads dataset metadata from the catalog.

#### `loadDatasetSlice(dataset: string, datetimeRange:` [`DatetimeISOStringRange`](types.md#datetimeisostringrange)`, config: ClientConfig = {}): Promise<`[`DatasetSlice`](types.md#datasetslice)`>`

Loads dataset slice with available datetimes in the given datetime range from the catalog.

The current data with offset can be loaded by providing `datetimeRange = WeatherLayers.offsetDatetimeRange(new Date().toISOString(), 0, 24)`.

#### `loadDatasetData(dataset: string, datetime?:` [`DatetimeISOString`](types.md#datetimeisostring)`, config: ClientConfig = {}): Promise<`[`DatasetData`](types.md#datasetdata)`>`

Loads dataset data at the given datetime from the catalog. If the datetime is not provided, the current data is loaded.
