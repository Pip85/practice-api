# python-api-challenge
This challenge was in two parts.  The first found in the WeatherPy notebook and the second in the VacationPy notebook.

Part one involed pulling 1,500 random latitude and longitude coordinates using Numpy.  
These coordinates were then run through the Python Citipy library to obtain the closest cities to the coordinates.
Of the 1,500 coordinates, only a little more than 600 cities were identified.  The cities were stored in a list.

A loop was utilized to run the cities through the OpenWeatherMap API.  Information on temperature, humidity, cloudiness,
wind speed and more was captured from the API and stored in separate lists.  Conditional statements and try and except
were used to keep the code moving and avoid duplication of cities.

The list information was then compiled into a dataframe.  The dataframe header and statistical information were displayed.

A check for humidity was made to ensure none of the cities had over 100% humidity.  None were found.

Scatter plots were created to compare the various information with latitude of the cities.  Plots included comparisons
of max temperature, humidity, cloudiness and wind speed with latitude.  A brief analysis was included with each
scatter plot.

The data frame was split between cities in the northern hemisphere and those in the southern hemisphere.  Plots and
linear regression were then prepared for latitude vs temperature, humidity, cloudiness and wind speed with latitude for
each hemisphere.  A brief analysis was included with each plot, along with a print of the r-value.  

All plot images were saved in an output folder along with a .csv of the city dataframe.

Part two, began by reading the .csv file created in part one into a new dataframe.  

Using the new dataframe, a Google heatmap was created for all city locations.

A new dataframe was created by narrowing down the cities according to ideal weather conditions.  This resulted in
a dataframe of only 8 cities.

Using Google Places API, a search was done on each city in the narrowed dataframe to find the nearest hotel for each city.
A new column was created in the dataframe and populated with the hotel name for each of the cities.

Another Google heatmap was created to mirror the first one.  Markers were then generated based on the hotel coordinates and
layered over the heatmap.

A png file of both heatmaps was saved within the VacationPy folder.