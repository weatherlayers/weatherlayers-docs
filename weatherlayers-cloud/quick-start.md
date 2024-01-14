# Quick Start

### Installation

```
npm install weatherlayers-gl
```

### Trial Usage

```javascript
import * as WeatherLayersClient from 'weatherlayers-gl/client';

// use your WeatherLayers Cloud access token
const client = new WeatherLayersClient.Client({
  accessToken: 'xxx',
});
```

A valid access token is required to use the library. Sign up at [WeatherLayers Account](https://account.weatherlayers.com/) to get your access token.

### Production Usage

[Contact support](mailto:support@weatherlayers.com) to upgrade your access token for a production usage.
