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

The trial access token is valid for 30 days. After the trial period, the pricing is pricing is a flat fee of 300 EUR or 360 USD / year for one application. The application is defined by the production domain, includes unlimited amount of development or test domains.
