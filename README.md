
# Mapping Bigfoot sightings 

## Project Contents

- [Mapping Bigfoot sightings](#mapping-bigfoot-sightings)
  - [Project Contents](#project-contents)
  - [Project Introduction](#project-introduction)
  - [Data Sources](#data-sources)
    - [Bigfoot Sightings Data](#bigfoot-sightings-data)
    - [Other Data](#other-data)
  - [Mapmaking Process](#mapmaking-process)
  - [Map summary](#map-summary)
- [Final Project Link](#final-project-link)

***
## Project Introduction
For the final project of MAP671, I wanted to create a map representing curious data. Looking for different themes, I stumbled upon [The Bigfoot Field Research Organization (BFRO)](www.bfro.net), a website compiling different databases of Bigfoot encounters including sightings, audible sightings, trackmarks, or footprints. Every report included in these databases is geocoded and timestamped. 

Although I am not the 'I believe' type or into conspiracy theories, I thought it could be fun to map this data. Moreover, the BFRO accepts online submissions of Bigfoot sighting reports, which adds a certain sense of community crowdsourcing to their data.

## Data Sources

### Bigfoot Sightings Data
A database of Bigfoot sightings was constructed using the summaries of data from [The Bigfoot Field Research Organization (BFRO)](www.bfro.net) elaborated by [Mangani's Bigfoot Maps](http://penn.freeservers.com/bigfootmaps/). From the latter's website, I downloaded the
[text file](http://www.penn.freeservers.com/bigfootmaps/BFROcreature.txt) containing the 2016 updated BFRO's creature sightings. I converted the text file into a CSV file and edited it using [VS Code](https://code.visualstudio.com). I organized the attribute data file to contain latitude, longitude, date of the sighting, and a link to the BFRO's report of each record (see Fig. 1). 

![CSV screenshot](https://github.com/alexmunozviso/map671-fp/blob/main/img/screenshot01.png)
*Fig. 1: Screenshot of the CSV file viewed in VS Code*

The CSV file was then imported to QGIS as Delimited text and exported as a GeoJSON. Both can be downloaded here:

* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA CSV LINK
* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA GeoJSON LINK

### Other Data
2022 United States county and state boundaries were obtained from the [United States Census Bureau website](https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html). After adding geometries, **joining the Bigfoot sightings database per location**, and normalizing this data per state/county area, these are the final datasets:
* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA state LINK
* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA county LINK

## Mapmaking Process

Example of in process map ![in process image](filepath)

1. **Example bold**
2. *Example italics*
3. 
4. 

## Map summary

Across the README.md file, please answer the who, what, when, where, why, and how of the map making process


# Final Project Link

Please view the [final map online](www.github...)
