<html>

<head>

<link rel="stylesheet" href="./Leaflet-1.0.3/leaflet.css"/>
<script src="./Leaflet-1.0.3/leaflet.js"></script>
<!-- map style  -->  
<style>
#map{ height: 100%; }
</style>

</head>

<body>

<div id="map"></div>
<!-- create the map -->
<!--L.tilelayer example with mapbox api-->
<script>
var map = L.map('mapid').setView([45.4215, 75.6972], 13);
L.tileLayer('http://tiles.mapc.org/basemap/{z}/{x}/{y}.png',
  {
    attribution: 'Tiles by <a href="http://mapc.org">MAPC</a>, Data by <a href="http://mass.gov/mgis">MassGIS</a>',
    maxZoom: 17,
    minZoom: 9
  }).addTo(map);
</script>

</body>


</html>
