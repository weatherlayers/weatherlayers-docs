# Troubleshooting

### Mapbox & MapLibre integration can't be enabled after disabling

#### Issue

Layers can't be reused, they need to be recreated.

#### Symptoms

After `deck.MapboxOverlay` is added to the map with `maplibregl.Map.addControl` and removed from the map with `maplibregl.Map.removeControl`, adding it back again with `maplibregl.Map.addControl` doesn't render any layers.

#### Solution

After removing `deck.MapboxOverlay` from the map with `maplibregl.Map.removeControl`, remove layers as well with `deck.MapboxOverlay.setProps({ layers: [] })`.

After adding `deck.MapboxOverlay` to the map with `maplibregl.Map.addControl`, add layers with `deck.MapboxOverlay.setProps({ layers: [...all layers...] })`.
