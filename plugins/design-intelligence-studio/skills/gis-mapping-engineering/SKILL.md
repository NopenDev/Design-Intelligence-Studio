---
name: gis-mapping-engineering
description: "Use when working with geographic or spatial data, GIS databases, coordinate systems, geocoding, spatial analysis, map services, interactive web maps, routing, or cartographic map design."
---

# GIS & Mapping Engineering

Treat maps as spatial systems, not decorative charts. Own the spatial data path from source and coordinate reference system through storage, analysis, delivery, rendering, and verification.

## 1. Decide whether a map is appropriate

Start with the decision or task the user needs to complete. Use a map when location, distance, adjacency, movement, route, or spatial pattern is essential. For simple comparisons or rankings by region, a table or chart may communicate more clearly. Distinguish an analytical map from a product map used for search, navigation, editing, or operational monitoring.

## 2. Inventory spatial evidence

For every source, record:
- provider, dataset name, version/date, update cadence, license, attribution, and permitted use;
- geometry type and dimensionality (point, line, polygon, raster, 3D/temporal where relevant);
- coordinate reference system (CRS), datum, axis order, units, extent, and resolution;
- attribute definitions, missing values, precision, positional accuracy, and known limitations;
- provenance and transformation steps.

Never assume that coordinates are WGS84, that two layers share a CRS, or that a web basemap permits unrestricted caching or redistribution.

## 3. Spatial data engineering

- Choose formats based on access pattern and scale: GeoJSON for interoperable small-to-medium web features; GeoPackage/GeoParquet for managed analytical data; Cloud Optimized GeoTIFF for raster; vector/raster tiles or PMTiles for high-volume delivery.
- Validate geometry type, validity, topology, bounds, null geometry, coordinate ranges, and duplicate features before processing.
- Transform to an appropriate projected CRS before planar distance/area calculations. Use geodesic/geography-aware methods where the region and metric require them. Preserve SRID metadata throughout.
- Use PostGIS or another spatial database when repeated spatial queries, concurrent editing, or indexed joins justify it. Add spatial indexes and confirm plans with representative queries.
- For raster workflows, track cell size, alignment, nodata, resampling method, scale, and units. Do not silently mix resolutions or grid origins.
- Keep ETL reproducible: pin source versions, record parameters, validate outputs, and preserve metadata and attribution.

## 4. Spatial analysis

Choose the operation to match the question: spatial join, intersect, containment, buffer, nearest-neighbor, overlay, dissolve, network routing, raster map algebra, zonal statistics, interpolation, clustering, or spatial statistics. Check geometry validity, boundary effects, projection distortion, sample bias, and scale. Report assumptions and uncertainty; do not present a spatial correlation as causation.

## 5. Map product and rendering

Select technology from verified constraints, not brand preference:
- Leaflet for a straightforward interactive 2D map and modest feature volumes;
- MapLibre GL JS for vector-tile styling and data-driven WebGL maps;
- OpenLayers for complex GIS layers, projections, and OGC service workflows;
- deck.gl for large/high-volume interactive layers and GPU-assisted visualization;
- CesiumJS for 3D globe, terrain, and 3D Tiles;
- hosted platforms (for example Google Maps or ArcGIS) when their data, routing, support, or service contract is genuinely required.

For every map specify initial extent, zoom behavior, basemap, layer order, legend, labels, units, selection/highlight state, popup content, loading/error state, and mobile/touch behavior. Use clustering, aggregation, vector tiles, or server-side filtering when raw feature rendering overwhelms the client. Do not send massive unfiltered GeoJSON payloads to the browser.

## 6. Cartographic integrity and accessibility

- Choose projection and classification based on geography and analytical purpose.
- For choropleths, normalize counts when population/area/exposure is the meaningful denominator; state the denominator and classification method.
- Use perceptually ordered or diverging ramps that match the data semantics; identify no-data separately from zero/lowest values.
- Keep legends, scale, units, source/date, uncertainty, and caveats visible.
- Do not use color as the only signal. Provide keyboard-accessible map controls and a non-map list/table alternative for critical information.
- Provide attribution and honor data/provider terms. Treat precise location and movement histories as sensitive data; minimize precision and retention when appropriate.

## 7. Verification

Test CRS and bounds with known control points, compare sample features to source attributes, inspect layer alignment, verify query plans and tile payload sizes, and test map behavior at mobile and desktop sizes. Confirm that filtering, selection, zoom, and popups correspond to the same underlying feature IDs. Document unverified assumptions.

## Output contract

For a GIS solution, report data sources and licenses, CRS, chosen formats/storage, spatial operations, map stack and why it fits, scale/performance strategy, cartographic decisions, risks, and reproducible validation steps. Separate confirmed facts from estimates.

## Boundaries and routing

- General software structure and service boundaries → `software-architecture-code-engineering`.
- Implementing non-spatial application code → `frontend-backend-engineering`.
- Non-spatial dashboards and statistical storytelling → `data-visualization-analytics`.
- General UI foundations and interaction design → the relevant UI/UX skill.
- Do not map sensitive locations at exact precision unless the task and permissions justify it.
