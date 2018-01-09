# OpenStreetMap Export Tutorial

## Exporting data from OpenStreetMap

OpenStreetMap (OSM) is open and freely available data. All of data that you help create and upload into OSM, can be extracted back out. As you spend time working with Geographic Information Systems, you may want to utilize OSM data in a GIS software package. There are various different ways you are able to extract data from OpenStreetMap. This guide will compare and contrast different methods so you can choose the best way that fit your needs.

## 1. The Simple Way: Downloading straight from OpenStreetMap.org

- difficulty: easy
- scale: city-level
- file-format: .osm

This is the easiest and most straightforward way to download OSM data. Go to OpenStreetMap.org and navigate to the area you want to download. The site will not let you download too much data at one time, therefore you need to zoom into about the city level. When you are ready to download the area that is displayed on your screen click on the Export button on the top menu. The left-hand export pane will display. Another option to select an area is by manually inputting the coordinates of the bounding box. Then click on the Export button on the left-hand pane to begin your download. 

![osm download](assets/osm_website_export_annotated.png)

## 2. Geofabrik [download](http://download.geofabrik.de/)

- difficulty: easy
- scale: country-level
- file-format: .osm.pdf, shapefile

GeoFabrik has data extracts from OSM which are normally updated every day. The extracts typically cover whole countries and regions. Select your continent and then your country of interest. Options to download include .osm.pbf and shapefiles. 

A .osm.pbf is a compressed .osm file. A .osm file is a type of XML file that contains OSM data.

### shapefile format
In OSM there are no layers in the traditional GIS sense. There are different types of features such as points (nodes), lines (ways), and polygons (closed ways). A feature is defined according to what it's tags are, and a tag can be anything. Geofabrik generates shapefiles grouping the most commonly found types of features in OSM into layers that are commonly used in GIS software. For example, one of the layers are roads, which contain the highways, tracks, and paths found in OSM.

## 3. Metro Extracts

- difficulty: easy
- scale: city-level
- file-format: various

Metro Extracts are chunks of OpenStreetMap (OSM) data clipped to the rectangular region surrounding a particular city or region of interest. Data is available for locations around the world and is updated on a weekly basis. If you don't see an existing extract that covers the area you are interested in, you can create your own custom extract. You can download a file format according to how you would like your data organized.

![file_format](assets/fileformat.png)

To download the OSM data, go to the Metro Extracts download page at https://mapzen.com/data/metro-extracts/. Learn more about using Metro Extracts by following this [tutorial](https://mapzen.com/documentation/metro-extracts/tutorial/).

The files organized by OpenStreetMap tags have differences compared to shapefiles from Geofabrik. Here is an example:

#### Metro Extract organized by OSM tags
- admin
- aeroways
- amenities
- barrierpoints
- barrierways
- buildings
- housenumbers
- land usages
- places
- roads
- roads generalized
- transport areas
- transport points
- water areas
- water areas generalized
- waterways

#### Geofabrik download organized by OSM tags

- buildings
- landuse
- natural
- places
- pofw (places of worship)
- pois (points of interest)
- railways
- roads
- traffic
- transport areas
- water
- waterways

## 4. Query to find the exact data you need: Overpass Turbo (https://overpass-turbo.eu/)

- difficulty: medium to advanced
- scale: city
- file-format: various

Overpass Turbo, is a web-based data filtering tool for OpenStreetMap. With Overpass Turbo you can run Overpass API queries and analyse the resulting OSM data interactively on a map. There is an integrated Wizard which makes creating queries super easy. There is a limit to how much you can download so you may need to limit your searches. There are also some nifty queries you can make such are compare differences over different time periods 

## 5. Download the whole planet - Planet.osm.org

- difficulty: medium
- scale: world
- file-format: .osm.pbf

Downloading the whole planet can be useful in certain use cases including research, generating metrics, and looking at historical data. The downsize is that these files are very large. An uncompressed .osm that covers the whole planet is over 800GB. On this site you download compressed files that are smaller (over 35GB) but still large. You can also download history planet files that contain historical OSM information.

## 6. Download OSM straight from QGIS

- difficulty: medium
- scale: city
- file-format: .osm, spatialite

QGIS, which is a free, open-source desktop GIS application. QGIS integrates OSM import as a core functionality. 

### Note: 
Before bringing in any data, first add a basemap. Harvard has a good walkthrough on how to do this by adding the OpenLayers plugin. [Tutorial](http://maps.cga.harvard.edu/qgis/wkshop/basemap.php)

In QGIS, go to Menu "Vector -> OpenStreetMap -> Download data" which will connect to the OSM server and download data. You can select coordinates for the area you want. You can skip this step if you already have a .osm XML file. The server will not let you download too much data at one time, therefore you need to zoom into about the city level.

![Load data](assets/vector_Download_Data.PNG)
![Load data2](assets/osm_Download_Data_Window.PNG)

QGIS is able to load osm files directly (.osm and .osm.pbf files). 

If you need to get the data into a Spatialite database then continue with the following two steps:

On QGIS the .osm file can be imported at "Vector -> Openstreetmap -> Import Topology from XML"."Import topology from an XML file" will convert your .osm file into a spatialite database, and create a db connection.

![QGIS OSM import](assets/vector_Import_from_XML_.bmp)
![QGIS OSM import2](assets/import_from_XML.bmp)

"Export topology to Spatialite" then allows you to open the database connection.
![Vector Export](assets/vector_Export_SpatialLite.PNG)

Find your .osm db file that you created in the "Import Topology from XML"
![import osm db](assets/export_Osm_SpatialLite.PNG)

Finally select the type of data you want (points, lines, polygons) and choose tags to import. This creates a spatialite geometry layer that you can then add to your project via the "add a spatialite layer" menu.
![types of data](assets/export_Osm_SpatialLite_Data_Type_Tags.PNG)

Note that this process imports raw OSM GIS data, not any particular map style/symbology.

## 7. [OSM Export Tool](http://export.hotosm.org/en/)

Yet another way to extract data is via the HOT OSM Export Tool. This tool is recently being developed on, and HOT will release a new version. We will expand on our guidance once the new version is complete.

