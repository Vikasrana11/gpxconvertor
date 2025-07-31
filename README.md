Project Description: GPX to KML Converter with Multi-File Support and Interactive Map
This project is a web-based application designed to convert GPX (GPS Exchange Format) files into KML (Keyhole Markup Language) files, with support for processing multiple GPX files simultaneously. It features an interactive map interface built with OpenLayers, allowing users to visualize GPX data (tracks, waypoints, and stop points) on either an OpenStreetMap (OSM) or Google Satellite Imagery base layer, toggleable via a Bootstrap-styled switch button. The application provides detailed summaries of GPX data, interactive popups for map features, and options to download individual or batch KML files for use in tools like Google Earth.

Key Features

GPX File Parsing and Multi-File Support:

Users can upload one or multiple GPX files through a file input field (accept=".gpx").
The application parses GPX files to extract track points (trkpt), waypoints (wpt), and metadata (e.g., time, elevation).
Track points are processed to calculate:

Total distance using the Haversine formula.
Speed between consecutive points (in km/h).
Stop points where speed is 0 km/h.
Elevation (min, max) and timestamps converted to Indian Standard Time (IST).


Waypoints are identified and displayed with names if available.


Interactive Map with Layer Switching:

The map is powered by OpenLayers (v7.5.2) and displays by default on page load, centered at coordinates [80.3, 19.8] (central India) with a zoom level of 10.
Two base map layers are available:

OpenStreetMap (OSM): A default, open-source map layer (ol.source.OSM).
Google Satellite Imagery: Uses Google Maps tiles (lyrs=s) for high-resolution satellite views.


A toggle switch (Bootstrap form-switch) allows users to switch between OSM and Google Satellite layers. The switch is styled with labels that highlight the active layer in bold blue text.
When GPX files are loaded, the map automatically zooms to fit the extent of the loaded features with padding for better visibility (max zoom: 15).


Map Feature Visualization:

Track Points: Displayed as blue circles, with the first point as a green circle (start) and the last as a red circle (end).
Stop Points: Yellow circles where speed is 0 km/h.
Waypoints: Marked with a custom icon (from Flaticon).
Tracks: Red lines connecting track points.
A legend (displayed when GPX files are loaded) explains the symbols used for each feature type.
Popups: Clicking a point feature (track point, stop point, or waypoint) displays a popup with details such as latitude, longitude, elevation, IST time, speed, or waypoint name. Popups include a close button ("×").


KML Generation and Download:

Converts parsed GPX data into KML format, preserving styles for tracks, start/end points, stop points, waypoints, and track points.
Supports two download options:

Individual KML: Downloads a KML file for the last uploaded GPX file.
Batch KML: Combines all loaded GPX files into a single KML file.


Uses the File System Access API (showSaveFilePicker) for modern browsers, with fallback to Blob-based downloads for broader compatibility.


Summary Display:

A summary section displays aggregated statistics for all loaded GPX files, including:

Number of tracks, waypoints, track points, and stop points.
Start and end times (in IST).
Minimum and maximum elevation.
Total distance (in km).
Minimum, maximum, and average speed (in km/h).


Updates dynamically as GPX files are loaded or reset.


Reset Functionality:

A "Reset" button clears all loaded data, resets the map to its initial state, clears the file input, disables download buttons, and hides the legend.


Responsive Design:

Built with Bootstrap 5.3.0 for a responsive UI.
The map container, toggle switch, and legend adapt to smaller screens (e.g., mobile devices) by centering elements and removing absolute positioning at screen widths below 768px.


User Interface:

Top Navbar: Includes a non-functional sidebar toggle button (for future sidebar integration) and the app title.
File Input: Allows multiple GPX file uploads.
Download Buttons: For individual and batch KML downloads, enabled only when valid data is loaded.
Map Container: Fixed height of 500px, with the toggle switch in the top-left corner and legend in the top-right corner (when visible).
Summary Section: Displays GPX data statistics in a clean, readable format.
Output Pre: Reserved for potential debug or additional output (currently unused).
