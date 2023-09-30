# Troubleshooting

### Layers can't be enabled after disabling in MapLibre/Mapbox interleaved mode

#### Issue

Layers can't be reused, they need to be recreated.

#### Symptoms

After `deck.MapboxOverlay` is added to the map with `maplibregl.Map.addControl` and removed from the map with `maplibregl.Map.removeControl`, adding it back again with `maplibregl.Map.addControl` doesn't render any layers.

#### Solution

After removing `deck.MapboxOverlay` from the map with `maplibregl.Map.removeControl`, remove layers as well with `deck.MapboxOverlay.setProps({ layers: [] })`.

After adding `deck.MapboxOverlay` to the map with `maplibregl.Map.addControl`, add layers with `deck.MapboxOverlay.setProps({ layers: [...all layers...] })`.

### HighLowLayer doesn't display in MapLibre/Mapbox interleaved mode

#### Issue

HighLowLayer uses deck.gl CollisionFilterExtension, which has an unresolved bug that it can't be used after bitmap layers (RasterLayer, ContourLayer). [https://github.com/visgl/deck.gl/issues/7864](https://github.com/visgl/deck.gl/issues/7864)

#### Symptoms

HighLowLayer doesn't display.

#### Solution

Move HighLowLayer to be before bitmap layers (RasterLayer, ContourLayer), and offset it with `getPolygonOffset: () => [0, -1000]`.
