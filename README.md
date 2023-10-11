
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
    - [Static Maps](#static-maps)
    - [Webmap](#webmap)
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

![Fig 1&2](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig1-2.png)
*Fig. 1 (left): VS Code screenshot of the text file as downloaded from Mangani's Bigfoot Maps* | *Fig. 2 (right): VS Code screenshot of the final CSV file database.*


### Other Data
2022 United States county and state boundaries were obtained from the [United States Census Bureau website](https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html). After adding geometries, joining the Bigfoot sightings data per state/county, and normalizing it per area, these are the final datasets:
* [2022-us-state-add-geo-bfro.zip](https://github.com/alexmunozviso/map671-fp/blob/main/data/2022-us-state-add-geo-bfro.zip)
* [2022-us-county-add-geo-bfro.zip](https://github.com/alexmunozviso/map671-fp/blob/main/data/2022-us-county-add-geo-bfro.zip)

## Tools Used
* [Visual Studio Code](https://code.visualstudio.com) was used to create the Bigfoot Sighting Database.
* [QGIS](https://www.qgis.org) was used to geoprocess, analyze, and represent the geodata for this project. The static maps were also exported using QGIS layouts.
* Data is shown on [Mapbox](https://www.mapbox.com/) web map. If the map got popular it would require a fee to use.
* [Adobe Illustrator](https://www.adobe.com/products/illustrator) was used to edit the Bigfoot miniatures used as map symbols and as part of the website's graphics.

## Mapmaking Process
### Static Maps
The static maps were all created using QGIS. The CRS was set to ESRI: 102008 (North America Albers Equal Area Conic), as it is a standard projected coordinate system for mapping the contiguous United States. 

First, I imported the CSV containing the Bigfoot sightings database as delimited text using the Data Source Manager (see Fig. 3). The data was then imported to QGIS as a point data layer. Then, I imported the  shapefiles downloaded from the US Census Bureau containing state and county boundaries. 

![Fig 3](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig3copia.png)
*Fig. 3: Thanks to setting the appropriate field names and data organization (see Fig. 2), the CSV file can be imported as a point layer by matching X,Y values with the lon,lat fields in the CSV.*

Using the Vector geoprocessing tool 'Clip', I extracted those Bigfoot sightings within my database that happened in the contiguous United States. I did so by clipping the Bigfoot database the extent of one of the shapefiles obtained from the US Census Bureau. 

![Fig 4](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig4.png)
*Fig. 4: On the left side you can see the values given to the 'Clip' tool. On the right side you can see the geoprocessing result. The brown points are the original imported data and the red ones are the resulting clipped ones.*

After getting area information for my state/counties shapefiles using the 'Add geometry attributes' tool, I calculated a new field in their attribute table converting the 'Area' field (which is calculated in square meters) to square kilometers to ease future field calculations.

The following step was to create a field containing unique values for each of the three layers so they can be joined later. I calculated a new field called 'Id' and filled with unique values (1,2,3,4,5,...) using the expression *$Id* in the field calculator expression box.

Using these fields, 

![Fig 5](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig4.png)
*Fig. 5: 'Id' field calculation.*

### Webmap

# Final Project Link

Please view the website for my final project [following this link](www.github...).
