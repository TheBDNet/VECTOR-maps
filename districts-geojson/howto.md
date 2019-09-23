# Add code in template header
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css"/><br/>
  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script><br/>
  <script src="http://code.jquery.com/jquery-2.1.4.min.js"></script><br/>

# Code in article
<div id = "map" style = "width:100%; height:300px"></div>
<script>
   // Creating map options
   var mapOptions = {
   center: [23.80, 90.25],
   zoom: 10

    //Scroll wheel zoom only after click
    map.scrollWheelZoom.disable();
    map.on('focus', () => { map.scrollWheelZoom.enable(); });
    map.on('blur', () => { map.scrollWheelZoom.disable(); });

   // Creating a map object
   var map = new L.map('map', mapOptions);

   // Adding tile layer to map
   var layer = new L.TileLayer('https://tile.thunderforest.com/outdoors/{z}/{x}/{y}.png?apikey=7b0675ae928f48a68ad159eb21934271').addTo(map);

   // load GeoJSON from an external file
   $.getJSON("phocamapskml/faridpur.geojson",function(data){
     // add GeoJSON layer to the map once the file is loaded
     L.geoJson(data).addTo(map);
   });

   // Adding marker to the map
   marker.addTo(map);

</script>
