# FCT Healthcare Accessibility Dashboard

A mobile-friendly Leaflet dashboard for the Federal Capital Territory, Abuja.

## Included
- OpenStreetMap basemap
- Area Council PHC summaries, 652 facility overview, 62 analyzed wards
- Filters for Area Council and facility level
- GeoJSON file upload and auto-loading of `data/wards.geojson` and `data/facilities.geojson` when provided

## Important data note
The current package contains verified summary statistics, **not** the complete PostGIS spatial exports. Until you add GeoJSON files, the map shows its basemap and summary figures, but no ward boundaries or facility points. The dashboard is a static snapshot, not a live PostGIS connection.

## Publish on GitHub Pages
1. Upload `index.html`, `README.md`, and optionally the `data` folder to the root of `Roizay93/fct-healthcare-dashboard`.
2. In repository **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
3. Visit `https://roizay93.github.io/fct-healthcare-dashboard/` once GitHub reports that the site has deployed.

## Adding spatial data
Export ward polygon features to `data/wards.geojson` with properties `ward`, `council`, `population`, `phcs`, `required`, `deficit`.
Export facility points to `data/facilities.geojson` with properties `name`, `level`, `council`.
Both GeoJSON files must use WGS84 coordinates (longitude, latitude; EPSG:4326). Do not publish private patient data or database credentials.

## Source summary
PostGIS snapshot: 652 facilities (544 primary, 100 secondary, 8 tertiary); 62 wards; 9 wards with deficits; summed ward PHC deficit of 52. Council PHC counts are ward analysis totals and need not match the full facility table exactly.
