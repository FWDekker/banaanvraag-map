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


## Guidelines
### Performance
The map editing tool doesn't have great performance. Therefore, if you are done editing the map and want to share the file
* set `Layers > Displayed layers` to disable all layers except `Borders`, `Labels`, and `Icons` (and `Religions` if it's stuck),
* set `Style > Style preset` to `Clean`, and
* set `Options > Rendering` to `Best performance`.

### Colour schemes
States are coloured according to [Colorcet's Glasbey colormap](https://colorcet.holoviz.org/user_guide/Categorical.html), which provides 256 distinct colours. You can view the colormap in Python as follows:

1. (Shell) Install Colorcet (in a venv).
   ```shell
   $ python3 -m venv colorcet_venv
   $ source colorcet_venv/bin/activate
   $ python3 -m pip install colorcet
   ```
2. (Python) Display colors.
   ```python
   >>> import colorcet as cc
   >>> cc.glasbey
   ```

If you add a new state, and there are now `n` states, use the `n`th colour in the set of Colorcet's Glasbey colormap.


## Export
### Formats
Though Azgaar supports exporting as PNG or JPG, those options explort only the current view. To get the entire map, some specific instructions are required.

#### SVG
1. Click `Export`, and click `.svg`. Done!

Unfortunately, SVGs exported from Azgaar v1.93.04 look different when loaded with Inkscape v1.2.2. Most notably, nation labels look considerably worse.

#### PNG
1. Click `Export`, select `tiles`, set `Columns` to `2`, `Rows` to `2`, and `Scale` to `1`, and click `Download`.
2. Extract the downloaded `.zip`, delete `fmg_tile_schema.png`, and join the images using ImageMagick command
   ```shell
   montage fmg*.png -geometry +0 banaanvraag.png
   ```

### Layouts
#### For releases
1. Set `Layers > Displayed layers` to `Texture`, `Biomes`, `Wind Rose`, `Rivers`, `Relief`, `Borders`, and `Labels`.
2. Set `Style > Style preset` to `Pale`.
3. Set `Style > Labels > states > Font` to `Almendra SC`.
4. Set `Style > Labels > states > Font size` to `18`.
5. Set `Style > Labels > states > Filter` to `Shadow 2`.
6. Set `Style > Labels > cities > Opacity` to `0`.
7. Set `Style > Labels > towns > Opacity` to `0`.
8. Set `Style > Ocean > Pattern` to `Kiwiroo`.
9. Set `Style > Ocean > Ocean layers` to `Standard 3`.
10. Set `Options > Rendering` to `Best Quality`.
11. Export as SVG and as PNG.

#### For NationStates
1. Set `Layers > Displayed layers` to `States` and `Labels`.
2. Set `Style > Style preset` to `Clean`.
3. Set `Style > Labels > states > Font size` to `18`.
4. Set `Style > Labels > cities > Opacity` to `0`.
5. Set `Style > Labels > towns > Opacity` to `0`.
6. Set `Options > Rendering` to `Best Quality`.
7. Export as PNG.
