# Terrain Analysis: St. Lucia

Raster terrain analysis of St. Lucia using a SRTM 30m Digital Elevation Model (DEM) 
in QGIS. The analysis demonstrates core raster workflows including DEM download, 
hillshade generation, terrain derivative computation, and multi-layer blending.

---

## Data Source

**NASA Shuttle Radar Topography Mission (SRTM) 30m DEM**, downloaded via the 
OpenTopography DEM QGIS plugin.  
[https://portal.opentopography.org](https://portal.opentopography.org)

---

## Methods

A 30m resolution DEM was downloaded for St. Lucia using the OpenTopography DEM 
QGIS plugin and saved as a GeoTIFF (EPSG:4326). A hillshade layer was generated 
using **Raster → Analysis → Hillshade** and blended with the colored DEM using 
Multiply blending mode to create a color relief map. Terrain derivatives including 
aspect and Terrain Ruggedness Index (TRI) were computed using QGIS raster analysis 
tools. Contour lines were extracted using the Contour algorithm under 
**Raster → Extract**.

---

## Analysis

**Digital Elevation Model** — Elevation visualized using a green-to-red color ramp 
draped over a hillshade, revealing St. Lucia's dramatic topography with peak 
elevations of 914m.

**Aspect** — Slope direction mapped from 0–360° using an inverted Spectral color 
ramp blended with hillshade via Multiply mode.

**Terrain Ruggedness Index (TRI)** — Surface complexity mapped from 0–200m. 
High ruggedness values are concentrated near the Pitons volcanic complex in the 
southwest.

---

## Maps

![Digital Elevation Model](st_lucia_DEM.png)

![Aspect Analysis](st_lucia_aspect.png)

![Terrain Ruggedness Index](st_lucia_TRI.png)

---

## Tools & Technologies

- QGIS 3.x
- OpenTopography DEM QGIS plugin
- SRTM 30m DEM (GeoTIFF, EPSG:4326)
- GDAL raster analysis tools
- Google Satellite basemap (XYZ tiles)
