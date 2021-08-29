# **python-api_weather_analysis**

Student project - Analyze, chart and map random coordinates from Citipy library using Open Weather Map API data and Google Maps.

## **software/tools used**

* pandas:  https://pandas.pydata.org/<br>
* Jupyter Notebook:  https://jupyter.org/<br>
* citipy python library:  https://pypi.python.org/pypi/citipy<br>
* jupyter-gmaps:  https://jupyter-gmaps.readthedocs.io/en/latest<br>
* python_pandas libraries:<br>
    * Citipy<br>
    * Matplotlib Pyplot<br>
    * NumPy<br>
    * SciPy stats<br>


## **data resources**

> API - Open Weather Map:  https://openweathermap.org/api<br>
> API - Google Places:  https://cloud.google.com/maps-platform/places<br>
> 

## **project background**<br>

### **Part I - WeatherPy**

* In this example, you'll be creating a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. 
* The first requirement is to create a series of scatter plots to showcase the following relationships:

> * Temperature (F) vs. Latitude
> * Humidity (%) vs. Latitude
> * Cloudiness (%) vs. Latitude
> * Wind Speed (mph) vs. Latitude

* After each plot, add a sentence or two explaining what the code is analyzing.

* The second requirement is to run linear regression on each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

> * Northern Hemisphere - Temperature (F) vs. Latitude
> * Southern Hemisphere - Temperature (F) vs. Latitude
> * Northern Hemisphere - Humidity (%) vs. Latitude
> * Southern Hemisphere - Humidity (%) vs. Latitude
> * Northern Hemisphere - Cloudiness (%) vs. Latitude
> * Southern Hemisphere - Cloudiness (%) vs. Latitude
> * Northern Hemisphere - Wind Speed (mph) vs. Latitude
> * Southern Hemisphere - Wind Speed (mph) vs. Latitude

* After each pair of plots, take the time to explain what the linear regression is modeling. For example, describe any relationships you notice and any other analysis you may have.

### **Part II - VacationPy**

* Now let's use your skills in working with weather data to plan future vacations. Use jupyter-gmaps and the Google Places API for this part of the assignment.

* To complete this part of the assignment,you will need to do the following:

  * Create a heat map that displays the humidity for every city from Part I.

  * Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.
 
* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the hotel name.


## **acknowledgments**

* *Background provided as part of Georgia Tech Data Analytics Boot Camp:*<br>

    © 2021 Trilogy Education Services, LLC, a 2U, Inc. brand. Confidential and Proprietary. All Rights Reserved.

*  Project Author:  Valerie Pippenger - https://github.com/Pip85

## **process**

* This challenge was in two parts.  The first found in the WeatherPy notebook and the second in the VacationPy notebook.

* **Part one** involed pulling 1,500 random latitude and longitude coordinates using Numpy.  
* These coordinates were then run through the Python Citipy library to obtain the closest cities to the coordinates.
* Of the 1,500 coordinates, only a little more than 600 cities were identified.  The cities were stored in a list.
* A loop was utilized to run the cities through the Open Weather Map API.  
* Information on temperature, humidity, cloudiness, wind speed and more was captured from the API and stored in separate lists.  
* Conditional statements and try and except were used to keep the code moving and avoid duplication of cities.
* The list information was then compiled into a dataframe.  The dataframe header and statistical information were displayed.
* A check for humidity was made to ensure none of the cities had over 100% humidity.  None were found.
* Scatter plots were created to compare the various information with latitude of the cities.  Plots included comparisons of max temperature, humidity, cloudiness and wind speed with latitude.  A brief analysis was included with each scatter plot.
* ![humidity](https://github.com/Pip85/python-api_weather_analysis/blob/main/WeatherPy/output_data/City%20Latitude%20vs%20Humidity.png)<br>

* ![wind](https://github.com/Pip85/python-api_weather_analysis/blob/main/WeatherPy/output_data/City%20Latitude%20vs%20Wind%20Speed.png)<br>

* ![Cloudiness](https://github.com/Pip85/python-api_weather_analysis/blob/main/WeatherPy/output_data/City%20Latitude%20vs%20Cloudiness.png)<br>

* ![Temp](https://github.com/Pip85/python-api_weather_analysis/blob/main/WeatherPy/output_data/City%20Latitude%20vs%20Max%20Temperature.png)<br>


* The data frame was split between cities in the northern hemisphere and those in the southern hemisphere.  
* Plots and linear regression were then prepared for latitude vs temperature, humidity, cloudiness and wind speed with latitude for each hemisphere.  
* A brief analysis was included with each plot, along with a print of the r-value.  
* See all regression plots:  https://github.com/Pip85/python-api_weather_analysis/tree/main/WeatherPy/output_data

* All plot images were saved in an output folder along with a .csv of the city dataframe.

* **Part two**, began by reading the .csv file created in part one into a new dataframe.  
* Using the new dataframe, a Google heatmap was created for all city locations.

![Heat](https://github.com/Pip85/python-api_weather_analysis/blob/main/VacationPy/heatmap.png)<br>

* A new dataframe was created by narrowing down the cities according to ideal weather conditions.  This resulted in a dataframe of only 8 cities.
* Using Google Places API, a search was done on each city in the narrowed dataframe to find the nearest hotel for each city.
* A new column was created in the dataframe and populated with the hotel name for each of the cities.
* Another Google heatmap was created to mirror the first one.  Markers were then generated based on the hotel coordinates and layered over the heatmap.

![heat_hotel](https://github.com/Pip85/python-api_weather_analysis/blob/main/VacationPy/hotel_heatmap.png)<br>

* A png file of both heatmaps was saved within the VacationPy folder.