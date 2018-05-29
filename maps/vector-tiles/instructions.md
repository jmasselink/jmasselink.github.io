**Command templates for creating and serving vector tiles**

OGR2OGR
-- ogr2ogr works when at C:\Users\joelm
docker run -it --rm -v C:\Users\joelm:/data klokantech/gdal ogr2ogr -t_srs EPSG:4326 -f GeoJSON KingCo_2000_Census_BlockGroups.geojson KingCo_2000_Census_BlockGroups.shp -Progress

OGRINFO
-- Park Boundary GeoJSON
ogrinfo input/geojson/Gonarezhou/Gonarezhou_Park_Boundary.geojson -al -so
-- Patrol Blocks GeoJSON
ogrinfo input/geojson/Gonarezhou/Gonarezhou_Patrol_Blocks.geojson -al -so

TIPPECANOE
tippecanoe -o output/mvt/Gonarezhou_Park_Boundary.mbtiles input/geojson/Gonarezhou/Gonarezhou_Park_Boundary.geojson

tippecanoe -o output/mvt/Gonarezhou_Patrol_Blocks.mbtiles input/geojson/Gonarezhou/Gonarezhou_Patrol_Blocks.geojson


TILESERVER-GL
docker run --rm -it -v C:\users\keump:/data -p 8080:80 klokantech/tileserver-gl
docker run --rm -it -v "c:/Users/joelm/Dropbox (Vulcan)/GIS/Projects/vector_tile_project/data/output/mvt":/data -p 8080:80 klokantech/tileserver-gl


-- DOCKER Tileserver-gl - THIS WORKS
PS C:\Users\joelm\Dropbox (Vulcan)\GIS\Projects\vector_tile_project\data\output\mvt>
docker run --rm -it -v C:\Users\joelm:/data -p 8081:80 klokantech/tileserver-gl

-- DOES NOT WORK
PS C:\Users\joelm\Dropbox (Vulcan)\GIS\Projects\vector_tile_project>
docker run --rm -it -v data:/data -p 8081:80 klokantech/tileserver-gl "/output/mvt/Gonarezhou_Park_Boundary.mbtiles"

docker run -v C:\Users\joelm\Dropbox (Vulcan)\GIS\Projects\vector_tile_project\data

output/mvt/Gonarezhou_Patrol_Blocks.mbtiles


TILESERVER-GL - CYGWIN
-- doesn't work
docker run --rm -it -v mvt:/data -p 8081:80 klokantech/tileserver-gl --mbtiles Gonarezhou_Patrol_Blocks.mbtiles
