Project Description: GPX to KML Converter with Multi-File Support and Interactive Map
This project is a web-based application designed to convert GPX (GPS Exchange Format) files into KML (Keyhole Markup Language) files, with support for processing multiple GPX files simultaneously. It features an interactive map interface built with OpenLayers, allowing users to visualize GPX data (tracks, waypoints, and stop points) on either an OpenStreetMap (OSM) or Google Satellite Imagery base layer, toggleable via a Bootstrap-styled switch button. The application provides detailed summaries of GPX data, interactive popups for map features, and options to download individual or batch KML files for use in tools like Google Earth.


Summary Display:

A summary section displays aggregated statistics for all loaded GPX files, including:

Number of tracks, waypoints, track points, and stop points.
Start and end times (in IST).
Minimum and maximum elevation.
Total distance (in km).
Minimum, maximum, and average speed (in km/h).


User Interface:

Top Navbar: Includes a non-functional sidebar toggle button (for future sidebar integration) and the app title.
File Input: Allows multiple GPX file uploads.
Download Buttons: For individual and batch KML downloads, enabled only when valid data is loaded.
Map Container: Fixed height of 500px, with the toggle switch in the top-left corner and legend in the top-right corner (when visible).
Summary Section: Displays GPX data statistics in a clean, readable format.
Output Pre: Reserved for potential debug or additional output (currently unused).
