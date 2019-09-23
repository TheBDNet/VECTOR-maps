# Add code in template header
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css"/><br/>
  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script><br/>
  <script src="http://code.jquery.com/jquery-2.1.4.min.js"></script><br/>

# Code in article
<div id = "map" style = "width:100%; height:300px"></div><br/>
<script><br/>
   // Creating map options<br/>
   var mapOptions = {<br/>
 center: [23.80, 90.25],<br/>
 zoom: 10<br/>

   // Creating a map object<br/>
   var map = new L.map('map', mapOptions);<br/>

   // Adding tile layer to map<br/>
   var layer = new L.TileLayer('https://tile.thunderforest.com/outdoors/{z}/{x}/{y}.png?apikey=<apikey>').addTo(map);<br/>

   // load GeoJSON from an external file<br/>
   $.getJSON("phocamapskml/faridpur.geojson",function(data){<br/>
     // add GeoJSON layer to the map once the file is loaded<br/>
     L.geoJson(data).addTo(map);<br/>
   });<br/>

   // Adding marker to the map<br/>
   marker.addTo(map);<br/>
</script><br/>
