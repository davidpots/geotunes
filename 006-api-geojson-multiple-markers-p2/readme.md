# Goal

I want to take 005, and add to it by having MULTIPLE markers set via the GeoJSON document.

Reading about this, it seems CSV may be a valuable tool to use for this. 

- A Mapbox example showing CSV use is here: https://www.mapbox.com/mapbox.js/assets/airports.csv
- Mapbox talking about getting addresses processed into lat/long is here: https://www.mapbox.com/tilemill/docs/guides/data-to-map/

These lead me to this document, which describes how to manage addresses / locations in Google Docs, and then process them into CSV with lat/long. Okay!

    https://www.mapbox.com/tilemill/docs/guides/google-docs/

The first step is to install this: 
  
    https://github.com/mapbox/geo-googledocs

Here is what a successful Google Spreadsheet looks like, after parsing address to lat/long:

    http://monosnap.com/image/dyKzwYq6inSrwp6z8n1d5GKc2.png

## Exporting GeoJSON & CSV

I was able to successfully export everything to GeoJSON and load it in the map. First, I selected all columns. Then I did Tools > Export GeoJSON. I then pasted the output into my GeoJSON file, but had to put curly braces before/after it to work. Successful file looks like this:

    { 
      "features":[{"id":"chesapeake beach, maryland","properties":{"geo_accuracy":"administrative","place":"chesapeake beach, maryland","geo_longitude":-76.534678,"geo_latitude":38.6862299},"type":"Feature","geometry":{"type":"Point","coordinates":[-76.534678,38.6862299]}},{"id":"columbia, maryland","properties":{"geo_accuracy":"administrative","place":"columbia, maryland","geo_longitude":-76.8546725,"geo_latitude":39.2151996},"type":"Feature","geometry":{"type":"Point","coordinates":[-76.8546725,39.2151996]}},{"id":"lusby, maryland","properties":{"geo_accuracy":"administrative","place":"lusby, maryland","geo_longitude":-76.4415551084601,"geo_latitude":38.356088},"type":"Feature","geometry":{"type":"Point","coordinates":[-76.4415551084601,38.356088]}},{"id":"berwyn heights, maryland","properties":{"geo_accuracy":"administrative","place":"berwyn heights, maryland","geo_longitude":-76.9105292,"geo_latitude":38.9939991},"type":"Feature","geometry":{"type":"Point","coordinates":[-76.9105292,38.9939991]}},{"id":"college park, maryland","properties":{"geo_accuracy":"city","place":"college park, maryland","geo_longitude":-76.9369189,"geo_latitude":38.980666},"type":"Feature","geometry":{"type":"Point","coordinates":[-76.9369189,38.980666]}}],"type":"FeatureCollection"
    }

I was able to export to CSV using the instructions here: https://www.mapbox.com/tilemill/docs/guides/google-docs/

Import to TileMill using the instructions on either of these two posts. This works for both CSV and for GeoJSON. Important! Be sure to select "Save and Style" when you import, otherwise the markers won't be styled at all.

    # CSV
    https://www.mapbox.com/tilemill/docs/guides/google-docs/

    # GeoJSON
    https://www.mapbox.com/blog/mapping-google-doc-spreadsheet/

Here is the Google Doc I used to create this: https://docs.google.com/spreadsheet/ccc?key=0Agr4pQlyhezxdG1sbE1mbzg0Q2FLV2tFV3pYM2xUVVE&usp=drive_web#gid=0

## Next

Figure out how to have popup / tooltips for each pin. Ideally, I create a link between an ID in each location into another JSON file, where I can store all the other crap for the song (song name, description, etc). After this, figure out how to ALSO link this to the EchoNest API: so the ID of the lat/long maps to a song ID, which then pulls in data for that song from EchoNest.