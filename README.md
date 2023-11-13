Official map for the NationStates [Banaanvraag](https://nationstates.net/region=Banaanvraag) region.


## Usage
To download a `.png` or `.svg` of the map, check the [releases](https://github.com/FWDekker/banaanvraag-map/releases).

To edit the map, download [`banaanvraag.map`](https://github.com/FWDekker/banaanvraag-map/blob/main/banaanvraag.map) and open the map using [Azgaar's fantasy map generator](https://azgaar.github.io/Fantasy-Map-Generator/).


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


## Guidelines
### Performance
The map editing tool doesn't have great performance.
The editor's wiki [has an article with tips about performance](https://github.com/Azgaar/Fantasy-Map-Generator/wiki/Tips#performance-tips).
Additionally, it may help to set `Options > Rendering` to `Best performance`.

If you are done editing the map and want to share the file,
* set `Layers > Displayed layers` to disable all layers except `States` and `Labels`, and
* set `Style > Style preset` to `Clean` or to the custom `NationStates` preset described below.

### Colour schemes
States are coloured according to [Colorcet's Glasbey colourmap](https://colorcet.holoviz.org/user_guide/Categorical.html), which provides 256 distinct colours.
[You can see the list of colours here.](https://github.com/FWDekker/banaanvraag-map/blob/main/resources/glasbey.txt)
If you add a new state, and there are now `n` states, use the `n`th colour in the set of Colorcet's Glasbey colormap.


## Export
This section describes the reproducible export procedure for the official map images.
As of Azgaar v1.93.11, using Firefox is preferred over Chromium because the `Release` export is considerably faster.

### Image formats
#### SVG
1. Click `Export`, and click `.svg`.
   Done!

Unfortunately, SVGs exported from Azgaar v1.93.04 look different when loaded with Inkscape v1.2.2.
Most notably, nation labels look considerably worse.

#### PNG
To export the entire map as PNG:
1. Click `Export`, select `tiles`, set `Columns` to `2`, `Rows` to `2`, and `Scale` to `1`, and click `Download`.
2. Extract the downloaded `.zip`, delete `fmg_tile_schema.png`, and join the images using ImageMagick command
   ```shell
   montage fmg*.png -geometry +0 banaanvraag.png
   ```

### Appearance
#### For NationStates
The NationStates style contains very little detail and simple, distinct colours.

1. Set `Options > Rendering` to `Best quality`.
2. Use the [`NationStates` style preset](https://github.com/FWDekker/banaanvraag-map/blob/main/resources/styles/NationStates.json), or recreate it as follows:
   1. Set `Style > Style preset` to `Clean`.
   2. Set `Style > Labels > states > Font size` to `18`.
   3. Set `Style > Labels > cities > Opacity` to `0`.
   4. Set `Style > Labels > towns > Opacity` to `0`.
   5. (Optional) Save the style preset.
3. Set `Layers > Displayed layers` to `States` and `Labels`.
4. (Optional) Save the layers preset.
5. Export in the desired image format(s).

#### For releases
The official release is supposed to look good, but may take a long time to export.

1. Set `Options > Rendering` to `Best quality`.
2. Use the [`Release` style preset](https://github.com/FWDekker/banaanvraag-map/blob/main/resources/styles/Release.json), or recreate it as follows:
   1. Set `Style > Style preset` to `Pale`.
   2. Set `Style > Labels > states > Font` to `Almendra SC`.
   3. Set `Style > Labels > states > Font size` to `18`.
   4. Set `Style > Labels > states > Filter` to `Shadow 2`.
   5. Set `Style > Labels > cities > Opacity` to `0`.
   6. Set `Style > Labels > towns > Opacity` to `0`.
   7. (Optional) Save the style preset.
3. Set `Layers > Displayed layers` to `Texture`, `Biomes`, `Wind Rose`, `Rivers`, `Relief`, `Borders`, and `Labels`.
4. (Optional) Save the layers preset.
5. Export in the desired image format(s).
   This may take several minutes.
