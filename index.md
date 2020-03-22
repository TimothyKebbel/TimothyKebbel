<!DOCTYPE html>

<html>
<head>
  <title>My first leaflet webviewer</title>
  <!--Load leaflet -->
  <script src="https://unpkg.com/leaflet@1.3.1/dist/leaflet.js" integrity="sha512-/Nsx9X4HebavoBvEBuyp3I7od5tA0UzAxs+j83KgC8PU0kgB4XiK4Lfe4y4cgBtaRJQEIFCW+oC506aPT2L1zw==" crossorigin=""></script>
  <!--Load vectorGrid plugin for Leaflet -->
  <script src="https://unpkg.com/leaflet.vectorgrid@latest/dist/Leaflet.VectorGrid.bundled.js"></script>
  <!--Load the style stylesheet of leaflet -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.3.1/dist/leaflet.css" integrity="sha512-Rksm5RenBEKSKFjgI3a41vrjkw4EVPlJ3+OiI65vTjIdo9brlAacEuKOiQ5OFh7cOI1bkDwLqdLw3Zg0cRJAAQ==" crossorigin=""/>

  <style>
  *Set the dimensions of our map /*
    .map {
      height: 50%;
      width: 50%;
    }
    </style>

</head>

<body>
  <!--Create our map object  -->
  <div id="map" class="map"></div>
</body>
</html>

<script>
// Find our map id
var map = L.map('map')
// Set open openstreetmap
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);

// Set vectorTileOptions
var vectorTileOptions = {
vectorTileLayerStyles: {
'water-bodies': function() {
return {
  color: 'red',
  opacity: 1,
  fillColor: 'yellow',
  fill: true,
}
},
},
interactive: true,	// Make sure that this VectorGrid fires mouse/pointer events
}

// Set the coordinate system
var projection_epsg_no = '32189';
// Set the variable for storing the workspace:layername
var waterbodies_geoserverlayer = 'water-bodies';
// Creating the full vectorTile url
var waterURL = '/geoserver/gwc/service/tms/1.0.0/' + waterbodies_geoserverlayer + '@EPSG%3A' + projection_epsg_no + '@pbf/{z}/{x}/{-y}.pbf';
// Creating the Leaflet vectorGrid object
var water_vectorgrid = L.vectorGrid.protobuf(waterURL, vectorTileOptions)

// Define the action taken once a polygon is clicked. In this case we will create a popup with the camping name
water_vectorgrid.on('click', function(e) {
    L.popup()
      .setContent(e.layer.properties.naamnl)
      .setLatLng(e.latlng)
      .openOn(map);
  })
  .addTo(map);

// Add the vectorGrid to the map
water_vectorgrid.addTo(map);

// Set the map view. In this case we set it to the Netherlands
map.setView([45,75], 5);

</script>
