Risk Visualization Documentation

Main Components Explanation

In this project, there are 3 main components, RiskMap, RiskTable and RiskGraph.

1. RiskMap
   
  a. This is the component which displays the location data extracted from the
provided data set as the markers on the map. (react-leaflet, custom markers)
  b. The location markers are selected and shown according to the year which the
user can type the year or choose from the combo box. (material ui autocomplete)
  c. Due to the redundant appearance of the locations in the data set, the markers
are clustered with the same location so that the user can see all the overlapping
markers by clicking on each cluster. (react-leaflet-cluster)
  d. All the marker colors are different for various risk rating values. The colors are
randomly generated.
  e. Clicking on the marker is regarded as selecting, and thus the size of the marker
is bigger. Unclicking on it will make the size normal which means to be
unselecting.

2. RiskTable

  a. This is the component which displays all the data of the specific year which the
user chose in the previous map page in a table. (material react table)
  b. The user can sort the data based on the reasonable column values such as
Asset Name, Latitude, Longitude, Business Category and Risk Rating. Both
ascending and descending sorting can be used.
  c. The filtering is also possible with the reasonable columns like Asset Name (user
can type to filter), Business Category (user can choose a category to filter), Risk
Rating (user can give minimum and maximum value to filter) and Risk Factors
(user can choose the multiple factors to filter).

3. RiskGraph
   
  a. This component shows the line graph where x-axis represents time (years) and
y-axis represents risk rating value from the provided data set. (line graph)
  b. The graph data can be controlled with 3 attributes, Asset Name, Location (lat,
long) and Business Category. These can be selected on a toggle button with 3
values. (material toggle button)
  c. For each attribute selected, the combo box will appear with the respective data
so that the user can choose a specific value. (material select)
  d. According to the specified value, the graph will vary its shape. The following is
how the algorithm for the graph works for each attribute chosen.

  i. Location given - all the data with the same latitude and longitude will be
extracted and the average/mean value of the risk rating will be calculated
for each year. The tooltip includes the year (x-axis value), average risk
rating (y-axis value), top risk factor and its value, all risk factors for that
location in that year and asset names residing on that location. (custom
tooltip)

  ii. Category given - all the data with the same category will be extracted
and the average/mean value of the risk rating will be calculated for each
year. The tooltip includes the year (x-axis value), average risk rating
(y-axis value), top risk factor and its value, all risk factors for that category
in that year and all asset names belonging in that category.

  iii. Asset Name given - all the data with the same asset name will be
extracted and the average/mean value of the risk rating will be calculated
for each year. The tooltip includes the year (x-axis value), average risk
rating (y-axis value), top risk factor and its value, all risk factors for that
asset in that year and asset name.

Supporting Components Explanation

1. TabComponent
   
  ○ This component integrates the main components discussed above. (material tab)
  
2. data
   
  ○ This helps extract the data from the provided data set. (npm xlsx, parsing xlsx
file)

3. Redux
   
  ○ This is used for centralized state management so that the components can utilize
and update the state easily without any props drilling or lifting up. (redux with next
js)

  ○ In this project, after parsing the data from the xlsx file, it is stored in the redux
state. Every component can access it easily. Additionally, local storage is also
utilized to maintain the persistence of the state even after refreshing.

  ○ Selected year on the map tab is also stored in the store and thus the data in table
representation is filtered only with the ones in the specific year.

  ○ When the user clicks on a marker of the map, since a marker represents an
asset, the selected asset data is stored in the redux store so that the graph
representation is updated with the selected asset data.

How to Run the Project Locally
1. Git clone the project.
2. Go to the root directory of the project and run this command. `npm install`
3. Run this command. `npm run dev`.
4. Open the browser with this. `http://localhost:3000`
