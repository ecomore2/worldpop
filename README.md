
<!-- README.md is generated from README.Rmd. Please edit that file -->

# WorldPop

<!-- badges: start -->

<!-- badges: end -->

Raw raster files data (**100-m resolution**) are downloaded from
[WorldPop](https://www.worldpop.org) and are cropped by the polygon of
the province of Vientiane prefecture that is dowloaded from
[GADM](https://gadm.org). Data are not projected
([EPSG](http://www.epsg.org):[4326](https://epsg.io/4326)), with
coordinates expressed in decimal degrees. Adjusted population sizes are
corrected so that the total population size in the raster corresponds to
the UN country estimate. All the details are in the [cleaning
pipeline](https://ecomore2.github.io/worldpop/make_data.html).

Cleaned data can be downloaded as follows:

  - [Population](https://www.worldpop.org/geodata/summary?id=61)
        data:
      - [VT\_popmap10\_admin001.tif](https://www.dropbox.com/s/b1byouuilije6ly/VT_popmap10_admin001.tif?raw=1)
        (2.1
        MB)
      - [VT\_popmap10adj\_admin001.tif](https://www.dropbox.com/s/9ottfpf34oznywx/VT_popmap10adj_admin001.tif?raw=1)
        (2.1
        MB)
      - [VT\_popmap15\_admin001.tif](https://www.dropbox.com/s/kc8rq5mh6tq2sxk/VT_popmap15_admin001.tif?raw=1)
        (2.1
        MB)
      - [VT\_popmap15adj\_admin001.tif](https://www.dropbox.com/s/snthubnbx2i4en5/VT_popmap15adj_admin001.tif?raw=1)
        (2.1 MB)
  - [Urban change](https://www.worldpop.org/geodata/summary?id=1228)
    data:
      - [VT00urbchg.tif](https://www.dropbox.com/s/wdl4mqvod5w0x2t/VT00urbchg.tif?raw=1)
        (342
        KB)
      - [VT10urbchg.tif](https://www.dropbox.com/s/n8hqh2vs6b72fmi/VT10urbchg.tif?raw=1)
        (343 KB)

These raster can be loaded directly in R as so:

``` r
library(raster)
tmp <- tempfile(fileext = ".tif")
download.file("https://www.dropbox.com/s/b1byouuilije6ly/VT_popmap10_admin001.tif?raw=1", tmp)
VT_popmap10 <- raster(tmp)
download.file("https://www.dropbox.com/s/9ottfpf34oznywx/VT_popmap10adj_admin001.tif?raw=1", tmp)
VT_popmap10adj <- raster(tmp)
download.file("https://www.dropbox.com/s/kc8rq5mh6tq2sxk/VT_popmap15_admin001.tif?raw=1", tmp)
VT_popmap15 <- raster(tmp)
download.file("https://www.dropbox.com/s/snthubnbx2i4en5/VT_popmap15adj_admin001.tif?raw=1", tmp)
VT_popmap15adj <- raster(tmp)
download.file("https://www.dropbox.com/s/wdl4mqvod5w0x2t/VT00urbchg.tif?raw=1", tmp)
VT00urbchg <- raster(tmp)
download.file("https://www.dropbox.com/s/n8hqh2vs6b72fmi/VT10urbchg.tif?raw=1", tmp)
VT10urbchg <- raster(tmp)
```
