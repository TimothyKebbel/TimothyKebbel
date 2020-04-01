<html>
<head>
  <meta charset="utf-8" />
  <title>Simple FeatureLayer</title>
  <meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />

  <!-- Load Leaflet from CDN -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.6.0/dist/leaflet.css"
  integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ=="
  crossorigin=""/>
  <script src="https://unpkg.com/leaflet@1.6.0/dist/leaflet.js"
  integrity="sha512-gZwIG9x3wUXg2hdXF6+rVkLF/0Vi9U8D2Ntg4Ga5I5BZpVkVxlJWbSQtXPSiUTtC0TjtGOmxa1AJPuV0CPthew=="
  crossorigin=""></script>


  <!-- Load Esri Leaflet from CDN -->
  <script src="https://unpkg.com/esri-leaflet@2.3.3/dist/esri-leaflet.js"
  integrity="sha512-cMQ5e58BDuu1pr9BQ/eGRn6HaR6Olh0ofcHFWe5XesdCITVuSBiBZZbhCijBe5ya238f/zMMRYIMIIg1jxv4sQ=="
  crossorigin=""></script>




  <style>
    body { margin:0; padding:0; }
    #map {
      position: relative;
      height: 500px;
      width: 500px;
      left: 250px;
    }
  </style>
</head>
<body>

<div id="map"></div>

<script>
  var map = L.map('map').setView([37.837, -122.479], 8);

  L.esri.basemapLayer('Streets').addTo(map);

  var iconFs = L.icon({
    iconUrl: 'https://esri.github.io/esri-leaflet/img/earthquake-icon.png',
    iconSize: [27, 31],
    iconAnchor: [13.5, 17.5],
  });

  // a Leaflet marker is used by default to symbolize point features.
  L.esri.featureLayer({
    url: 'https://services1.arcgis.com/0MSEUqKaxRlEPj5g/ArcGIS/rest/services/Coronavirus_2019_nCoV_Cases/FeatureServer/1',
    pointToLayer: function(geojson, latLng) {
      return L.marker(latLng, { icon: conFs});
    }
  }).addTo(map);
</script>

</body>
</html>
