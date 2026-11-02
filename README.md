# Personal Forecast

A customizable point forecast for friends and family: any place, any time range, a title, an
automatically written summary you can edit, and waves for spots on the water. It runs entirely in the
browser on GitHub Pages; there are no servers, keys or workflows.

## Set up
1. Create a new GitHub repository and upload everything in this folder (with hidden files showing,
   so `docs/.nojekyll` comes along).
2. **Settings → Pages:** Source "Deploy from a branch", branch `main`, folder `/docs`.
3. Open `https://<your-user>.github.io/<repo>/` (add `?demo=1` to try it with made-up data).

## Using it
* **Title:** anything ("Paul's Fishing Forecast"); it heads the page and every product.
* **Place:** search for a town or place, type latitude and longitude, or **Pick on a map**. The place
  name can be edited, and times follow the place's own time zone.
* **Time range:** start and end, or 24 h / 3 / 5 / 7 days; rows **Hourly** or **3-hourly**.
* **Rows:** sky, temperature, dew point, humidity, chances of rain and thunder (1, 3 and 6 hours),
  10 m wind, gusts and direction, and the chance of gusts over 20, 25 and 30 mph.
* **Waves and sea state:** tick it for a point on the water to add wave height, swell, period,
  direction and water temperature (Open-Meteo marine model).
* **Summary:** main concerns and a discussion written from the forecast. Edit either one and your
  text is kept; **Rewrite from the forecast** brings the automatic version back.
* **Edit** any value in the table or graph as on the planning page, then **Save and publish** for PDF,
  Excel, CSV or an interactive HTML page to send. The summary goes on the PDF and HTML.

## Data
Model guidance from Open-Meteo (HRRR, NAM, NBM, GFS, ECMWF IFS and AIFS, ICON, GEM, UKMO and their
ensembles), the NWS forecast (NDFD, from api.weather.gov, US points only), Open-Meteo marine for waves,
and Open-Meteo geocoding for place search. The map uses OpenStreetMap tiles and Leaflet from cdnjs.
Everything you type stays in your browser.

## Updating the code
`docs/guidance.js` and `docs/planning-app.js` are shared with the ER Weather Tools repository
(the page runs them with `window.PAGE = "personal"`). After changing a script, run
`python3 pipeline/stamp_versions.py` so browsers load the new version.
