# Grid layer

Variable rendered as grid of values or symbols (arrows, wind barbs)

### Example

```javascript
import { Deck } from '@deck.gl/core';
import * as WeatherLayers from '@weatherlayers/weatherlayers-gl';

// load custom self-hosted data
const image = { data: new Float32Array(...), width: ..., height: ... };

const deckgl = new Deck({
  layers: [
    new WeatherLayers.GridLayer({
      image: image,
    }),
  ],
});
```

### Data properties

[Data properties](../data.md#data-properties) are common for all layers in the standalone bundle.

### Style properties

#### `style`

Type: enum `WeatherLayers.GridStyle`, values: `VALUE`, `ARROW`, `WIND_BARB`, optional

Default: `VALUE`

Style of the grid points, values or symbols (arrows, wind barbs).

#### `textFunction`

Type: function `(value: number) => string`, optional

Default: `(value) => Math.round(value).toString()`

Function to format the value.

#### `textFontFamily`

Type: string, optional

Default: `"Helvetica Neue", Arial, Helvetica, sans-serif`

Font family of the text. See [TextLayer fontFamily](https://deck.gl/docs/api-reference/layers/text-layer#fontfamily).

#### `textSize`

Type: number, optional

Default: `12`

Size of the text. See [TextLayer getSize](https://deck.gl/docs/api-reference/layers/text-layer#getsize).

#### `textColor`

Type: color `[number, number, number, number?]`, optional

Default: `[153, 153, 153, 255]`

Color of the text. See [TextLayer getColor](https://deck.gl/docs/api-reference/layers/text-layer#getcolor).

#### `textOutlineWidth`

Type: number, optional

Default: `1`

Width of outline around the text, relative to the font size. See [TextLayer outlineWidth](https://deck.gl/docs/api-reference/layers/text-layer#outlinewidth).

#### `textOutlineColor`

Type: color `[number, number, number, number?]`, optional

Default: `[13, 13, 13, 255]`

Color of outline around the text. See [TextLayer outlineColor](https://deck.gl/docs/api-reference/layers/text-layer#outlinecolor).

#### `iconSize`

Type: number, optional

Default: `12`

Size of the icon. See [IconLayer getSize](https://deck.gl/docs/api-reference/layers/icon-layer#getsize).

#### `iconColor`

Type: color `[number, number, number, number?]`, optional

Default: `[255, 255, 255, 102]`

Color of the icon. See [IconLayer getColor](https://deck.gl/docs/api-reference/layers/icon-layer#getcolor).

#### `opacity`

Type: number, optional

Default: `1`

The opacity of the layer. See [Layer opacity](https://deck.gl/docs/api-reference/core/layer#opacity).