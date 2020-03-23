<html>

<head>

<link rel="stylesheet" href="./Leaflet-1.0.3/leaflet.css"/>
<script src="./Leaflet-1.0.3/leaflet.js"></script>
<!-- map style  -->  
<style>
div#map{ height: 250px; }
</style>

</head>

<body>

<div id="map"></div>
<!-- create the map -->
<!--L.tilelayer example with mapbox api-->
<script>
var map = L.map('map').setView([45.4215, 75.6972], 13);
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
}).addTo(map);
</script>

</body>


</html>
