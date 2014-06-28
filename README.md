quitestyleWA
============

###To produce basemap using OSM data and TileMill to generate basemap cache

##Steps:

1. Using OSM data from Geofabrik for WA State, Washington-lates.OSM bz2 data. Using this URL:
http://download.geofabrik.de/north-america/us/washington.html

2. Using TileMill to stylize using CartoCSS (MSS files)

     imposm shapefiles are in WGS84 Mercator projection

     Using KC data, need to reproject StatePlane to WGS84 - Read https://gist.github.com/keum/7920560/edit

     using ogrinfo namdoffile.shp -al -so to view the data

     using ogr2ogr command to convert stateplane into WGS84:  ogr2ogr -t_srs EPSG:4326 newnameFile.shp oldNameFile.shp




3. Will try to use osm-quite-la produced from LA Times staff: http://datadesk.github.io/osm-quiet-la/

     osm-quite-la MSS (style file):  color palette, road symbols, labels and other features.

     Palette:  https://github.com/keum/osm-quiet-la/blob/master/quiet-la/palette.mss

     Road symbol:  https://github.com/keum/osm-quiet-la/blob/master/quiet-la/roads.mss

     Other features:   https://github.com/keum/osm-quiet-la/blob/master/quiet-la/style.mss

     Labeling:    https://github.com/keum/osm-quiet-la/blob/master/quiet-la/labels.mss



##Workflow:

A: Take OSM data from metro extract
  1. Taking data from Geofabrik which is extracted data from OSM
  url: http://download.geofabrik.de/north-america.html choosed WA state. using download washington-latest.osm.bz2

B: Bring them into TillMill and style them using Quite-LA style

C. Create mbTile to cache basemap.

D. Cache individual layers  (features of sewer/points/service area)



##Using:

A. Using TileStream: - Serving Mbtiles load into client web browser.

1. Using portable-node-app (from Dane) to install windows TileStream in local laptop and copy the exported Mbtiles files into appropriate directory.

2. Install leaflet and it’s library locallyA for TileMill
