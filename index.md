
<html>

<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>Testing Map</title>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.2.0/leaflet.css" type="text/css" crossorigin="">
<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.2.0/leaflet.js" crossorigin=""></script>
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<link rel="stylesheet" href="style.css" type="text/css">
<script type="text/javascript">

var map;
function init() {
   // create map and set center and zoom level
   map = new L.map('mapid');
   map.setView([39.9526,-75.1652],13);
   // create tile layer and add it to map
   L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
     maxZoom: 19,
     attribution: '&copy; <a href="https://openstreetmap.org/copyright">OpenStreetMap contributors</a>'
   }).addTo(map);
}

</script>
</head>


<body onload="init()">
<h1 id="title">Heading 1</h1>
<div id="mapid">
</div>

<div id="docs">
<p>This page shows farmers markets in Philadelphia, Pennsylvania. Click a market to get more information.</p>
</div>

</body>

</html>
