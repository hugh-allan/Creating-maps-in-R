# Diving In {#divingin}

There are plenty of github repositories explaining the different types of GIS and using R.

Below is the public `google-my-maps` map that can be modified an worked on from within the window provided below.

<iframe src="https://www.google.com.au/maps/d/u/0/embed?mid=1DAgemW-rkdMHTO8fxnbvbSVF4H0XNLd_" width="640" height="480"></iframe>
{: .box-note}
**Note:** This can currently me modified and changed by anyone with the link. As it comes more important for the dataset to not be modified by others we will tighten this process up using the leaflet and shiny app process we are using for the mapping and analysis at the bottom of this post.

So far we have saved a `leaflet` `rmd` file as an html file and pasted it from the includes folder of the website. We will tighten this up too. :)

## Downloading

To begin with check this is working in your local RStudio enviroment

1. Install the required packages. You need a recent version of the GDAL, GEOS, Proj.4, and UDUNITS libraries installed for this to work on Mac and Linux. More information on that at https://github.com/r-spatial/sf#installling.


```r
# devtools::install_github("robinlovelace/geocompr")
```

2. Load the ones we need:

- In addition, it uses the following visualization packages:


```r
library(tmap)    # for static and interactive maps
library(leaflet) # for interactive maps
library(mapview) # for interactive maps
library(ggplot2) # tidyverse data visualization package
library(shiny)   # for web applications
```


```r
library(spData)
library(dplyr)
library(sf)
library(bookdown)
library(leaflet)
library(leaflet.extras)
library(geojsonio)
```


```r
library(sf)
library(raster)
library(dplyr)
library(spData)
# library(spDataLarge)
```

3. Check it's all working, e.g. with this command:


```r
world %>%  
  plot()
```

<img src="02-Diving-In_files/figure-html/unnamed-chunk-3-1.png" width="672" />

And some blogging on the matter [here](http://zevross.com/blog/2014/09/30/use-the-amazing-d3-library-to-animate-a-path-on-a-leaflet-map/).



