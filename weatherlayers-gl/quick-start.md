# Quick Start

### Installation

```
npm install weatherlayers-gl
```

TypeScript `d.ts` typing files are provided as part of the distribution package.

### Trial Usage

```typescript
import * as WeatherLayers from 'weatherlayers-gl';
```

No license file is necessary to use the library for a trial.

A watermark is displayed when the library is deployed to a production domain. In order to remove the watermark, a valid license file is required.

### Production Usage

```javascript
import * as WeatherLayers from 'weatherlayers-gl';

// use your WeatherLayers GL license file
import license from './license.json';
WeatherLayers.setLicense(license);
```

A valid license file is required to use the library in production. [Contact support](mailto:support@weatherlayers.com) for details.

