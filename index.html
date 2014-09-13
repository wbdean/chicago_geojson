<!DOCTYPE html>
<html>
<meta charset="utf-8">
<title>D3 + Leaflet</title>
<style>

@import url(//cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.2/leaflet.css);


#map {
  width: 960px;
  height: 500px;
}

svg {
  position: relative;
}

path {
  stroke:#fff;
  stroke-width:1;
}

path:hover {
  
  fill: #0BCBD3;
  fill-opacity: .8;
}

#info {
  position: absolute;
  right: 100px;
  height: 52px;
  width: 200px;
  background: #ECECEC;
  z-index: 10;
  top: 100px;
  border-radius: 10px;
  padding:15px;
  text-align: center;
  font-size: 16px;
}

</style>



<h1>D3 + Leaflet</h1>

<div id="map">
  <div id = "info">
    <div id = "communityName">
    </div>
    <div id = "area">
    </div>
  </div>
</div>


<script src="http://d3js.org/d3.v3.min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.2/leaflet.js"></script>
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<script>

//forked from http://bost.ocks.org/mike/leaflet/

 var mapboxTiles = L.tileLayer('https://{s}.tiles.mapbox.com/v3/cwhong.map-hziyh867/{z}/{x}/{y}.png', {
        attribution: '<a href="http://www.mapbox.com/about/maps/" target="_blank">Terms &amp; Feedback</a>'
    });

var map = new L.Map("map", {center: [41.8819, -87.6278], zoom: 10})
    .addLayer(mapboxTiles);

var svg = d3.select(map.getPanes().overlayPane).append("svg"),
    g = svg.append("g").attr("class", "leaflet-zoom-hide");




d3.json("chicagoCommunities.geojson", function(collection) {

  var max = d3.max(collection.features, function(d){
    return d.properties.shape_area;
  });

  var min = d3.min(collection.features, function(d){
    return d.properties.shape_area;
  });

  console.log(max + " " + min);

  var color = d3.scale.linear()
    .domain([min,max])
    .range(['rgb(255,255,204)','rgb(35,132,67)']);

  console.log(collection);
  var transform = d3.geo.transform({point: projectPoint}),
      path = d3.geo.path().projection(transform);

  var feature = g.selectAll("path")
      .data(collection.features)
      .enter()
      .append("path")
      .attr('fill',function(d){
        console.log(color(d.properties.shape_area));
        return color(d.properties.shape_area);
      })
      .on('mouseover', function(d) {
        $('#communityName').text(d.properties.community);
        $('#area').text(d.properties.shape_area);
      });

  map.on("viewreset", reset);
  reset();

  // Reposition the SVG to cover the features.
  function reset() {
    var bounds = path.bounds(collection),
        topLeft = bounds[0],
        bottomRight = bounds[1];

    svg .attr("width", bottomRight[0] - topLeft[0])
        .attr("height", bottomRight[1] - topLeft[1])
        .style("left", topLeft[0] + "px")
        .style("top", topLeft[1] + "px");

    g   .attr("transform", "translate(" + -topLeft[0] + "," + -topLeft[1] + ")");

    feature.attr("d", path);
  }

  // Use Leaflet to implement a D3 geometric transformation.
  function projectPoint(x, y) {
    var point = map.latLngToLayerPoint(new L.LatLng(y, x));
    this.stream.point(point.x, point.y);
  }
});

</script>
