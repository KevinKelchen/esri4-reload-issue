# esri4-reload-issue

While developing a mobile application with the Esri ArcGIS Javascript API 4.12, we discovered the iOS phone browsers (and desktop Safari) are crashing with a simple WebMap.  It appears to be related to the Share settings of the Feature Layer.

Example app, use iOS Safari/Chrome or MacOS Safari: https://esri4-reload-issue.netlify.com  
Login: Use your Cartegraph AGOL credentials  
Map being used as of 9-12-19: http://cartegraph.maps.arcgis.com/home/item.html?id=fbe67d845361475f92333c9f563cd53d  

How to create the issue manually:
1. Create New Feature Layer (polygon) in ArcGIS Online
2. Add Feature Layer to Map, use default basemap.
3. Save Map
4. Share Map to "Everyone"
5. Go to Details of Feature Layer and set Sharing to "Org"
6. View Map in iOS Safari/Chrome, or MacOS Safari browser.
7. Zoom out on the map, the browser will crash and attempt to reload the content.

If you change the Sharing of the Feature Layer to "Everyone", the map will be stable.  For some reason whenever the Sharing of the Feature Layer isn't "Everyone", the map will crash the browser constantly.

Is there extra processing, or authentication, that is occurring when a Map/Feature Layer are configured this way?  Is this an invalid configuration?  I have not seen anything in the console or network traffic that would suggest the map is more complex with a secured Feature Layer.