# Green Sea Turtle Migration & Habitat Use
### *Chelonia mydas* — Chagos Archipelago, Western Indian Ocean

This project visualizes satellite telemetry data from green sea turtles tagged at the Chagos Archipelago (British Indian Ocean Territory) using QGIS. The analysis demonstrates GPS data processing workflows, vector styling, and spatial density estimation applied to marine wildlife tracking data.

---

## Data Source

Hays GC, Esteban N, Rattray A. 2024. Data from: Study "Green turtles (*Chelonia Mydas*); Hays; Chagos Archipelago, Western Indian Ocean". Movebank Data Repository.  
[https://doi.org/10.5441/001/1.313](https://doi.org/10.5441/001/1.313)

---

## Methods

GPS tracking data were downloaded as a `.csv` file from the Movebank Data Repository and imported into QGIS using the Delimited Text import tool with EPSG:4326 (WGS 84) as the coordinate reference system. Individual turtle tracks were classified by tag identifier and symbolized using categorized random colors.

Migration path lines were generated using the **Points to Path** algorithm in the QGIS Processing Toolbox, grouped by `tag-local-identifier` to produce individual trajectory lines per turtle. A kernel density heatmap was applied to the full point dataset, weighted by GPS satellite count, to identify spatial concentrations of habitat use.

The data were also converted from `.csv` to `.gpx` format using GPS Visualizer to demonstrate native GPS file workflows.

---

## Maps

**Figure 1 — Individual Migration Tracks**  
Each color represents a unique tagged individual. Tracks radiate outward from the Chagos Archipelago tagging site across the Western Indian Ocean toward foraging grounds along the East African coast and surrounding seamounts.

![Migration Tracks](migration-tracks.png)

---

**Figure 2 — Habitat Use & Migration (Heatmap + Paths)**  
Kernel density heatmap overlaid with migration path lines. The intense red hotspot at Chagos reflects the high density of GPS fixes at the nesting/tagging site. Softer pink regions indicate foraging area concentrations west of the archipelago.

![Habitat Use and Migration](habitat-use-migration.png)

---

**Figure 3 — Chagos Departure Tracks & Foraging Hotspots**  
Zoomed view centered on the Chagos Archipelago showing individual departure trajectories and nearby foraging hotspots. The bathymetric texture of the satellite basemap reveals the mid-ocean ridge system that the turtles navigate across during migration.

![Chagos Departure Tracks](chagos-departure-tracks.png)

---

## Key Findings

- Tagged turtles dispersed across a vast area of the Western Indian Ocean, with some individuals traveling over 3,000 km from the tagging site
- Primary foraging hotspots are concentrated along the East African continental shelf and adjacent seamount systems
- The Chagos Archipelago serves as a critical nesting hub, with turtles converging on the site from widely distributed foraging grounds
- Individual movement strategies vary substantially, with some turtles following direct routes and others displaying complex, localized foraging behavior

---

## Tools & Technologies

- QGIS 3.x
- Movebank GPS telemetry data (.csv, .gpx)
- Google Satellite basemap (XYZ tiles)
- CRS: EPSG:4326 WGS 84
