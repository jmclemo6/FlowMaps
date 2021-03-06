# FlowMaps

Makes flow maps using mathematical interpolations between a start and an end point in a given map projection.

The script takes one input file, being a CSV table of flows. It produces one output file in shapefile, geojson, kml, gml, or gmt format.

For thorough usage information, please use the help flag from the command line:

```
python InterpolatedFlowMaps.py -h
```

Please note that the input CSV file must be in the format of the example below.  The headers seen below, named exactly as seen, must be present and unique in the input file, though other headers/columns may exist (these will be ignored). Sequencing of the headers does not matter. Strings throughout may be enclosed in double quotes.  FlowMag variables can have decimals, but don't necessarily need to be numbers (e.g., they could be strings like "high" or "low") - these values are simply copied to the output geojson file.

All coordinate values must be latitude and longitude in WGS84.

Example CSV:

```
OrigName,OrigLat,OrigLon,DestName,DestLat,DestLon,FlowMag
Ponta Delgada,37.7483018179,-25.6665834976,Lisbon,38.7227228779,-9.1448663055,6013
Ponta Delgada,37.7483018179,-25.6665834976,Los Angeles,33.9899782502,-118.179980511,1661
Ponta Delgada,37.7483018179,-25.6665834976,Coimbra,40.2003743683,-8.41668034,2259
Ponta Delgada,37.7483018179,-25.6665834976,Christchurch,-43.5350313123,172.630020711,4656
Ponta Delgada,37.7483018179,-25.6665834976,Toronto,43.6999798778,-79.4200207944,584
Ponta Delgada,37.7483018179,-25.6665834976,Kyoto,35.0299922882,135.749997924,282
Ponta Delgada,37.7483018179,-25.6665834976,Yokohama,35.3200262645,139.58004838,6985
Ponta Delgada,37.7483018179,-25.6665834976,Durban,-29.8650130017,30.9800105374,4981
Ponta Delgada,37.7483018179,-25.6665834976,Knoxville,35.9700124298,-83.9200303566,1235
```

## Dependencies

* scipy
* gdal
* shapely
* pyproj