# Client

Client providing access to WeatherLayers Cloud data

### Example

Configure WeatherLayers Cloud client with your access token created in [WeatherLayers Account](https://account.weatherlayers.com/).

```javascript
import * as WeatherLayersCloud from '@weatherlayers/weatherlayers-cloud';

// configure WeatherLayers Cloud client
const client = new WeatherLayersCloud.Client({
  accessToken: 'xxx',
});


```

### Constructor

#### `Client(config: ClientConfig = {})`

### Config properties

#### `url`

string

#### `accessToken`

string

#### `dataFormat`

string

### Methods

#### `loadCatalog(): Promise<string[]>`

Loads dataset ids from the catalog.

#### `loadDataset(dataset: string, options: { attributionLinkClass?: string }): Promise<Dataset>`

Loads dataset from the catalog.

#### `loadDatasetData(dataset: string, datetime: string, options: { datetimeInterpolate?: boolean }): Promise<DatasetData>`

Loads dataset data at datetime from the catalog.

