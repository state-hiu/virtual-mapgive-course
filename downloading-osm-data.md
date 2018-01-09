
# Downloading OSM data

As a GIS professional, you may come accross having a need to utilize OSM data in a GIS software package. Today we will introduce some ways to do this using QGIS, one of the most popular free and open source GIS software packages! There are many qays to download OSM data, here are just a few:

## For Small areas

### QGIS 2: OpenStreetMap Vectors 
(source: http://wiki.openstreetmap.org/wiki/QGIS#QGIS2_OpenStreetMap_Vectors)

QGIS 2.0 integrates OpenStreetMap import as a core functionality. To get OSM data:

* Menu "Vector -> Openstreetmap -> Load data" will connect to the OSM server and download data. You can skip this step if you already have a .osm XML file.

* "Import topology from an XML file" below will convert your .osm file into a spatialite database, and create a db connection.

* "Export topology to Spatialite" then allows you to open the database connection, select the type of data you want (points, lines, polygons) and choose tags to import. This creates a spatialite geometry layer that you can then add to your project via the "add a spatialite layer" menu.

Note that this process imports raw OSM GIS data not any particular map **style/symbology**.

### OpenStreetMap.org

![OSM export](https://cloud.githubusercontent.com/assets/2665840/10675703/316c40d0-78f1-11e5-96a6-99021f47468b.png)

## For Large areas

### geofabrik
http://download.geofabrik.de/

You can click on different regions then drill down to small subunits.You can then download the latest OSM extracts in different formats.

QGIS can open both .osm and osm.pbf files. Just click the 'Add vector data' button.

For large datasets .osm and .osm.pbf files can be slow to work with, so you may want to add your data to a spatial database such as PostGIS or SpatiaLite. View the [OSM to SpatiaLite instructions](https://github.com/d3netxer/virtual-mapgive-course/blob/master/OSM-to-SpatiaLite.md)

### HOT export tool

* You can only extract certain areas of the world
* Interesting output formats such as shapefile, Garmin Map, OSMAnd OBF, and SQLite SQL

