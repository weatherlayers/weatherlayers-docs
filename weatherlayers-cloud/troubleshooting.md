# Troubleshooting

### TypeScript integration can't find WeatherLayers Client typings

#### Issue

WeatherLayers Client typings are exported as a separate export with `exports` syntax.

```typescript
  "exports": {
    ".": {
      "require": "./dist/weatherlayers-deck.min.cjs",
      "import": "./dist/weatherlayers-deck.min.js",
      "script": "./dist/weatherlayers-deck.umd.min.js",
      "types": "./dist/weatherlayers-deck.d.ts"
    },
    "./client": {
      "require": "./dist/weatherlayers-client.min.cjs",
      "import": "./dist/weatherlayers-client.min.js",
      "script": "./dist/weatherlayers-client.umd.min.js",
      "types": "./dist/weatherlayers-client.d.ts"
    }
  },
```

#### Symptoms

After `deck.MapboxOverlay` is added to the map with `maplibregl.Map.addControl` and removed from the map with `maplibregl.Map.removeControl`, adding it back again with `maplibregl.Map.addControl` doesn't render any layers.

#### Solution

After removing `deck.MapboxOverlay` from the map with `maplibregl.Map.removeControl`, remove layers as well with `deck.MapboxOverlay.setProps({ layers: [] })`.

After adding `deck.MapboxOverlay` to the map with `maplibregl.Map.addControl`, add layers with `deck.MapboxOverlay.setProps({ layers: [...all layers...] })`.
