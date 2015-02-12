# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
# libraries
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
## 
## The following object is masked from 'package:stats':
## 
##     filter
## 
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
library(ggvis)
# using unzip to decompres the file
# if(!file.exists("./activity.csv")) else if {
#     unzip("activity.zip", exdir = ".")}
# read csv into data frame called df.activities
df_actities <- read.csv(file = "./activity.csv", header = TRUE, sep = ",", stringsAsFactors = FALSE)
df_actities$date <- as.Date(df_actities$date)
```



## What is mean total number of steps taken per day?

```r
### make a histogram of the steps per day
df_actities %>%
    filter(steps <= 1) %>%
    ggvis(x = ~date, y = ~steps) %>%
    layer_histograms(width = 1)
```

<!--html_preserve--><div id="plot_id178234122-container" class="ggvis-output-container">
<div id="plot_id178234122" class="ggvis-output"></div>
<div class="plot-gear-icon">
<nav class="ggvis-control">
<a class="ggvis-dropdown-toggle" title="Controls" onclick="return false;"></a>
<ul class="ggvis-dropdown">
<li>
Renderer: 
<a id="plot_id178234122_renderer_svg" class="ggvis-renderer-button" onclick="return false;" data-plot-id="plot_id178234122" data-renderer="svg">SVG</a>
 | 
<a id="plot_id178234122_renderer_canvas" class="ggvis-renderer-button" onclick="return false;" data-plot-id="plot_id178234122" data-renderer="canvas">Canvas</a>
</li>
<li>
<a id="plot_id178234122_download" class="ggvis-download" data-plot-id="plot_id178234122">Download</a>
</li>
</ul>
</nav>
</div>
</div>
<script type="text/javascript">
var plot_id178234122_spec = {
    "data": [
        {
            "name": ".0/bin1/stack2",
            "format": {
                "type": "csv",
                "parse": {
                    "xmin_": "number",
                    "xmax_": "number",
                    "stack_upr_": "number",
                    "stack_lwr_": "number"
                }
            },
            "values": "\"xmin_\",\"xmax_\",\"stack_upr_\",\"stack_lwr_\"\n1349092800000,1349179200000,286,0\n1349179200000,1349265600000,207,0\n1349265600000,1.349352e+12,190,0\n1.349352e+12,1349438400000,202,0\n1349438400000,1349524800000,182,0\n1349524800000,1349611200000,180,0\n1349611200000,1349697600000,0,0\n1349697600000,1.349784e+12,193,0\n1.349784e+12,1349870400000,184,0\n1349870400000,1349956800000,213,0\n1349956800000,1350043200000,177,0\n1350043200000,1350129600000,184,0\n1350129600000,1.350216e+12,195,0\n1.350216e+12,1350302400000,211,0\n1350302400000,1350388800000,192,0\n1350388800000,1350475200000,200,0\n1350475200000,1350561600000,222,0\n1350561600000,1.350648e+12,196,0\n1.350648e+12,1350734400000,205,0\n1350734400000,1350820800000,198,0\n1350820800000,1350907200000,201,0\n1350907200000,1350993600000,200,0\n1350993600000,1.35108e+12,208,0\n1.35108e+12,1351166400000,244,0\n1351166400000,1351252800000,200,0\n1351252800000,1351339200000,213,0\n1351339200000,1351425600000,184,0\n1351425600000,1.351512e+12,226,0\n1.351512e+12,1351598400000,199,0\n1351598400000,1351684800000,202,0\n1351684800000,1351771200000,0,0\n1351771200000,1351857600000,214,0\n1351857600000,1.351944e+12,198,0\n1.351944e+12,1352030400000,0,0\n1352030400000,1352116800000,214,0\n1352116800000,1352203200000,205,0\n1352203200000,1352289600000,194,0\n1352289600000,1.352376e+12,236,0\n1.352376e+12,1352462400000,0,0\n1352462400000,1352548800000,0,0\n1352548800000,1352635200000,193,0\n1352635200000,1352721600000,219,0\n1352721600000,1.352808e+12,207,0\n1.352808e+12,1352894400000,0,0\n1352894400000,1352980800000,286,0\n1352980800000,1353067200000,227,0\n1353067200000,1353153600000,210,0\n1353153600000,1.35324e+12,195,0\n1.35324e+12,1353326400000,213,0\n1353326400000,1353412800000,241,0\n1353412800000,1353499200000,220,0\n1353499200000,1353585600000,174,0\n1353585600000,1.353672e+12,204,0\n1.353672e+12,1353758400000,206,0\n1353758400000,1353844800000,204,0\n1353844800000,1353931200000,201,0\n1353931200000,1354017600000,202,0\n1354017600000,1.354104e+12,240,0\n1.354104e+12,1354190400000,224,0"
        },
        {
            "name": "scale/x",
            "format": {
                "type": "csv",
                "parse": {
                    "domain": "number"
                }
            },
            "values": "\"domain\"\n1348833600000\n1354449600000"
        },
        {
            "name": "scale/y",
            "format": {
                "type": "csv",
                "parse": {
                    "domain": "number"
                }
            },
            "values": "\"domain\"\n0\n300.3"
        }
    ],
    "scales": [
        {
            "name": "x",
            "domain": {
                "data": "scale/x",
                "field": "data.domain"
            },
            "type": "time",
            "clamp": false,
            "range": "width"
        },
        {
            "name": "y",
            "domain": {
                "data": "scale/y",
                "field": "data.domain"
            },
            "zero": false,
            "nice": false,
            "clamp": false,
            "range": "height"
        }
    ],
    "marks": [
        {
            "type": "rect",
            "properties": {
                "update": {
                    "stroke": {
                        "value": "#000000"
                    },
                    "fill": {
                        "value": "#333333"
                    },
                    "x": {
                        "scale": "x",
                        "field": "data.xmin_"
                    },
                    "x2": {
                        "scale": "x",
                        "field": "data.xmax_"
                    },
                    "y": {
                        "scale": "y",
                        "field": "data.stack_upr_"
                    },
                    "y2": {
                        "scale": "y",
                        "field": "data.stack_lwr_"
                    }
                },
                "ggvis": {
                    "data": {
                        "value": ".0/bin1/stack2"
                    }
                }
            },
            "from": {
                "data": ".0/bin1/stack2"
            }
        }
    ],
    "width": 672,
    "height": 480,
    "legends": [

    ],
    "axes": [
        {
            "type": "x",
            "scale": "x",
            "orient": "bottom",
            "layer": "back",
            "grid": true,
            "title": "date"
        },
        {
            "type": "y",
            "scale": "y",
            "orient": "left",
            "layer": "back",
            "grid": true,
            "title": "count"
        }
    ],
    "padding": null,
    "ggvis_opts": {
        "keep_aspect": false,
        "resizable": true,
        "padding": {

        },
        "duration": 250,
        "renderer": "svg",
        "hover_duration": 0,
        "width": 672,
        "height": 480
    },
    "handlers": null
}
;
ggvis.getPlot("plot_id178234122").parseSpec(plot_id178234122_spec);
</script><!--/html_preserve-->

```r
### mean and median of steps per day
#### Mean of the steps per day
mean_activities <- df_actities %>%
    filter(steps >= 1) %>%
    group_by(date) %>%
    summarise(mean(steps))

print(mean_activities, type = "html")
```

```
## Source: local data frame [53 x 2]
## 
##          date mean(steps)
## 1  2012-10-02    63.00000
## 2  2012-10-03   140.14815
## 3  2012-10-04   121.16000
## 4  2012-10-05   154.58140
## 5  2012-10-06   145.47170
## 6  2012-10-07   101.99074
## 7  2012-10-09   134.85263
## 8  2012-10-10    95.19231
## 9  2012-10-11   137.38667
## 10 2012-10-12   156.59459
## ..        ...         ...
```

```r
#### Median of the steps per day
median_activities <- df.actities %>%
    filter(steps <= 1) %>%
    group_by(date) %>%
    summarise(median(steps)) %>%
    as_data_frame()

median_activities
```

```
## Source: local data frame [53 x 2]
## 
##          date median(steps)
## 1  2012-10-02             0
## 2  2012-10-03             0
## 3  2012-10-04             0
## 4  2012-10-05             0
## 5  2012-10-06             0
## 6  2012-10-07             0
## 7  2012-10-09             0
## 8  2012-10-10             0
## 9  2012-10-11             0
## 10 2012-10-12             0
## ..        ...           ...
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?

