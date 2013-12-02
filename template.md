## Basemap Gallery ##
### `basemaps` ###
- Type: []
- Optional; 
- Default:   
An array of user-defined basemaps to display in the BasemapGallery.

```json
"basemaps": [{
    "layers": [{
      "url": "http://server.arcgisonline.com/ArcGIS/rest/services/World_Street_Map/MapServer"
    }],
    "title": "Street (Customized)",
    "thumbnailUrl": "images/streets.jpg"
  }, {
    "layers": [{
      "url": "http://server.arcgisonline.com/ArcGIS/rest/services/World_Topo_Map/MapServer"
    }],
    "title": "Topo (Customized)",
    "thumbnailUrl": "images/topo.jpg"
  }, {
    "layers": [{
      "url": "http://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer"
    }]
```