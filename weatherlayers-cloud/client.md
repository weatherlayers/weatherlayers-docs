# Catalog Client

Client providing access to weather data from WeatherLayers Catalog

### Example

Configure WeatherLayers Catalog Client with your WeatherLayers Cloud access token created in [WeatherLayers Account](https://account.weatherlayers.com/).

```javascript
import * as WeatherLayersCatalogClient from '@weatherlayers/weatherlayers-catalog-client';

// configure WeatherLayers Catalog Client with your WeatherLayers Cloud access token
const client = new WeatherLayersCatalogClient.Client({
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

### Methods

#### `loadCatalog(): Promise<string[]>`

Loads dataset ids from the catalog.

#### `loadDataset(dataset: string, options: { attributionLinkClass?: string }): Promise<Dataset>`

Loads dataset from the catalog.

#### `loadDatasetData(dataset: string, datetime: string, options: { datetimeInterpolate?: boolean }): Promise<DatasetData>`

Loads dataset data at datetime from the catalog.

