** Background**

Building scale-dependent view of data

**Commands for creating and serving vector tiles**

Preliminary setup:
1. Install GDAL binaries and verify that **ogr2ogr** is accessible from the command line.
2. On a Windows 10 machine, install [**CYGWIN**](https://cygwin.com/) Linux shell
3. Compile [**tippecanoe**](https://github.com/mapbox/tippecanoe) using Cygwin following the instructions listed here:
  -   [ArcGIS2Mapbox](https://github.com/GISupportICRC/ArcGIS2Mapbox#installing-tippecanoe-on-windows)

**convert Shapefile to GeoJSON using ogr2ogr**

OGR2OGR
-- ogr2ogr works when at C:\\Users\\[user]
`docker run -it --rm -v C:\\Users\\joelm:/data klokantech/gdal ogr2ogr -t_srs EPSG:4326 -f GeoJSON KingCo_2000_Census_BlockGroups.geojson KingCo_2000_Census_BlockGroups.shp -Progress`

OGRINFO

- Park Boundary GeoJSON:

`ogrinfo input/geojson/Gonarezhou/Gonarezhou_Park_Boundary.geojson -al -so`

- Patrol Blocks GeoJSON:

`ogrinfo input/geojson/Gonarezhou/Gonarezhou_Patrol_Blocks.geojson -al -so`


**convert GeoJSON to Vector Tiles using tippecanoe**

TIPPECANOE

`tippecanoe -o output/mvt/Gonarezhou_Park_Boundary.mbtiles input/geojson/Gonarezhou/Gonarezhou_Park_Boundary.geojson`

`tippecanoe -o output/mvt/Gonarezhou_Patrol_Blocks.mbtiles input/geojson/Gonarezhou/Gonarezhou_Patrol_Blocks.geojson`


**serve local Vector Tiles using TileServer GL**

TILESERVER-GL

`docker run --rm -it -v C:\\users\\[user]:/data -p 8080:80 klokantech/tileserver-gl`


**Modify *config.json* file**


{
  "data": {
    "Gonarezhou_Park_Boundary": {
      "mbtiles": "Gonarezhou_Park_Boundary.mbtiles"
    },
    "Gonarezhou_Patrol_Blocks": {
      "mbtiles": "Gonarezhou_Patrol_Blocks.mbtiles"
    },
    "Gonarezhou_points": {
      "mbtiles": "Gonarezhou_points.mbtiles"
    }
  },
  "options": {
    "paths": {
      "fonts": "fonts",
      "mbtiles": "/data",
      "root": "/usr/src/app/node_modules/tileserver-gl-styles",
      "styles": "styles"
    }
  },
  "styles": {
  }
}


**Launch Maputnik Style Editor**

- navigate to location of Maputnik install:

- \..\\Maputnik\\public\\
