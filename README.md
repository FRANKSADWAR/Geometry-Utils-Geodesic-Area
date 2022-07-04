# Geometry-Utils-Geodesic-Area
Geodesic area formulae


Compute geodesic areas on draw using leaflet geoman



map.on('pm:create', (ec)=> {

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
  
  
  
