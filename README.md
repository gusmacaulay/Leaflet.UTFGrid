# Leaflet.UTFGrid

Provides a [UTFGrid](https://github.com/mapbox/utfgrid-spec) implementation for Leaflet 1.0.

```L.UTFGrid``` provides basic UTFGrid functionality including hover and click events.

```L.UTFGridCanvas``` provides highlighting of areas using ```<canvas>``` tiles.  Optionally can highlight entire 
feature, not just the portion of it within a single tile.
 

See the [example](//consbio.github.io/Leaflet.UTFGrid).

*Only supports Leaflet 1.0*  
(tested on Leaflet 1.0 beta 1). 

Note: only supports browsers that provide ```<canvas>```. 




## Usage

Requires [corslite](https://github.com/mapbox/corslite/).


Include the JavaScript:

```
<script src="L.UTFGrid.min.js"></script>
```

Example usage:

```
var utfgrid = L.utfGrid(url, {
    resolution: 4,
    pointerCursor: true,
    mouseInterval: 66  // Delay for mousemove events
});
utfgrid.addTo(map);

utfgrid.on("mouseover", function(e){
    // DO SOMETHING
});

utfgrid.on("mouseout", function(e){
    // DO SOMETHING
});

utfgrid.on("click", function(e){
    // DO SOMETHING
});
```


Using ```<canvas>``` tiles:

```
var utfgrid = L.utfGridCanvas(url, {
    idField: 'ID'  // The sole property in this UTFGrid is called NAME (state name)
    buildIndex: true  //requires above field to be set properly
    fillColor: 'black'
    debug: false  // if true, show tile borders and tile keys
});
```


## Credits:
Developed with support from the [South Atlantic Landscape Conservation Cooperative](http://www.southatlanticlcc.org/)

Core implementation of UTFGrid based on ideas from [Leaflet.utfgrid](https://github.com/danzel/Leaflet.utfgrid) and 
heavily modified to extend Leaflet's builtin ```L.TileLayer```.

Canvas implementation inspired by [Mapbox Glower](https://github.com/mapbox/glower). 