
# Mapping Bigfoot Sightings in the Contiguous United States 

## Project Contents

- [Mapping Bigfoot Sightings in the Contiguous United States](#mapping-bigfoot-sightings-in-the-contiguous-united-states)
  - [Project Contents](#project-contents)
  - [Project Introduction](#project-introduction)
  - [Data Sources](#data-sources)
    - [Bigfoot Sightings Data](#bigfoot-sightings-data)
    - [Other Data](#other-data)
  - [Tools Used](#tools-used)
  - [Mapmaking Process](#mapmaking-process)
- [Final Project Link](#final-project-link)

***
## Project Introduction
For the final project of MAP671, I wanted to create a map representing curious data. Looking for different themes, I stumbled upon [The Bigfoot Field Research Organization (BFRO)](http://www.bfro.net), a website compiling different databases of Bigfoot encounters including sightings, audible sightings, trackmarks, or footprints. Every report included in these databases is geocoded and timestamped. 

I am not the 'I believe' type or really interested in conspiracy theories (more like in conspiracy theorists), but I thought it could be fun to map this data. Moreover, the BFRO accepts online submissions of Bigfoot sighting reports, which adds a certain sense of community data crowdsourcing and community mapping to their project; two research topics that are of great personal interest.

## Data Sources

### Bigfoot Sightings Data
My database of Bigfoot sightings was constructed using the summaries of data from [The Bigfoot Field Research Organization (BFRO)](http://www.bfro.net) elaborated by [Mangani's Bigfoot Maps](http://penn.freeservers.com/bigfootmaps/). From the latter's website, I downloaded a
[text file](http://www.penn.freeservers.com/bigfootmaps/BFROcreature.txt) containing the 2016 updated BFRO's creature sightings. This data includes only visual sightings of the Bigfoot and excludes records of audible sightings, trackmarks, or footprints. I converted the text file into a CSV file and edited it using [VS Code](https://code.visualstudio.com). I re-organized and arranged the attribute data file to keep contain latitude, longitude, date of the sighting, and a link to the BFRO's sighting report (see Fig. 1 & 2). My final CSV file contained 3209 geocoded and timestamped reports for the North American area. After clipping the database to the extent of the contiguous United States in QGIS, 3032 reports remained on my final database.

Here you can download the prime CSV file and the final version of the database as a GeoJSON:

* [bfro-creature-sightings.csv](https://github.com/alexmunozviso/map671-fp/blob/main/data/bfro-creature-sightings.csv)
* [us-clipped-bfro-creature-sightings.geojson](https://github.com/alexmunozviso/map671-fp/blob/main/data/us-clipped-bfro-creature-sightings.geojson)

![CSV screenshot](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig1.png)
*Fig. 1 (left): VS Code screenshot of the text file as downloaded from Mangani's Bigfoot Maps* | *Fig. 2 (right): VS Code screenshot of the final CSV file database*


### Other Data
2022 United States county and state boundaries were obtained from the [United States Census Bureau website](https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html). After adding geometries, joining the Bigfoot sightings data per state/county, and normalizing it per area, these are the final datasets:
* [2022-us-state-add-geo-bfro.zip](https://github.com/alexmunozviso/map671-fp/blob/main/data/2022-us-state-add-geo-bfro.zip)
* [2022-us-county-add-geo-bfro.zip](https://github.com/alexmunozviso/map671-fp/blob/main/data/2022-us-county-add-geo-bfro.zip)

## Tools Used
* [Visual Studio Code](https://code.visualstudio.com) was used to create the Bigfoot Sighting Database.
* [QGIS](https://www.qgis.org) was used to geoprocess, analyze, and represent the geodata for this project.
* Data is shown on [Mapbox](https://www.mapbox.com/) web map. If the map got popular it would require a fee to use.
* [Adobe Illustrator](https://www.adobe.com/products/illustrator) was used to edit the Bigfoot miniatures used as map symbols and as part of the website's graphics.

## Mapmaking Process


# Final Project Link

Please view the website for my final project [following this link](www.github...).
