# Style properties

Style properties common for all layers.

#### `visible`

Type: boolean, optional

Default: true

Visibility of the layer. See [Layer visible](https://deck.gl/docs/api-reference/core/layer#visible).

#### `opacity`

Type: number, optional

Default: `1`

Opacity of the layer. See [Layer opacity](https://deck.gl/docs/api-reference/core/layer#opacity).

#### `extensions`

Type: array of extensions

Use `[new ClipExtension()]` for a global image in an equirectangular projection on a [WebMercatorViewport](https://deck.gl/docs/api-reference/core/web-mercator-viewport), to clip the areas of the image beyond a valid Mercator bounding box. See [ClipExtension](https://deck.gl/docs/api-reference/extensions/clip-extension).

#### `clipBounds`

Type: bounding box of minX, minY, maxX, maxY `[number, number, number, number]`, required for `ClipExtension`

Recommended value is `[-181, -85.051129, 181, 85.051129]` for a global image in an equirectangular projection on a [WebMercatorViewport](https://deck.gl/docs/api-reference/core/web-mercator-viewport), to clip the areas of the image beyond a valid Mercator bounding box. There is `181` instead of `180` to avoid a pixel gap at the antimeridian. See [ClipExtension.clipBounds](https://deck.gl/docs/api-reference/extensions/clip-extension#clipbounds).
