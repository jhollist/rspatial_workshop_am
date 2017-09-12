# Packages
library(here)
library(sf)
library(raster)
library(dplyr)

# Load up the data
library(httr)
url <- "https://github.com/usepa/rspatial_workshop/blob/master/data/data.zip?raw=true"
GET(url,write_disk(here("data/data.zip"),overwrite = TRUE))

# Unzip the data
unzip(here("data/data.zip"), exdir = here("data"), overwrite = TRUE)

# Read in data
dc_metro <- st_read(here("data/Metro_Lines.shp"))
plot(st_geometry(dc_metro))
dc_metro_sttn <- st_read(here("data/metrostations.geojson"))
us_states <- st_read(here("data/tl_2015_us_state.shp"))
summary(us_states)
# Write a shapefile
st_write(dc_metro,here("data/dc_metro_new.shp"))

# Read in Raster data
dc_elev <- raster(here("data/dc_ned.tif"))

writeRaster(dc_elev,"dc_elev_example.tif", overwrite = T)

