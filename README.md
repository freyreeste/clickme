# Clickme

**Clickme** is an R package that lets you create interactive visualizations in the browser, directly from your R session.

That means you can minimize your use of boring static plots.

## Install

Just run this in R to install Clickme:

```S
install.packages("devtools") # you don't need to run this command if you already have the devtools package installed.

devtools::install_github("clickme", "nachocab")
```

If there is a new Clickme version a few days later, you can update by simply re-running that last command.

## Examples

Let's take it out for a spin.

```S
library(clickme)
clickme(points, rnorm(100)) # try zooming in and out, click the Show names button, hover over points
```

A more interesting example
```S
data(microarray)
clickme(points, x = microarray$significance, y = microarray$logFC,
        color_groups = ifelse(microarray$adj.P.Val < 1e-4, "Significant", "Noise"),
        names = microarray$gene_name,
        x_title = "Significance (-log10)", y_title = "Fold-change (log2)",
        extra = list(Probe = microarray$probe_name))
```


## Resources

* [Points template parameters](http://rclickme.com/clickme/user_manual/points.html)
* Developer guide (coming soon)

## Acknowledgements
Thank you **Mike Bostock**. Making the [D3.js](http://d3js.org) library more accessible was my strongest motivation for developing Clickme.

Thank you **Yihui Xie**. The [knitr](https://github.com/yihui/knitr) R package has shown me the importance of building bridges across technologies, while also turning my scientific ramblings into reproducible work.

Thank you **Hadley Wickam**. The [testthat](https://github.com/hadley/test_that) R package has been consistently saving my butt since I started coding for a living.

There are other fine people trying to move visualization to the browser. Check out [rCharts](http://rcharts.io/) by Ramnath Vaidyanathan.
