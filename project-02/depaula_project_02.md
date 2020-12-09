---
title: "Mini-Project 02"
output: 
  html_document:
    keep_md: true
    toc: true
    toc_float: true
---

# Data Visualization Project 02


```r
library(tidyverse)
```

```
## -- Attaching packages --------------------------------------------------------------------------------------- tidyverse 1.3.0 --
```

```
## v ggplot2 3.3.2     v purrr   0.3.4
## v tibble  3.0.3     v dplyr   1.0.2
## v tidyr   1.1.2     v stringr 1.4.0
## v readr   1.3.1     v forcats 0.5.0
```

```
## Warning: package 'ggplot2' was built under R version 4.0.3
```

```
## -- Conflicts ------------------------------------------------------------------------------------------ tidyverse_conflicts() --
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
library(plotly)
```

```
## Warning: package 'plotly' was built under R version 4.0.3
```

```
## 
## Attaching package: 'plotly'
```

```
## The following object is masked from 'package:ggplot2':
## 
##     last_plot
```

```
## The following object is masked from 'package:stats':
## 
##     filter
```

```
## The following object is masked from 'package:graphics':
## 
##     layout
```

```r
library(maps)
```

```
## Warning: package 'maps' was built under R version 4.0.3
```

```
## 
## Attaching package: 'maps'
```

```
## The following object is masked from 'package:purrr':
## 
##     map
```

```r
library(GGally)
```

```
## Warning: package 'GGally' was built under R version 4.0.3
```

```
## Registered S3 method overwritten by 'GGally':
##   method from   
##   +.gg   ggplot2
```

```r
cb_palette <- c("#88CCEE", "#CC6677", "#DDCC77", "#117733", "#332288", "#AA4499", 
                             "#44AA99", "#999933", "#882255", "#661100", "#6699CC", "#888888", "#000000")
marathon_2017 <- read.csv('../data/marathon_results_2017.csv')
```




```r
ggplotly(marathon_2017 %>% 
  filter(Gender < 101 & M.F == 'M') %>% 
  ggplot(aes(x = Gender, y = Age), alpha = 1) +
  geom_point(aes(color = Country), shape = 21) +
  scale_color_manual(values = cb_palette) +
  theme_classic()) %>% 
  layout(legend = list(orientation = 'h', y = -0.3)) %>% 
  layout(title='Age and Position on Male Marathon 2017', xaxis = list(title ='Position'))
```

<!--html_preserve--><div id="htmlwidget-562da80376443c96d387" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-562da80376443c96d387">{"x":{"data":[{"x":[32],"y":[45],"text":"Country: BRA<br />Gender:  32<br />Age: 45","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(136,204,238,1)"}},"hoveron":"points","name":"BRA","legendgroup":"BRA","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[37,63,66,83,89],"y":[34,33,30,30,36],"text":["Country: CAN<br />Gender:  37<br />Age: 34","Country: CAN<br />Gender:  63<br />Age: 33","Country: CAN<br />Gender:  66<br />Age: 30","Country: CAN<br />Gender:  83<br />Age: 30","Country: CAN<br />Gender:  89<br />Age: 36"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(204,102,119,1)"}},"hoveron":"points","name":"CAN","legendgroup":"CAN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[8,12],"y":[28,32],"text":["Country: ETH<br />Gender:   8<br />Age: 28","Country: ETH<br />Gender:  12<br />Age: 32"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(221,204,119,1)"}},"hoveron":"points","name":"ETH","legendgroup":"ETH","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[77],"y":[36],"text":"Country: GBR<br />Gender:  77<br />Age: 36","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(17,119,51,1)"}},"hoveron":"points","name":"GBR","legendgroup":"GBR","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[95,100],"y":[40,30],"text":["Country: GER<br />Gender:  95<br />Age: 40","Country: GER<br />Gender: 100<br />Age: 30"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(51,34,136,1)"}},"hoveron":"points","name":"GER","legendgroup":"GER","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[62],"y":[41],"text":"Country: IRL<br />Gender:  62<br />Age: 41","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(170,68,153,1)"}},"hoveron":"points","name":"IRL","legendgroup":"IRL","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[51],"y":[48],"text":"Country: ITA<br />Gender:  51<br />Age: 48","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(68,170,153,1)"}},"hoveron":"points","name":"ITA","legendgroup":"ITA","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[3,39,50,94],"y":[25,19,23,22],"text":["Country: JPN<br />Gender:   3<br />Age: 25","Country: JPN<br />Gender:  39<br />Age: 19","Country: JPN<br />Gender:  50<br />Age: 23","Country: JPN<br />Gender:  94<br />Age: 22"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(153,153,51,1)"}},"hoveron":"points","name":"JPN","legendgroup":"JPN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,5,15,18],"y":[24,31,34,32],"text":["Country: KEN<br />Gender:   1<br />Age: 24","Country: KEN<br />Gender:   5<br />Age: 31","Country: KEN<br />Gender:  15<br />Age: 34","Country: KEN<br />Gender:  18<br />Age: 32"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(136,34,85,1)"}},"hoveron":"points","name":"KEN","legendgroup":"KEN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[21,67],"y":[42,29],"text":["Country: MEX<br />Gender:  21<br />Age: 42","Country: MEX<br />Gender:  67<br />Age: 29"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(102,17,0,1)"}},"hoveron":"points","name":"MEX","legendgroup":"MEX","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[53],"y":[41],"text":"Country: NED<br />Gender:  53<br />Age: 41","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(102,153,204,1)"}},"hoveron":"points","name":"NED","legendgroup":"NED","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[2,4,6,7,9,10,11,13,16,17,19,20,22,23,24,25,26,27,28,29,30,31,33,34,35,36,38,40,41,42,43,44,45,46,47,48,49,52,54,55,56,57,58,59,60,61,64,65,68,69,70,71,72,73,74,75,76,78,79,80,81,82,84,85,86,87,88,90,91,92,93,96,97,98,99],"y":[30,32,40,33,27,28,32,41,32,41,29,29,30,31,36,28,28,39,25,29,37,36,26,40,27,35,32,43,31,30,24,32,37,25,35,26,27,37,28,29,41,28,21,27,31,22,36,30,25,23,40,32,31,25,25,20,32,28,30,30,32,31,45,26,39,25,33,26,39,36,24,26,30,28,23],"text":["Country: USA<br />Gender:   2<br />Age: 30","Country: USA<br />Gender:   4<br />Age: 32","Country: USA<br />Gender:   6<br />Age: 40","Country: USA<br />Gender:   7<br />Age: 33","Country: USA<br />Gender:   9<br />Age: 27","Country: USA<br />Gender:  10<br />Age: 28","Country: USA<br />Gender:  11<br />Age: 32","Country: USA<br />Gender:  13<br />Age: 41","Country: USA<br />Gender:  16<br />Age: 32","Country: USA<br />Gender:  17<br />Age: 41","Country: USA<br />Gender:  19<br />Age: 29","Country: USA<br />Gender:  20<br />Age: 29","Country: USA<br />Gender:  22<br />Age: 30","Country: USA<br />Gender:  23<br />Age: 31","Country: USA<br />Gender:  24<br />Age: 36","Country: USA<br />Gender:  25<br />Age: 28","Country: USA<br />Gender:  26<br />Age: 28","Country: USA<br />Gender:  27<br />Age: 39","Country: USA<br />Gender:  28<br />Age: 25","Country: USA<br />Gender:  29<br />Age: 29","Country: USA<br />Gender:  30<br />Age: 37","Country: USA<br />Gender:  31<br />Age: 36","Country: USA<br />Gender:  33<br />Age: 26","Country: USA<br />Gender:  34<br />Age: 40","Country: USA<br />Gender:  35<br />Age: 27","Country: USA<br />Gender:  36<br />Age: 35","Country: USA<br />Gender:  38<br />Age: 32","Country: USA<br />Gender:  40<br />Age: 43","Country: USA<br />Gender:  41<br />Age: 31","Country: USA<br />Gender:  42<br />Age: 30","Country: USA<br />Gender:  43<br />Age: 24","Country: USA<br />Gender:  44<br />Age: 32","Country: USA<br />Gender:  45<br />Age: 37","Country: USA<br />Gender:  46<br />Age: 25","Country: USA<br />Gender:  47<br />Age: 35","Country: USA<br />Gender:  48<br />Age: 26","Country: USA<br />Gender:  49<br />Age: 27","Country: USA<br />Gender:  52<br />Age: 37","Country: USA<br />Gender:  54<br />Age: 28","Country: USA<br />Gender:  55<br />Age: 29","Country: USA<br />Gender:  56<br />Age: 41","Country: USA<br />Gender:  57<br />Age: 28","Country: USA<br />Gender:  58<br />Age: 21","Country: USA<br />Gender:  59<br />Age: 27","Country: USA<br />Gender:  60<br />Age: 31","Country: USA<br />Gender:  61<br />Age: 22","Country: USA<br />Gender:  64<br />Age: 36","Country: USA<br />Gender:  65<br />Age: 30","Country: USA<br />Gender:  68<br />Age: 25","Country: USA<br />Gender:  69<br />Age: 23","Country: USA<br />Gender:  70<br />Age: 40","Country: USA<br />Gender:  71<br />Age: 32","Country: USA<br />Gender:  72<br />Age: 31","Country: USA<br />Gender:  73<br />Age: 25","Country: USA<br />Gender:  74<br />Age: 25","Country: USA<br />Gender:  75<br />Age: 20","Country: USA<br />Gender:  76<br />Age: 32","Country: USA<br />Gender:  78<br />Age: 28","Country: USA<br />Gender:  79<br />Age: 30","Country: USA<br />Gender:  80<br />Age: 30","Country: USA<br />Gender:  81<br />Age: 32","Country: USA<br />Gender:  82<br />Age: 31","Country: USA<br />Gender:  84<br />Age: 45","Country: USA<br />Gender:  85<br />Age: 26","Country: USA<br />Gender:  86<br />Age: 39","Country: USA<br />Gender:  87<br />Age: 25","Country: USA<br />Gender:  88<br />Age: 33","Country: USA<br />Gender:  90<br />Age: 26","Country: USA<br />Gender:  91<br />Age: 39","Country: USA<br />Gender:  92<br />Age: 36","Country: USA<br />Gender:  93<br />Age: 24","Country: USA<br />Gender:  96<br />Age: 26","Country: USA<br />Gender:  97<br />Age: 30","Country: USA<br />Gender:  98<br />Age: 28","Country: USA<br />Gender:  99<br />Age: 23"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(136,136,136,1)"}},"hoveron":"points","name":"USA","legendgroup":"USA","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[14],"y":[34],"text":"Country: ZIM<br />Gender:  14<br />Age: 34","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"hoveron":"points","name":"ZIM","legendgroup":"ZIM","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":37.2602739726027},"plot_bgcolor":"rgba(255,255,255,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-3.95,104.95],"tickmode":"array","ticktext":["0","25","50","75","100"],"tickvals":[-4.44089209850063e-16,25,50,75,100],"categoryorder":"array","categoryarray":["0","25","50","75","100"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":true,"linecolor":"rgba(0,0,0,1)","linewidth":0.66417600664176,"showgrid":false,"gridcolor":null,"gridwidth":0,"zeroline":false,"anchor":"y","title":"Position","hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[17.55,49.45],"tickmode":"array","ticktext":["20","30","40"],"tickvals":[20,30,40],"categoryorder":"array","categoryarray":["20","30","40"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":true,"linecolor":"rgba(0,0,0,1)","linewidth":0.66417600664176,"showgrid":false,"gridcolor":null,"gridwidth":0,"zeroline":false,"anchor":"x","title":{"text":"Age","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":true,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895},"y":-0.3,"orientation":"h"},"annotations":[{"text":"Country","x":1.02,"y":1,"showarrow":false,"ax":0,"ay":0,"font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xref":"paper","yref":"paper","textangle":-0,"xanchor":"left","yanchor":"bottom","legendTitle":true}],"hovermode":"closest","barmode":"relative","title":"Age and Position on Male Marathon 2017"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"45dc679ccbe":{"colour":{},"x":{},"y":{},"type":"scatter"}},"cur_data":"45dc679ccbe","visdat":{"45dc679ccbe":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

```r
ggplotly(marathon_2017 %>% 
  filter(Gender < 101 & M.F == 'F') %>% 
  ggplot(aes(x = Gender, y = Age), alpha = 1) +
  geom_point(aes(color = Country), shape = 21) +
  scale_color_manual(values = cb_palette) +
  theme_classic()) %>% 
  layout(legend = list(orientation = 'h', y = -0.3)) %>% 
  layout(title='Age and Position on Female Marathon 2017', xaxis = list(title ='Position'))
```

<!--html_preserve--><div id="htmlwidget-edbfbd8bc9d89731c7b7" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-edbfbd8bc9d89731c7b7">{"x":{"data":[{"x":[59,95,98],"y":[47,37,36],"text":["Country: AUS<br />Gender:  59<br />Age: 47","Country: AUS<br />Gender:  95<br />Age: 37","Country: AUS<br />Gender:  98<br />Age: 36"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(136,204,238,1)"}},"hoveron":"points","name":"AUS","legendgroup":"AUS","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[9],"y":[32],"text":"Country: BDI<br />Gender:   9<br />Age: 32","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(204,102,119,1)"}},"hoveron":"points","name":"BDI","legendgroup":"BDI","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[2],"y":[27],"text":"Country: BRN<br />Gender:   2<br />Age: 27","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(221,204,119,1)"}},"hoveron":"points","name":"BRN","legendgroup":"BRN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[23,29,47,91,97],"y":[30,33,40,43,50],"text":["Country: CAN<br />Gender:  23<br />Age: 30","Country: CAN<br />Gender:  29<br />Age: 33","Country: CAN<br />Gender:  47<br />Age: 40","Country: CAN<br />Gender:  91<br />Age: 43","Country: CAN<br />Gender:  97<br />Age: 50"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(17,119,51,1)"}},"hoveron":"points","name":"CAN","legendgroup":"CAN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[55],"y":[29],"text":"Country: ESP<br />Gender:  55<br />Age: 29","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(51,34,136,1)"}},"hoveron":"points","name":"ESP","legendgroup":"ESP","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[7,10,22],"y":[29,23,30],"text":["Country: ETH<br />Gender:   7<br />Age: 29","Country: ETH<br />Gender:  10<br />Age: 23","Country: ETH<br />Gender:  22<br />Age: 30"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(170,68,153,1)"}},"hoveron":"points","name":"ETH","legendgroup":"ETH","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[50],"y":[26],"text":"Country: GBR<br />Gender:  50<br />Age: 26","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(68,170,153,1)"}},"hoveron":"points","name":"GBR","legendgroup":"GBR","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[32],"y":[25],"text":"Country: GER<br />Gender:  32<br />Age: 25","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(153,153,51,1)"}},"hoveron":"points","name":"GER","legendgroup":"GER","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[25,65],"y":[25,28],"text":["Country: JPN<br />Gender:  25<br />Age: 25","Country: JPN<br />Gender:  65<br />Age: 28"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(136,34,85,1)"}},"hoveron":"points","name":"JPN","legendgroup":"JPN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,5,6,8],"y":[37,33,24,23],"text":["Country: KEN<br />Gender:   1<br />Age: 37","Country: KEN<br />Gender:   5<br />Age: 33","Country: KEN<br />Gender:   6<br />Age: 24","Country: KEN<br />Gender:   8<br />Age: 23"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(102,17,0,1)"}},"hoveron":"points","name":"KEN","legendgroup":"KEN","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[76],"y":[26],"text":"Country: MEX<br />Gender:  76<br />Age: 26","type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(102,153,204,1)"}},"hoveron":"points","name":"MEX","legendgroup":"MEX","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[3,4,11,12,13,14,15,16,17,18,19,20,21,24,26,27,28,30,31,33,34,35,36,37,38,39,40,41,42,43,44,45,46,48,49,51,52,53,54,56,57,58,60,61,62,63,64,66,67,68,69,70,71,72,73,74,75,77,78,79,80,81,82,83,84,85,86,87,88,89,90,92,93,94,96,99,100],"y":[25,33,26,30,30,40,32,39,33,29,28,29,40,41,24,36,41,34,34,30,28,26,26,34,30,27,30,26,25,26,30,27,29,31,35,29,33,42,38,27,33,28,33,42,29,26,37,31,33,23,33,39,27,26,26,29,29,50,26,28,26,27,37,31,24,30,30,27,42,39,34,25,40,46,32,34,30],"text":["Country: USA<br />Gender:   3<br />Age: 25","Country: USA<br />Gender:   4<br />Age: 33","Country: USA<br />Gender:  11<br />Age: 26","Country: USA<br />Gender:  12<br />Age: 30","Country: USA<br />Gender:  13<br />Age: 30","Country: USA<br />Gender:  14<br />Age: 40","Country: USA<br />Gender:  15<br />Age: 32","Country: USA<br />Gender:  16<br />Age: 39","Country: USA<br />Gender:  17<br />Age: 33","Country: USA<br />Gender:  18<br />Age: 29","Country: USA<br />Gender:  19<br />Age: 28","Country: USA<br />Gender:  20<br />Age: 29","Country: USA<br />Gender:  21<br />Age: 40","Country: USA<br />Gender:  24<br />Age: 41","Country: USA<br />Gender:  26<br />Age: 24","Country: USA<br />Gender:  27<br />Age: 36","Country: USA<br />Gender:  28<br />Age: 41","Country: USA<br />Gender:  30<br />Age: 34","Country: USA<br />Gender:  31<br />Age: 34","Country: USA<br />Gender:  33<br />Age: 30","Country: USA<br />Gender:  34<br />Age: 28","Country: USA<br />Gender:  35<br />Age: 26","Country: USA<br />Gender:  36<br />Age: 26","Country: USA<br />Gender:  37<br />Age: 34","Country: USA<br />Gender:  38<br />Age: 30","Country: USA<br />Gender:  39<br />Age: 27","Country: USA<br />Gender:  40<br />Age: 30","Country: USA<br />Gender:  41<br />Age: 26","Country: USA<br />Gender:  42<br />Age: 25","Country: USA<br />Gender:  43<br />Age: 26","Country: USA<br />Gender:  44<br />Age: 30","Country: USA<br />Gender:  45<br />Age: 27","Country: USA<br />Gender:  46<br />Age: 29","Country: USA<br />Gender:  48<br />Age: 31","Country: USA<br />Gender:  49<br />Age: 35","Country: USA<br />Gender:  51<br />Age: 29","Country: USA<br />Gender:  52<br />Age: 33","Country: USA<br />Gender:  53<br />Age: 42","Country: USA<br />Gender:  54<br />Age: 38","Country: USA<br />Gender:  56<br />Age: 27","Country: USA<br />Gender:  57<br />Age: 33","Country: USA<br />Gender:  58<br />Age: 28","Country: USA<br />Gender:  60<br />Age: 33","Country: USA<br />Gender:  61<br />Age: 42","Country: USA<br />Gender:  62<br />Age: 29","Country: USA<br />Gender:  63<br />Age: 26","Country: USA<br />Gender:  64<br />Age: 37","Country: USA<br />Gender:  66<br />Age: 31","Country: USA<br />Gender:  67<br />Age: 33","Country: USA<br />Gender:  68<br />Age: 23","Country: USA<br />Gender:  69<br />Age: 33","Country: USA<br />Gender:  70<br />Age: 39","Country: USA<br />Gender:  71<br />Age: 27","Country: USA<br />Gender:  72<br />Age: 26","Country: USA<br />Gender:  73<br />Age: 26","Country: USA<br />Gender:  74<br />Age: 29","Country: USA<br />Gender:  75<br />Age: 29","Country: USA<br />Gender:  77<br />Age: 50","Country: USA<br />Gender:  78<br />Age: 26","Country: USA<br />Gender:  79<br />Age: 28","Country: USA<br />Gender:  80<br />Age: 26","Country: USA<br />Gender:  81<br />Age: 27","Country: USA<br />Gender:  82<br />Age: 37","Country: USA<br />Gender:  83<br />Age: 31","Country: USA<br />Gender:  84<br />Age: 24","Country: USA<br />Gender:  85<br />Age: 30","Country: USA<br />Gender:  86<br />Age: 30","Country: USA<br />Gender:  87<br />Age: 27","Country: USA<br />Gender:  88<br />Age: 42","Country: USA<br />Gender:  89<br />Age: 39","Country: USA<br />Gender:  90<br />Age: 34","Country: USA<br />Gender:  92<br />Age: 25","Country: USA<br />Gender:  93<br />Age: 40","Country: USA<br />Gender:  94<br />Age: 46","Country: USA<br />Gender:  96<br />Age: 32","Country: USA<br />Gender:  99<br />Age: 34","Country: USA<br />Gender: 100<br />Age: 30"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"transparent","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(136,136,136,1)"}},"hoveron":"points","name":"USA","legendgroup":"USA","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":37.2602739726027},"plot_bgcolor":"rgba(255,255,255,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-3.95,104.95],"tickmode":"array","ticktext":["0","25","50","75","100"],"tickvals":[-4.44089209850063e-16,25,50,75,100],"categoryorder":"array","categoryarray":["0","25","50","75","100"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":true,"linecolor":"rgba(0,0,0,1)","linewidth":0.66417600664176,"showgrid":false,"gridcolor":null,"gridwidth":0,"zeroline":false,"anchor":"y","title":"Position","hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[21.65,51.35],"tickmode":"array","ticktext":["30","40","50"],"tickvals":[30,40,50],"categoryorder":"array","categoryarray":["30","40","50"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":true,"linecolor":"rgba(0,0,0,1)","linewidth":0.66417600664176,"showgrid":false,"gridcolor":null,"gridwidth":0,"zeroline":false,"anchor":"x","title":{"text":"Age","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":true,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895},"y":-0.3,"orientation":"h"},"annotations":[{"text":"Country","x":1.02,"y":1,"showarrow":false,"ax":0,"ay":0,"font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xref":"paper","yref":"paper","textangle":-0,"xanchor":"left","yanchor":"bottom","legendTitle":true}],"hovermode":"closest","barmode":"relative","title":"Age and Position on Female Marathon 2017"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"45dc29535c88":{"colour":{},"x":{},"y":{},"type":"scatter"}},"cur_data":"45dc29535c88","visdat":{"45dc29535c88":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

```r
marathon_2017 %>% 
  filter(Gender < 101) %>%
  spread(M.F, Gender) %>% 
  plot_ly() %>%
  add_trace(
    type = 'scatter',
    mode = 'lines+markers',
    x = ~M,
    y = ~Pace,
    text = ~Name,
    name = "Male"
  ) %>%
  add_trace(
    type = 'scatter',
    mode = 'lines+markers',
    x = ~F,
    y = ~Pace,
    text = ~Name,
    name = "Female"
  ) %>% 
  layout(title='Pace comparison between male and female first 100 positions on marathon 2017', xaxis = list(title ='Position'))
```

```
## Warning: `arrange_()` is deprecated as of dplyr 0.7.0.
## Please use `arrange()` instead.
## See vignette('programming') for more help
## This warning is displayed once every 8 hours.
## Call `lifecycle::last_warnings()` to see where this warning was generated.
```

<!--html_preserve--><div id="htmlwidget-7f7c11eb778297a94360" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-7f7c11eb778297a94360">{"x":{"visdat":{"45dc38c7396":["function () ","plotlyVisDat"]},"cur_data":"45dc38c7396","attrs":{"45dc38c7396":{"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"scatter","mode":"lines+markers","x":{},"y":{},"text":{},"name":"Male","inherit":true},"45dc38c7396.1":{"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"scatter","mode":"lines+markers","x":{},"y":{},"text":{},"name":"Female","inherit":true}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"title":"Pace comparison between male and female first 100 positions on marathon 2017","xaxis":{"domain":[0,1],"automargin":true,"title":"Position"},"yaxis":{"domain":[0,1],"automargin":true,"title":"Pace","type":"category","categoryorder":"array","categoryarray":["0:04:57","0:04:58","0:04:59","0:05:03","0:05:04","0:05:05","0:05:08","0:05:09","0:05:11","0:05:14","0:05:16","0:05:17","0:05:18","0:05:20","0:05:21","0:05:22","0:05:25","0:05:26","0:05:27","0:05:28","0:05:29","0:05:30","0:05:31","0:05:32","0:05:33","0:05:34","0:05:35","0:05:36","0:05:37","0:05:38","0:05:39","0:05:40","0:05:41","0:05:43","0:05:44","0:05:45","0:05:46","0:05:47","0:05:48","0:05:49","0:05:50","0:05:51","0:05:52","0:05:53","0:05:54","0:05:55","0:05:56","0:05:57","0:05:58","0:05:59","0:06:01","0:06:03","0:06:04","0:06:07","0:06:10","0:06:12","0:06:14","0:06:15","0:06:16","0:06:20","0:06:21","0:06:23","0:06:24","0:06:25","0:06:27","0:06:29","0:06:30","0:06:34","0:06:35","0:06:36","0:06:37","0:06:38","0:06:39","0:06:41","0:06:42","0:06:43","0:06:44","0:06:45","0:06:46","0:06:47","0:06:48","0:06:49","0:06:50","0:06:51","0:06:52","0:06:53","0:06:54","0:06:55"]},"hovermode":"closest","showlegend":true},"source":"A","config":{"showSendToCloud":false},"data":[{"type":"scatter","mode":"lines+markers","x":[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,null,21,22,null,23,24,25,26,27,28,29,30,null,31,32,33,34,35,36,37,38,39,null,40,41,42,43,44,45,46,47,48,null,49,50,51,52,53,54,55,56,null,57,58,59,60,61,62,null,63,64,65,66,null,67,68,69,70,71,72,73,74,75,null,76,77,78,79,80,81,82,83,84,null,85,86,null,87,88,89,90,91,92,93,94,95,96,97,null,98,99,100],"y":["0:04:57","0:04:58","0:04:59","0:05:03","0:05:04","0:05:04","0:05:05","0:05:08","0:05:09","0:05:11","0:05:11","0:05:14","0:05:14","0:05:16","0:05:17","0:05:17","0:05:18","0:05:20","0:05:21","0:05:22",null,"0:05:26","0:05:27",null,"0:05:28","0:05:28","0:05:29","0:05:30","0:05:31","0:05:32","0:05:32","0:05:32",null,"0:05:33","0:05:33","0:05:34","0:05:35","0:05:36","0:05:36","0:05:37","0:05:37","0:05:37",null,"0:05:38","0:05:38","0:05:39","0:05:40","0:05:40","0:05:41","0:05:41","0:05:41","0:05:41",null,"0:05:43","0:05:44","0:05:44","0:05:44","0:05:45","0:05:45","0:05:45","0:05:45",null,"0:05:46","0:05:46","0:05:47","0:05:47","0:05:47","0:05:47",null,"0:05:48","0:05:48","0:05:49","0:05:49",null,"0:05:49","0:05:49","0:05:50","0:05:50","0:05:50","0:05:51","0:05:51","0:05:51","0:05:51",null,"0:05:52","0:05:52","0:05:53","0:05:53","0:05:53","0:05:53","0:05:54","0:05:54","0:05:54",null,"0:05:55","0:05:55",null,"0:05:55","0:05:56","0:05:56","0:05:57","0:05:57","0:05:57","0:05:57","0:05:57","0:05:57","0:05:58","0:05:58",null,"0:05:58","0:05:58","0:05:58"],"text":["Kirui, Geoffrey","Rupp, Galen","Osako, Suguru","Biwott, Shadrack","Chebet, Wilson","Abdirahman, Abdi","Maiyo, Augustus K.","Sefir, Dino","Puskedra, Luke","Ward, Jared","Quigley, Sean","Tsegay, Yemane","Keflezighi, Meb","Nyasango, Cutbert","Korir, Wesley","Puzey, Thomas R.","Kisri, Rachid","Mutai, Emmanuel","Ndhlovu, Pardon","Harvey, Brian",null,"Chipsiya, Christopher K.","Mindel, Scott",null,"Place, Ryan J","Humphrey, Luke","Ashe, Eric","Thompson, Christian C.","Maravilla, Jorge","Ornelas, Zachary","Ayr, Jason M.","Morgan, Mike",null,"Pierce, Keith","Martins, Cesar A.","Vangampleare, Stephen","Loeffler, Eric","Carpenter, Joseph K.","Fransen, Bret","Puzey, Jacob","Kotter, Jonathan B.","Iwasa, Kaito",null,"Wardian, Michael R.","Flaherty, Matthew A.","Mckay, David","Fischer, Matthew","Reaves, Patrick","Varela, Jonnathan","Tropf, Jordan","Bromka, Peter","Bishop, Daniel",null,"Aguila, Nick","Ohashi, Shinya","Boudalia, Said Sr.","Taylor, Alexander J.","Veldhuis, Jeroen","Chichester, Tim","O'Leary, Paddy C","Wells, Clint",null,"Zablocki, Christopher A.","Gray, Samuel R.","Gilmore, Peter","Fallas Navarro, Juan R.","Thomas, Jason","Whitty, Fergal M.",null,"Chiasson, Rejean","Skurka, Andrew","Turner, Wesley C","Trimaille, Johan",null,"Arias Navarro, Aroon H.","Ash, Alan","Remillard, Charles A.","Krieg, Sam D","Neill, Ian","Clark, Sean","Ellenberger, Michael P","Klecker, Jack R","Retzlaff, Chris",null,"Kinley, Jordan","Ashford, Christopher A","Macdonald, Adrian S.","Jones, Mark T","Metzger, David W","Trammell, Chadwick D.","Varner, Alexander","Parrott, John","Vanos, William",null,"Wysong, Jeff","Blas, Wayne",null,"Kuchwara, Sam N.","Roach, Adam D","Stone, Chris C.","Cox, Ryan","Nurse, Ian","Byers, Scott E","Kirk, Jacob D","Kai, Hiroki","Freudenberger, Holger U. III","Wimmer, Nicholas","Thor, Matthew",null,"Klein, Patrick J","Roche, Nicholas N.","Grosskopf, Johannes S."],"name":"Male","marker":{"color":"rgba(31,119,180,1)","line":{"color":"rgba(31,119,180,1)"}},"error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"line":{"color":"rgba(31,119,180,1)"},"xaxis":"x","yaxis":"y","frame":null},{"type":"scatter","mode":"lines+markers","x":[1,null,2,3,null,4,null,5,null,6,null,7,null,8,null,9,null,10,null,11,null,12,null,13,null,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,78,79,80,81,82,83,84,85,86,87,88,89,90,91,92,93,94,95,96,97,98,99,100],"y":["0:05:25",null,"0:05:27","0:05:28",null,"0:05:33",null,"0:05:38",null,"0:05:43",null,"0:05:46",null,"0:05:48",null,"0:05:49",null,"0:05:52",null,"0:05:55",null,"0:05:55",null,"0:05:58",null,"0:05:59","0:05:59","0:05:59","0:06:01","0:06:03","0:06:04","0:06:04","0:06:07","0:06:07","0:06:10","0:06:12","0:06:14","0:06:15","0:06:16","0:06:20","0:06:20","0:06:21","0:06:23","0:06:24","0:06:24","0:06:25","0:06:25","0:06:27","0:06:27","0:06:29","0:06:30","0:06:30","0:06:34","0:06:35","0:06:35","0:06:36","0:06:37","0:06:37","0:06:38","0:06:39","0:06:39","0:06:41","0:06:41","0:06:42","0:06:42","0:06:43","0:06:43","0:06:43","0:06:44","0:06:44","0:06:44","0:06:45","0:06:45","0:06:45","0:06:45","0:06:46","0:06:46","0:06:46","0:06:46","0:06:47","0:06:47","0:06:47","0:06:47","0:06:47","0:06:47","0:06:47","0:06:47","0:06:48","0:06:48","0:06:49","0:06:49","0:06:49","0:06:50","0:06:50","0:06:50","0:06:50","0:06:50","0:06:50","0:06:51","0:06:51","0:06:51","0:06:51","0:06:52","0:06:52","0:06:53","0:06:53","0:06:53","0:06:53","0:06:53","0:06:53","0:06:54","0:06:55"],"text":["Kiplagat, Edna",null,"Chelimo, Rose","Hasay, Jordan",null,"Linden, Desiree",null,"Cherono, Gladys",null,"Kipketer, Valentine",null,"Deba, Buzunesh",null,"Kosgei, Brigid",null,"Nukuri, Diane",null,"Aga, Ruti",null,"Flanagan, Lindsey",null,"Herrick, Danna",null,"Atkins, Esther",null,"McMahan, Dot","McWalters, Teresa","Groner, Roberta","Dimoff, Carrie","Costello, Liz","Duhon, Madeline","Philbrook, Lauren","Landau, Kate","Baysa, Atsede","Hannah, Rachel","Corno, Hilary","Kurosawa, Kana","Gibson, Audrey L.","Begay, Alvina Y.","Stucky, Raquel","Doucet, Shelley A","Phillips, Caitlin","Andre, Stephanie","Gill, Nadine","Bernardi, Alexandra E.","Quinn, Julianne","Ryan, Elizabeth","Davis, Rachel","Colligan, Nora","Jackson, Veronica M","Wiberley, Kelsey L.","Vest, Jamie","Coogan, Rachel","Anderson, Mallory E","Allan, Kirsten N","Tateishi, Caitlyn Claire","Nolan, Alison L","Arthur, D'Ann E","Lovig, Christy L.","Gress, Shannon","Lair, Jessie E","Walsh, Sorrell","Van Meter, Kathryn M.","Lizotte, Megan L.","Hein, Christine L.","Hurlbutt, Gretchen G","Bel Franquesa, Laura","Delong, Candace","Jablonski, Karen","Paulsen, Laura C.","Glasson, Rachel","Sabadosa, Apryl","Marshall, Wendy","Miller, Joyce R","Miura, Rachel","Rouse, Gina","Ishikawa, Natsuko","Schiemann, Katie M.","Pugmire, Heidi B.","Skatteboe, Karoline","Liu, Ziyang","Kaskalla, Tana","Rouillard, Molly","Moraczewski, Katie","Crowe, Heather","Jaswell, Megan","Swierzbinski, Elizabeth A","Quintero, Margarita","Schmidt, Heidi H","Hansen, Laura K","Donohue, Danielle M.","Sceats-Basil, Rochelle A.","Strong, Kayla","Cueno, Nicole","Lowry, Cristina","Doney, Blair J","Mack, Carrie O","Kruszka, Andrea M","Konderwich, Allison R.","Schulz, Heather","Farrell, Amy C","Hannon, Elizabeth","Switt, Angela H","Gaal, Ildiko M.","Dunn, Karen L","Bayliss, Jennifer A.","Sansonetti, Danielle","Yang, Carolyn","Keating, Paula M","Brown, Rebecca","Petrosky, Kristi M","Mckinney, Janell M."],"name":"Female","marker":{"color":"rgba(255,127,14,1)","line":{"color":"rgba(255,127,14,1)"}},"error_y":{"color":"rgba(255,127,14,1)"},"error_x":{"color":"rgba(255,127,14,1)"},"line":{"color":"rgba(255,127,14,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

```r
marathon_2017 %>% 
  select(Overall, Gender, Age) %>% 
  ggpairs()
```

![](lastname_project_02_files/figure-html/unnamed-chunk-6-1.png)<!-- -->


```r
countries <- read.csv('../data/countries.csv')
WorldData <- map_data('world') %>% filter(region != "Antarctica") %>% fortify

spread_countries <- countries %>% 
  spread(alpha3, name)
spread_countries <- spread_countries[,3:ncol(spread_countries)]
spread_countries <- gather(spread_countries) %>% 
  group_by(key) %>% 
  subset(!is.na(value)) %>% 
  mutate(key = toupper(key)) %>% 
  spread(key, value)
spread_countries
```

```
## # A tibble: 1 x 193
##   AFG    AGO   ALB   AND   ARE   ARG   ARM   ATG   AUS   AUT   AZE   BDI   BEL  
##   <chr>  <chr> <chr> <chr> <chr> <chr> <chr> <chr> <chr> <chr> <chr> <chr> <chr>
## 1 Afgha~ Ango~ Alba~ Ando~ Unit~ Arge~ Arme~ Anti~ Aust~ Aust~ Azer~ Buru~ Belg~
## # ... with 180 more variables: BEN <chr>, BFA <chr>, BGD <chr>, BGR <chr>,
## #   BHR <chr>, BHS <chr>, BIH <chr>, BLR <chr>, BLZ <chr>, BOL <chr>,
## #   BRA <chr>, BRB <chr>, BRN <chr>, BTN <chr>, BWA <chr>, CAF <chr>,
## #   CAN <chr>, CHE <chr>, CHL <chr>, CHN <chr>, CIV <chr>, CMR <chr>,
## #   COD <chr>, COG <chr>, COL <chr>, COM <chr>, CPV <chr>, CRI <chr>,
## #   CUB <chr>, CYP <chr>, CZE <chr>, DEU <chr>, DJI <chr>, DMA <chr>,
## #   DNK <chr>, DOM <chr>, DZA <chr>, ECU <chr>, EGY <chr>, ERI <chr>,
## #   ESP <chr>, EST <chr>, ETH <chr>, FIN <chr>, FJI <chr>, FRA <chr>,
## #   FSM <chr>, GAB <chr>, GBR <chr>, GEO <chr>, GHA <chr>, GIN <chr>,
## #   GMB <chr>, GNB <chr>, GNQ <chr>, GRC <chr>, GRD <chr>, GTM <chr>,
## #   GUY <chr>, HND <chr>, HRV <chr>, HTI <chr>, HUN <chr>, IDN <chr>,
## #   IND <chr>, IRL <chr>, IRN <chr>, IRQ <chr>, ISL <chr>, ISR <chr>,
## #   ITA <chr>, JAM <chr>, JOR <chr>, JPN <chr>, KAZ <chr>, KEN <chr>,
## #   KGZ <chr>, KHM <chr>, KIR <chr>, KNA <chr>, KOR <chr>, KWT <chr>,
## #   LAO <chr>, LBN <chr>, LBR <chr>, LBY <chr>, LCA <chr>, LIE <chr>,
## #   LKA <chr>, LSO <chr>, LTU <chr>, LUX <chr>, LVA <chr>, MAR <chr>,
## #   MCO <chr>, MDA <chr>, MDG <chr>, MDV <chr>, MEX <chr>, MHL <chr>, ...
```

```r
ggplot() +
    geom_map(data = WorldData, map = WorldData,
                  aes(x = long, y = lat, group = group, map_id=region),
                  fill = "white", colour = "#7f7f7f", size=0.5)  + 
    geom_map(data = marathon_2017, map=WorldData,
                  aes(fill=Gender, map_id=City),
                  colour="#7f7f7f", size=0.5) +
    coord_map("rectangular", lat0=0, xlim=c(-180,180), ylim=c(-60, 90)) + 
    theme_bw() +
    ggtitle("Athletes by country") +
    labs(fill = "Number of athletes", x = '', y = '')
```

```
## Warning: Ignoring unknown aesthetics: x, y
```

![](lastname_project_02_files/figure-html/unnamed-chunk-8-1.png)<!-- -->


