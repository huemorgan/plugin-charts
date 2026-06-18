# plugin-charts

Interactive [Chart.js](https://www.chartjs.org/) charts rendered inline in the
[Luna](https://github.com/huemorgan/luna) chat — line, bar, pie, doughnut,
radar, and scatter. Dark-themed, responsive, animated, with hover tooltips.

This is a **Luna plugin** built against the Luna Plugin SDK (`luna_sdk`) v0. It
imports nothing from `luna.*` — only the stable SDK surface — so it installs
from the Luna marketplace and runs without being part of Luna core.

## Install

In Luna: **Marketplace → Luna Official → plugin-charts → Install**.

## What it does

Exposes a single tool, `render_chart`, that the agent calls to draw a chart from
labels + datasets. The chart is returned as a self-contained HTML/JS widget the
chat renders inline.

```
render_chart(
  chart_type="bar",                 # line | bar | pie | doughnut | radar | scatter
  labels=["Jan", "Feb", "Mar"],
  datasets=[{"label": "Revenue", "data": [10, 20, 15]}],
  title="Q1 Revenue",
)
```

## Layout

```
plugin_charts/
  __init__.py        # the plugin (luna_sdk only)
  renderer.py        # Chart.js HTML generation (pure stdlib)
  luna-plugin.toml   # the data manifest the marketplace reads
```

## License

MIT — see [LICENSE](./LICENSE).
