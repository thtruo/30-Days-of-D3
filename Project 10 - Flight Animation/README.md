## Create TopoJSON world map

    # Download "Admin 0 - Countries" zip file from Natural Earth

    # Convert shapefile to GeoJSON (exclude Antartica)
    ogr2ogr -f GeoJSON -where "SU_A3 <> 'ATA'" countries.json ne_10m_admin_0_countries_lakes/ne_10m_admin_0_countries_lakes.shp

    # Convert GeoJSON to TopoJSON
    ./node_modules/.bin/topojson --id-property SU_A3 -p name=NAME -p name -o countries.topo.json countries.json

## Create TopoJSON airport data
    # Download "Airports" zip file from Natural Earth

    # Convert shapefile to GeoJSON (include major airpots)
    ogr2ogr -f GeoJSON -where "scalerank < 6" airports.json ne_10m_airports/ne_10m_airports.shp

    # Convert GeoJSON to TopoJSON
    ./node_modules/.bin/topojson --id-property abbrev -o airports.topo.json airports.json

## Draw maps and airports


## Draw plane in SVG


## Draw flight path


## Animate plane


## Rotate plan