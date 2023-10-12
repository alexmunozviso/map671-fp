
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

The decision to limit the map extent to the contiguous US was made to maintain a simpler map instead of including Alaska, Hawaii, and other extra-continental territories.

## Data Sources

### Bigfoot Sightings Data
My database of Bigfoot sightings was constructed using the summaries of data from [The Bigfoot Field Research Organization (BFRO)](http://www.bfro.net) elaborated by [Mangani's Bigfoot Maps](http://penn.freeservers.com/bigfootmaps/). From the latter's website, I downloaded a
[text file](http://www.penn.freeservers.com/bigfootmaps/BFROcreature.txt) containing the 2016 updated BFRO's creature sightings. This data includes only visual sightings of the Bigfoot and excludes records of audible sightings, trackmarks, or footprints. I converted the text file into a CSV file and edited it using [VS Code](https://code.visualstudio.com). I re-organized and arranged the attribute data file to keep contain latitude, longitude, date of the sighting, and a link to the BFRO's sighting report (see Fig. 1 & 2). My final CSV file contained 3209 geocoded and timestamped reports for the North American area. After clipping the database to the extent of the contiguous United States in QGIS, 3032 reports remained on my final database.

Here you can download the prime CSV file and the final version of the database as a GeoJSON:

* [bfro-creature-sightings.csv](https://github.com/alexmunozviso/map671-fp/blob/main/data/bfro-creature-sightings.csv)
* [us-clipped-bfro-creature-sightings.geojson](https://github.com/alexmunozviso/map671-fp/blob/main/data/us-clipped-bfro-creature-sightings.geojson)

![Figures 1&2](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig1-2.png)
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
All the maps discussed in this site can be accessed in the website for this project. See the link to the site at the [bottom of this README](#final-project-link).

### Static Maps
The static maps were all created using QGIS. The CRS was set to ESRI: 102008 (North America Albers Equal Area Conic), as it is a standard projected coordinate system for mapping the contiguous United States. 

First, I imported the CSV containing the Bigfoot sightings database as delimited text using the Data Source Manager (see Fig. 3). The data was then imported to QGIS as a point data layer. Then, I imported the  shapefiles downloaded from the US Census Bureau containing state and county boundaries. 

![Figure 3](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig3.png)
*Fig. 3: Thanks to setting the appropriate field names and data organization (see Fig. 2), the CSV file can be imported as a point layer by matching X,Y values with the lon,lat fields in the CSV.*

Using the Vector geoprocessing tool 'Clip', I extracted those Bigfoot sightings within my database that happened in the contiguous United States. I did so by clipping the Bigfoot database the extent of one of the shapefiles obtained from the US Census Bureau. 

![Figure 4](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig4.png)
*Fig. 4: On the left side you can see the values given to the 'Clip' tool. On the right side you can see the geoprocessing result. The brown points are the original imported data and the red ones are the resulting clipped ones.*

After getting area information for my state/counties shapefiles using the 'Add geometry attributes' tool, I calculated a new field in their attribute table converting the 'Area' field (which is calculated in square meters) to square kilometers to ease future field calculations.

The following step was to create a field containing unique values for each of the three layers so they can be joined later. I calculated a new field called 'Id' and filled with unique values (1,2,3,4,5,...) using the expression *$Id* in the field calculator expression box.

At this point, I considered that the processing of the Bigfoot sightings database was concluded. I exported it as a GeoJSON and made its CRS ESRI: 102008 (North America Albers Equal Area Conic).

Using the recently created 'Id' fields, it is possible to join the Bigfoot data to the state/county layers. The operation is done using the 'Join Attributes by Location (Summary)' tool. In Fig. 5 you can see the values given to the tool to produce a field containing the number of Bigfoot sightings per state/county.

![Figure 5](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig5.png)
*Fig. 5: View of the values given to the 'Join Attributes by Location (Summary)' tool for processing.*


The field obtained in the previous operation is not complete. The states/counties with no sightings reports appear as having *NULL* values. To change these for zeros, I operated the following expression in the field calculator (see also Fig. 6):

    if("Id_count" is null, 0, "Id_count")

![Figure 6](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig6.png)
*Fig. 6: Field calculation to replace NULL values with zeros. This operation can be also done by marking 'Update existing field' but I prefered to work on a new field for safety reasons; just in case something went wrong with the operation.*

Before moving on, I exported the US state data containing also the Bigfoot sightings data as a shapefile. I made its CRS ESRI: 102008 (North America Albers Equal Area Conic).

At this point, I was ready to create my first static map, which shows the amount of Bigfoot sightings per state as a choropleth map. The operation was simple, choosing to style the map layer as a graduate style based on the field containing the number of sightings in each state. The colors selected -for all the maps and the website of this project- were a gradient of light, bright, browns combined with white for the lowest map values and black as complementary for some map elements. Based on a Natural Breaks classification, I edited the values in each categories to make them seem less random. This map can be accessed through [this link](https://alexmunozviso.github.io/map671-fp/#Bigfoot%20Sightings%20by%20State).

For the second map, I wanted to offer a more nuanced representation of the data so it could add to the information provided by the state map. Rather than just representing the number of sightings per county, I decided to normalize these values to offer a more geographically accurate map. This operation was also pretty straightforward. Using the field calculator, I divided the field containing the number of sightings by that of the county area in square kilometers (see Fig. 7).

![Figure 7](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig7.png)
*Fig. 7: Field calculation to obtain a normalized sightings value per county.*

I exported the US county data containing also the Bigfoot sightings data as a shapefile. I made its CRS ESRI: 102008 (North America Albers Equal Area Conic).

Using the sightings density field that I just calculated, I made my second map. The styling and categorization was just as that of the first map. This second map can be accessed through [this link](https://alexmunozviso.github.io/map671-fp/#Bigfoot%20Sightings%20by%20County).

I also created a simpler but very visually effective third map. This map shows the Bigfoot sighting reports as point data distributed through the territory of the contiguous United States. For this map, the US state map is represented using as a Single Symbol layer styling. Then, the data points for Bigfoot sightings is represented using a bigfoot symbol instead of a point. In order to do so, I opened the layer styling pan and selected 'Single symbol' (Fig. 8). Then, on 'Symbol layer type' (Fig. 9) I changed the standard 'Simple Marker' for 'SVG Marker'. Scrolling down to the bottom, there is an option to upload an SVG file and personalize the map symbol (Fig. 10). I used a Bigfoot icon that I downloaded from [Freepik](https://www.freepik.com) and edited with Adobe Illustrator to match the style of my project. Finally, I tested different icon sizes and decided for 1.5.

![Figures 8, 9, and 10](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig8-9-10.png)
*Fig. 8, 9, and 10 (left to right): Using a personalized SVG file as the map symbol.*


You can see this final static map following [this link](https://alexmunozviso.github.io/map671-fp/#Bigfoot%20Sighting%20Reports%20(1900-2016)).

### Webmap
As part of this project, I also created an interactive webmap using [Mapbox](https://www.mapbox.com/) that could be inserted in the header of the project's website.

I started by uploading the final Bigfoot sightings and US state layers as databases to Mapbox. Then, I created a new style (i.e. map). For the basemap, I used Mapbox's template 'Outdoors'. I changed the style's name to match my project and added my two layers. 

I arranged the Bigfoot point data on top of the state boundaries. For the latter, I kept the stroke but gave it a transparent fill (see Fig. 11). In order to have the data points represented with the Bigfoot vector, I selected the layer and then 'Select data/Type/Symbol' (as shown in Fig. 12).

![Figure 11](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig11.png)
*Fig. 11: View of the two layers on Mapbox.*

![Figure 12](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig12.png)
*Fig. 12: Changing the layer symbology from a point to a symbol in Mapbox.*

Then, I went back to 'Style', and clicked on 'Icon/Image/Upload Images' (as shown in Fig. 13).

![Figure 13](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig13.png)
*Fig. 13: Uploading a personalized image as map symbol.*

After uploading my SVG image as the map symbol, I edited its size. Because the appropriate symbol size should be different depending on the zoom scale, I selected diverse sizes values according to zoom levels. To do that, I clicked on 'Size' and then 'Style across zoom range' (see Fig 14).

![Figure 14](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig14.png)
*Fig. 14: Styling symbol size across zoom range in Mapbox (I).*

Finally, after some try-and-error, and testing different options, I created this variable size according to zoom range:

![Figure 15](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig15.png)
*Fig. 15: Styling symbol size across zoom range in Mapbox (II).*

Finally, under 'Settings' I marked a 'Default map position' in terms of zoom and coordinates that matched that of the contiguous US in its entirety. Then, I pressed 'Lock' and saved these values so I could use them to mark the map's position in the the [*map.html*](https://github.com/alexmunozviso/map671-fp/blob/main/map.html) file in this repository (and home of the webmap of this project!).

![Figure 16](https://github.com/alexmunozviso/map671-fp/blob/main/img/fig16.png)
*Fig. 16: Setting a map position for the webmap.*


Both an inserted and full-page version of the webmap can be seen and interacted with in the project's website, accessible through the link in the section below.

# Final Project Link
Please view the website for my final project [following this link](https://alexmunozviso.github.io/map671-fp).
