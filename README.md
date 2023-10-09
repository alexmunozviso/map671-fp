
# Mapping Bigfoot sightings 

## Project Contents

- [Mapping Bigfoot sightings](#mapping-bigfoot-sightings)
  - [Project Contents](#project-contents)
  - [Project Introduction](#project-introduction)
  - [Data Sources](#data-sources)
    - [Bigfoot Sightings Data](#bigfoot-sightings-data)
    - [Other Data](#other-data)
  - [Mapmaking Process](#mapmaking-process)
- [Final Project Link](#final-project-link)

***
## Project Introduction
For the final project of MAP671, I wanted to create a map representing curious data. Looking for different themes, I stumbled upon [The Bigfoot Field Research Organization (BFRO)](http://www.bfro.net), a website compiling different databases of Bigfoot encounters including sightings, audible sightings, trackmarks, or footprints. Every report included in these databases is geocoded and timestamped. 

Although I am not the 'I believe' type or into conspiracy theories, I thought it could be fun to map this data. Moreover, the BFRO accepts online submissions of Bigfoot sighting reports, which adds a certain sense of community data crowdsourcing and community mapping to the project; two research topics that are of great personal interest.

## Data Sources

### Bigfoot Sightings Data
My database of Bigfoot sightings was constructed using the summaries of data from [The Bigfoot Field Research Organization (BFRO)](http://www.bfro.net) elaborated by [Mangani's Bigfoot Maps](http://penn.freeservers.com/bigfootmaps/). From the latter's website, I downloaded a
[text file](http://www.penn.freeservers.com/bigfootmaps/BFROcreature.txt) containing the 2016 updated BFRO's creature sightings. This data includes only visual sightings of the Bigfoot and excludes records of audible sightings, trackmarks, or footprints. I converted the text file into a CSV file and edited it using [VS Code](https://code.visualstudio.com). I organized and reworked the attribute data file to contain latitude, longitude, date of the sighting, and a link to the BFRO's report of each record in a way that could be read by QGIS as a geodata layer (see Fig. 1). Finally, I imported the CSV file into QGIS as Delimited text and saved it as a GeoJSON. 

**Both files can be downloaded here:**

* [bfro-creature-sightings.csv](https://github.com/alexmunozviso/map671-fp/blob/main/data/bfro-creature-sightings.csv)
* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA GeoJSON LINK

![CSV screenshot](https://github.com/alexmunozviso/map671-fp/blob/main/img/screenshot01.png)
*Fig. 1: Screenshot of the CSV file after editing it in VS Code*


### Other Data
2022 United States county and state boundaries were obtained from the [United States Census Bureau website](https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html). After adding geometries, **joining the Bigfoot sightings database per location**, and normalizing this data per state/county area, these are the final datasets:
* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA state LINK
* DATAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA county LINK

## Mapmaking Process


# Final Project Link

Please view the website for my final project [following this link](www.github...).
