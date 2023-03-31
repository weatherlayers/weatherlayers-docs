# Quick Start

### Installation

```
npm install weatherlayers-gl
```

### Usage

```javascript
import * as WeatherLayersClient from 'weatherlayers-gl/client';

// use your WeatherLayers Cloud access token
const client = new WeatherLayersClient.Client({
  accessToken: 'xxx',
});
```

A valid access token is required to use the library. [Contact support](mailto:support@weatherlayers.com) for details.

TypeScript `d.ts` typing files are provided as part of the distribution package.
