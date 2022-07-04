# Geometry-Utils-Geodesic-Area
Geodesic area formulae


Compute geodesic areas on draw using leaflet geoman












map.pm.addControls({
    position: 'topleft',
    drawMarker: false,
    drawCircleMarker: true,
    drawPolyline: true,
    drawRectangle: true,
    drawPolygon: true,
    drawCircle: true,
    editMode: true,
    dragMode: true,
    cutPolygon: true,
    removalMode: true,
    rotateMode: true,
    drawControls: true,
    editControls: true,
    customControls: true,
    optionsControls: true,
    pinningControls: true,
    snappingOption: true,
    splitMode: true,
    scaleMode: true,
    oneBlock: true
});

map.on('pm:create', (ec)=>
  {
    var shape = ec.shape;
    var layer = ec.layer;
    var all_latlngs, area;
    
    if( shape === "Rectangle"){
      all_latlngs = layer._latlngs[0];
      area = L.GeometryUtil.geodesicArea(all_latlngs).toFixed(4);
      layer.bindPopup(area.toString()).openPopup();
    } 
    else {
      // do the same for circles, polygons, 
    }
  });
