# Mangrove Vector Analysis
### Southeast Asia & Western Pacific

This project quantifies mangrove coverage within Large Marine Ecosystem (LME) buffer zones across Southeast Asia and the Western Pacific using QGIS vector analysis tools. The analysis demonstrates a complete spatial workflow from raw shapefiles to area calculations and choropleth mapping.

---

## Data Sources

- **Mangrove data**: Global Mangrove Watch (GMW), accessed via course data repository
- **Large Marine Ecosystems**: LME66 dataset, NOAA
- **World boundaries**: Natural Earth world polygon dataset

---

## Methods

All layers were clipped to a defined study area mask covering Southeast Asia and the Western Pacific. The LME layer was reprojected to EPSG:3857 (Web Mercator) to enable distance-based analysis in meters. A 5km buffer was created around each LME boundary and intersected with the clipped mangrove layer to identify mangrove coverage within proximity of Large Marine Ecosystems.

Area calculations were performed using the QGIS Field Calculator (`$area / 1000000`) to convert square meters to square kilometers. Mangrove area was then summarized by country using the Statistics by Categories tool, after spatially joining country ISO3 codes to the mangrove layer via Join Attributes by Location.

For visualization, the world layer was dissolved by ISO3 country code and joined with the country-level mangrove statistics to produce a graduated choropleth map.

**Total mangrove area within 5km of LMEs in the study area: 62,057 sq km**

---

## Maps

**Figure 1 — Mangrove Coverage by Country**
Graduated choropleth showing total mangrove area (sq km) per country within the study area. Indonesia and Australia contain the largest mangrove coverage in the region. Yellow polygons show the actual mangrove distribution along coastlines; white lines indicate LME 5km buffer zone boundaries.

![Mangrove Coverage by Country](mangrove-coverage-by-country.png)

---

**Figure 2 — Large Marine Ecosystems & Mangrove Distribution**
Overview map showing the spatial relationship between Large Marine Ecosystems (blue), country boundaries (tan), and mangrove distribution (yellow) across the study area. Mangroves are concentrated along the coastlines of the Malay Peninsula, Sumatra, Borneo, and northern Australia.

![LME and Mangrove Distribution](lme-mangrove-distribution.png)

---

## Key Findings

- Total mangrove area within 5km of Large Marine Ecosystems in the study area: **62,057 sq km**
- Indonesia has the largest mangrove coverage in the region, followed by Australia and Myanmar
- Mangroves are concentrated along sheltered coastlines, estuaries, and island archipelagos throughout Southeast Asia
- The high overlap between mangrove distribution and LME buffer zones highlights the ecological connectivity between coastal mangrove ecosystems and adjacent marine environments

---

## Tools & Technologies

- QGIS 3.x
- Vector analysis: Clip, Buffer, Intersect, Dissolve, Spatial Join
- Field Calculator for area computation
- CRS: EPSG:4326 (WGS 84), EPSG:3857 (Web Mercator) for buffer analysis
- Google Satellite basemap (XYZ tiles)
