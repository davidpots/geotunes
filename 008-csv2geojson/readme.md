# Problem

I am publishing CSV via Google Docs. I want to make it work in my map (which I think means converting it to GeoJSON).

Following this: https://www.mapbox.com/mapbox.js/example/v1.0.0/markers-from-csv/

# What this does

It takes a local CSV file (airports.csv) and uses the csv2geojson.js file (also saved locally) and displays all that data on my map.

# To do next:

- Take my own personal CSV file (from Google Docs) and replicate this. Save that file locally, and display those markers on the map.
- After proving the step above, see this (https://www.mapbox.com/tilemill/docs/guides/google-docs/) and check out how I can publish my CSV to TileMill directly from Google Docs. You did this in a prior project.
- After you master this, you can then manage your markers/location data exclusively in Google Docs -- and you shouldnt need to worry about saving a file / pasting the CSV with each update. That is pretty awesome.
- Then, you can look into the EchoNest API thing. If you could have the Echo Nest pull up the data for each tooltip as / after the tooltip is loaded (based on some song ID passed in the google doc), that'd be awesome
- Then, design that shit! Make the map pretty
- Also, figure out how to possibly let the user elegantly switch between tooltips/makers in a "next/prev" sort of way. That'd be awesome
- Also, see if you can figure out how to have a permanent legend / layer on the map that lets a user browse the songs / years / etc without requiring them to use the markers first.