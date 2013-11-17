# About This Prototype

I took 004, which (1) loads an example generic map from TileMill, and then (2) shows a marker positioned via GeoJSON. Then, I swapped out the generic map from TileMill with my own TileMill map -- which also specifies a marker. 

This is the original code summoning the map:
    
    var map = L.mapbox.map('map', 'examples.map-9ijuk24y')
      .setView([38, -102.0], 9);

And here is what I replaced it with (i.e., make it use my map instead):

    var map = L.mapbox.map('map', 'davidpots.g9cfjo03')
      .setView([37.9, -77], 5);

### The Result

Is that both pins appear! The pin in my TileMill map appears, as does the map in the GeoJSON source.

Next, I want to try having multiple pins in the GeoJSON source.