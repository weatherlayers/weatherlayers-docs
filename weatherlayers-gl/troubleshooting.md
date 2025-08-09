# Troubleshooting

### deck.gl shader hooks are not resolved

#### Issue

deck.gl must be used from a single bundle, otherwise it fails to resolve its shader hooks `DECKGL_FILTER_SIZE`, `DECKGL_FILTER_GL_POSITION`, `DECKGL_FILTER_COLOR`.

The shader source code calls these hooks but it's missing their declaration.

#### Symptoms

No layer displays. "Vertex shader is not compiled" error is logged in the browser console.

#### Solution

Check for duplicate deck.gl bundles used (versions or ESM vs CJS). Ensure that a single deck.gl bundle is used.

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

HighLowLayer uses deck.gl CollisionFilterExtension, which has a known unresolved bug that it can't be used after bitmap layers (RasterLayer, ContourLayer). [https://github.com/visgl/deck.gl/issues/7864](https://github.com/visgl/deck.gl/issues/7864)

#### Symptoms

HighLowLayer doesn't display.

#### Solution

Move HighLowLayer to be before bitmap layers (RasterLayer, ContourLayer), and offset it with `getPolygonOffset: () => [0, -1000]`.
