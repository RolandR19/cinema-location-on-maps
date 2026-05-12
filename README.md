🎬 Global Cinematic Data Explorer

This project is a high-performance, open-source geographic intelligence tool designed to visualize and analyze filming locations worldwide. By merging professional mapping engines with real-time data science visualizations, it transforms static movie metadata into an interactive analytical experience.

🧠 Project Core Logic

The application operates on a Reactive Filtering Engine. Unlike standard maps, every interaction (searching, moving a slider, or toggling a genre) triggers a global state update that synchronizes three distinct layers:

The Spatial Layer (OpenStreetMap): Dynamically plots GPS coordinates onto a fluid 2D map using Leaflet.js. It uses "jitter" algorithms to prevent marker overlapping in dense filming hubs like San Francisco or Vancouver.

The Analytical Layer (Chart.js): Generates live statistical distributions. It calculates the quality density (IMDb scores) and the production volume (Time-series) of the currently filtered dataset.

The Information Layer (UI/Tray): Renders a synchronized list of technical cards containing deep metadata, including directors, full casting, and production studios.

🛠️ Technical Implementation

Geographic Engine

Source: Powered by OpenStreetMap (OSM) tiles via the CartoDB "Voyager" provider for a clean, editorial look.

Interaction: Implements flyTo logic for smooth cinematic transitions between different global filming sites.

Data Science Dashboard

Multidimensional Filtering: Allows users to cross-reference data across three axes:

Temporal: Range-based year filtering.

Qualitative: Minimum IMDb score thresholding.

Categorical: Cluster-based genre selection.

Dynamic Charting: The bar and line charts aren't static images; they are re-rendered on-the-fly as the data subset changes.

Holistic Search Moteur

The search logic uses a consolidated string matching algorithm. It doesn't just look for titles; it scans through:

People: Directors, Writers, and Actors (1, 2, and 3).

Entities: Production companies and distributors.

Geography: Street-level locations and city names.

📊 Data Schema

The underlying engine processes JSON objects with the following structure:

Field

Purpose

title

Primary identifier for the production.

release_year

Integer used for temporal time-series mapping.

imdb_rating

Floating-point value for qualitative filtering.

genres

Array of strings for categorical clustering.

latitude / longitude

Precise decimal coordinates for spatial plotting.

director / casting

Relational data for the search engine.

fun_facts

Qualitative anecdotal data for user engagement.

🚀 Deployment

The project is architected as a Single-File Application (SFA). This means all logic, styles (Tailwind CSS), and mapping dependencies are bundled into one autonomous HTML file, requiring no backend or API keys to function, ensuring total privacy and portability.

Developed to bridge the gap between geographic information systems (GIS) and cinematic archives.
