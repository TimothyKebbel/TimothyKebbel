
<html>
<head>
<!-- External Stylesheets -->
<title>Leaflet Map</title>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
</head>
<body>
<div id="map" style="width: 705px; height: 375px; position: relative;"></div>
<!-- Add the Leaflet JavaScript library -->
<script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
<script>
    // Create variable to hold map element, give initial settings to map
    var map = L.map('map',{ center: [42.362432, -71.086086], zoom: 14});
    // Add OpenStreetMap tile layer to map element
    L.tileLayer('http://{s}.tile.osm.org/{z}/{x}/{y}.png', { attribution: '© OpenStreetMap' }).addTo(map);
</script>
</body>
</html>
