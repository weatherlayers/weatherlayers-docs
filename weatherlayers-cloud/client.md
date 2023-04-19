# Client

Client providing access to weather data from WeatherLayers Cloud or a compatible catalog

### Example

Configure client with your WeatherLayers Cloud access token created in [WeatherLayers Account](https://account.weatherlayers.com/).

```javascript
import * as WeatherLayersClient from 'weatherlayers-gl/client';

// use your WeatherLayers Cloud access token
const client = new WeatherLayersClient.Client({
  accessToken: 'xxx',
});
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



### Methods

#### `loadCatalog(): Promise<string[]>`

Loads dataset ids from the catalog.

#### `loadDataset(dataset: string, config: ClientConfig = {}): Promise<Dataset>`

Loads dataset from the catalog.

#### `loadDatasetSlice(dataset: string, datetimeRange: DatetimeISOStringRange, config: ClientConfig = {}): Promise<DatasetSlice>`

Loads dataset slice at the given datetime range from the catalog.

#### `loadDatasetData(dataset: string, datetime: DatetimeISOString, config: ClientConfig = {}): Promise<DatasetData>`

Loads dataset data at the given datetime from the catalog.

The current conditions can be loaded by providing `datetime = new Date().toISOString()`.

#### `loadDatasetSliceData(dataset: string, datetimeRange: DatetimeISOStringRange, datetime: DatetimeISOString, config: ClientConfig = {}): Promise<DatasetData>`

Loads dataset data at the given datetime from a dataset slice defined by the given datetime range. from the catalog.

The current conditions can be loaded by providing `datetime = new Date().toISOString()`.
