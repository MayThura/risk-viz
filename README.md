# Risk Visualization Platform

This project is designed to visualize risk data across different years, showcasing what kinds of disasters and risks have impacted various assets. It presents data in three distinct styles: on a map, in a detailed table, and through data graphs, allowing users to interactively explore and understand the risk factors and ratings associated with different assets.

## Project Overview

This interactive tool enables users to:

- View assets on a map, categorized by the type of business and filtered by year.
- Explore detailed risk factors and ratings for every asset in a selected year.
- Visualize the risk rating of selected assets, locations, or business types through dynamic graphs.

## Main Components

1. RiskMap
- Utilizes react-leaflet to display location data as custom markers on the map.
- Users can select a year via typing or a combo box (material ui autocomplete), influencing which assets are shown.
- Marker clustering (react-leaflet-cluster) improves the user experience by aggregating markers in the same location.
- Marker colors vary based on risk rating values, with colors randomly generated.
- Selecting a marker enlarges it, indicating the current selection.

2. RiskTable
   
- Presents year-specific data in a sortable and filterable table (material react table).
- Data can be sorted by columns like Asset Name, Latitude, Longitude, Business Category, and Risk Rating.
- Filtering capabilities allow users to narrow down the data by Asset Name, Business Category, Risk Rating, and Risk Factors.

3. RiskGraph
- Displays a line graph where the x-axis represents time (years) and the y-axis shows risk rating values (line graph).
- The graph can be adjusted based on three attributes: Asset Name, Location (latitude and longitude), and Business Category, selectable via a toggle button (material toggle button).
- Depending on the selected attribute, a combo box appears for specific value selection (material select).
- Graph data vary with selected attributes, offering insights like average risk ratings per year and top risk factors.

## Live Project

Explore the Risk Visualization Platform live at [Risk Visualization]([url](https://risk-viz-deploy.vercel.app/)).

