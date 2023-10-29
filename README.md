Official map for the NationStates [Banaanvraag](https://nationstates.net/region=Banaanvraag) region.


## Usage
To download a `.png` or `.svg` of the map, check the [releases](https://github.com/FWDekker/banaanvraag-map/releases).

To edit the map, download [`banaanvraag.map`](https://github.com/FWDekker/banaanvraag-map/blob/main/banaanvraag.map) and open the map using the [Azgaar fantasy map generator](https://azgaar.github.io/Fantasy-Map-Generator/).


## Limitations
### Subject to change
The following are canonical and complete, but may be retconned.

* Height maps
* Rivers

### Incomplete
* Capital city names
* Capital city locations (unless noted otherwise)
* Non-capital cities
* Provinces

### Non-canonical
* Biomes
* City statistics
* Climate
* Diplomacy


## Export
Exported maps should use _Layers preset_ "Default".

Azgaar has built-in support for exporting to SVG. However, SVGs exported from Azgaar v1.93.04 look different when loaded with Inkscape v1.2.2. Most notably, nation labels looks worse.

Azgaar also supports exporting as PNG or JPG. By default, only the current view is exported. To export the entire map, export as "Tiled". Releases should export 2x2 tiles at a scale of 1, resulting in a 3000x3000 image. After discarding `fmg_tile_schema.png`, the resulting images can be stitched together with ImageMagick: `montage fmg*.png -geometry +0 banaanvraag.png`.
