# regl-scatter2d [![experimental](https://img.shields.io/badge/stability-unstable-green.svg)](http://github.com/badges/stability-badges)

Scatter plot for lots of points.

Remake on [gl-scatter2d](https://github.com/gl-vis/gl-scatter2d), covering other scatter-related components.

## Usage

[![npm install regl-scatter2d](https://nodei.co/npm/regl-scatter2d.png?mini=true)](https://npmjs.org/package/regl-scatter2d/)

```js
let scatter = require('regl-scatter2d')({
	positions: data,
	color: 'rgba(0, 100, 200, .75)'
})

scatter()
```

## API

#### `drawScatter = require('regl-scatter2d')(options)`

| Property | Default | Description |
|---|---|---|
| `regl` | `null` | Regl instance to reuse, otherwise new regl is created. |
| `gl`, `canvas`, `container` | `null` | Options for `regl`, if new regl is created. |

The rest of options is passed into `drawScatter` method.

#### `drawScatter(positions|options?)`

Redraw scatter. Takes over new options.

| Property | Default | Description |
|---|---|---|
| `positions`, `points` | `[]` | An array of the unrolled xy coordinates of the points, as `[x,y, x,y, ...]` or array of points `[[x,y], [x,y], ...]`. |
| `size` | `12` | Number or array with marker sizes in pixels. Array length should correspond to `positions`. |
| `color`, `colors` | `'red'` | Color or array with colors. Each color can be a css-color string or an array with float `0..1` values. If `palette` is defined, `color` can be a number pointing at the color in the palette. |
| `borderSize` | `1` | Number or array with border sizes in pixels. Array length should correspond to `positions`. |
| `borderColor`, `borderColors` | `'black'` | Border color or array with border colors. If `palette` is defined, `borderColor` can be a number pointing at the color in the palette. |
| `palette` | `null` | List of basic colors, for example `['red', 'green', 'blue', 'black']`. |
| `marker`, `markers` | `null` | Define marker shape. Can be a string with UTF character to render, and svg path string, ImageData/canvas with SDF-field or array with any of these, corresponding to points. If `null`, circular marker is used. |
| `range`, `dataBox` | `null` | Data bounds limiting visible data as `[left, top, right, bottom]`. If `null`, the range is detected from the positions. |
| `precision` | `'low'` | Psition precision, `'high'` or `'low'`. Tradeoff between max number of points and rendering performance. |

## License

(c) 2017 Dima Yv. MIT License

Development supported by plot.ly.
