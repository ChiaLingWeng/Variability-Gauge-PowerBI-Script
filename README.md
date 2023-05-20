# Variability-Gauge-in-PowerBI
![Alt Text](https://github.com/ChiaLingWeng/Variability-Gauge-PowerBI-Script/blob/main/demo.gif)

We can draw a nested scatter plot easily using Python, R or JMP.
But since PowerBI server support none of the above method, we may use [Deneb](https://deneb-viz.github.io/) instead

You may use variability_chart.pbix directly to get the deneb plug-in.

# [Vega-Lite](https://vega.github.io/vega-lite/docs/facet.html) languages
### Here are some basic operators / properties, you must follow the correct format
### import PowerBI source 
```
    "data": {
        "name": "dataset"
    }
```

### Top-level View Specification: Avoid entering same config format repeatedly
```
{
  ...,
  "config": { // Configuration Object

    "view": { // - View Configuration

      // View Size
      "continuousWidth": ...,
      "continuousHeight": ...,
      "discreteWidth": ...,
      "discreteHeight": ...,
      // View Background Properties
      "fill": ...,
      "stroke": ...,
      ...
    },
    ...
  }
}
```
### Nested Chart: "facet" and "spec":{"facet","spec":...}
```
            "facet": {
                "column": {
                    "field": "A"
                },
            },
            "spec": {
                "facet": {
                    "column": {
                        "field": "B"
                    }
                },
                "spec": {
                    "layer": [
                        {
                            "mark": {
                                "type": "point",
                                "tooltip": true
                            }
                        }
                    ]
                }
            }
```
