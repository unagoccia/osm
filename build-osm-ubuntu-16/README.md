# opentileserver

This script is for building a basic tile server with OpenStreetMap data.

Only for use on a clean Ubuntu 16 install!!

Before proceeding, see <a href="opentileserver.org" target="blank"> opentileserver.org </a> for limitations, etc..

Step 1: Get opentileserver.sh script from GitHub

Step 2: Make it executable:

<code>chmod 755 opentileserver.sh</code>

Step 3:

vi and change the password on line 19 to something difficult

<code>
OSM_USER_PASS='posm';	#CHANGE ME
</code>

If using a non-Latin alphabet, ucomment line 24 below if needed:

<code>export LC_ALL=C</code>

See https://github.com/MapFig/opentileserver/issues/4

Step 4: Run the script

## Script usage:

<code>./opentileserver.sh  [web|ssl] [bright|carto] pbf_url</code>

[web|ssl]: 'web' for http and 'ssl' for https.

[bright|carto]: 'carto' for openstreetmap-carto or 'bright' for openstreetmap-bright

pbf_url: Complete PBF url from GeoFarbrik (or other source)


## Examples:

Load Delware data with openstreetmap-carto style and no SSL:

<code>./opentileserver.sh web carto http://download.geofabrik.de/north-america/us/delaware-latest.osm.pbf </code>

Load Bulgaria data with openstreetmap-bright style and SSL:

<code>./opentileserver.sh http://download.geofabrik.de/europe/bulgaria-latest.osm.pbf bright</code>

Load South America data with openstreetmap-carto style and SSL:

<code>./opentileserver.sh ssl carto http://download.geofabrik.de/south-america-latest.osm.pbf </code>

Load Japan data with openstreetmap-bright style and no SSL:

<code>./opentileserver.sh web bright http://download.geofabrik.de/asia/japan-latest.osm.pbf</code>

#generate_tiles_multiprocess.py

## Over View
Generate tiles

Step 1: Change user who created the osm-data

Step 2: Export params  
<code>export MAPNIK_MAP_FILE=xxx.xml</code>  
<code>export MAPNIK_TILE_DIR=/xxxxx/xxxx</code>

Step 3: Run the script

## Examples  
<code>su osm</code>  
<code>export MAPNIK_MAP_FILE=/usr/local/share/maps/style/OSMBright/OSMBright.xml</code>  
<code>export MAPNIK_TILE_DIR=/var/lib/mod_tile/default/</code>  
<code>./generate_tiles_multiprocess.py</code>
