---
title: "Using GIS for invasive species research"
author: "Anthony Davidson"
date: "2019-09-05"
knit: bookdown::render_book
site: bookdown::bookdown_site
documentclass: krantz
monofont: "Source Code Pro"
monofontoptions: "Scale=0.7"
bibliography: [book.bib]
biblio-style: apalike
link-citations: yes
github-repo: davan690/Creating-maps-in-R
url: 'https\://ssnhub.com/Creating-maps-in-R/'
description: "Everything you need to start using GIS in RMarkdown/bookdown projects."
cover-image: "images/cover.png"
colorlinks: yes
graphics: yes
---

# Overview {#overview}

This respository contains a collection of dynamic programming tools and introductory tutorials for dealing with maps and geo-spatical analysis using `rmarkdown and shiny`.

## Project objectives

The overall objective is to create a landing page and collection of GIS work in R. All the examples will focus on invasive species dynamics. The current goals that also meet the requirements to produce the figures needed for reproducible phd research.

### Objective one

*Produce **static-maps** for the first publication of my PhD.*

| Draft here | [Davidson2019a](https://www.ssnhub.com/beech-publication-wr/summary.html) |
|------------|---------------------------------------------------------------------------|
|            |                                                                           |

#### Datasets

  - Grid locations are in a `kmz` file called "invasive-species-location-research.kmz" [here](data/google-data/invasive-species-location-research.kmz)
    - `kml` file still called "invasive-species-location-research.kmz" [currently](data/google-data/invasive-species-location-research.kmz)
  - Outline of NZ here "" [here]()
  - Forest vegetation here "" [here]()
  - Data from landCare 2019 publication here "" [here]()

- Rcode
  - My attempt so far "" [here]()
  - GIS cheat "" [here]()
  - Powerpoint cheat "" [here]()

- Static maps
  - NZ beech forest dynamics "" [here]()
  - 8 grids full data "" [here]()
  - only 6 used "" [here]()
  - South Island of NZ "" [here]()

Two: *Produce static maps for the following data-set* [Davidson2019b]

[*same as above*]

Three: *Produce static maps for the following data-set* [Davidson2019c]

[*same as above*]

## My notes

- Vignettes
  - Creating maps in R "www.ssnhub.com/creating-maps-in-r.html"
  - Map for Chapter 2: Beech forests ""

- Examples
  - LandCare 2019 publication here ""

## Get started...

1. Fork this repo [here](www.github.com/davan690/Creating-maps-in-R/)

2. Pull project into Rstudio using version control.

   ![1567561101782](img/fork.PNG)

3. Ensure that your local RStudio packages are up to date.

For more details this following the same contributing options as the website instructions [here](https://www.ssnhub.com/contributing/).

**Note** This book is built from the absolute minimum you need to start a  [bookdown](https://bookdown.org/yihui/bookdown/) book. You can find the preview of the unmodified template of the book at http://seankross.com/bookdown-start/

- All of the content of this repository is licensed [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

The content of the mapping/GIS was orginally forked from from the following `github` repositories:

- [Creating maps in R](https://geocompr.robinlovelace.net/): A textbook on geocomputational analysis in R

### Packages

To run this book in RStudio the following packages are needed.

- [tidyverse]()
- [MapView](https://r-spatial.github.io/mapview/): a 3D interactive R packages
- [Video](https://www.youtube.com/watch?v=GMi1ThlGFMo)


```r
library(spData)
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
library(sf)
```

```
## Linking to GEOS 3.6.1, GDAL 2.2.3, PROJ 4.9.3
```

```r
library(bookdown)
library(leaflet)
library(leaflet.extras)
library(geojsonio)
```

```
## 
## Attaching package: 'geojsonio'
```

```
## The following object is masked from 'package:base':
## 
##     pretty
```
