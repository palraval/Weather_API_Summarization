# Weather_API_Summarization


## WeatherPy

A series of random longitude and latitude coordinates are generated and citipy is used to find the closest city to the randomly generated coordinates. Each unique city is placed into a list. The OpenWeatherMap API is used to extract the latitude, longitude, max temp, humidity, cloudiness, wind speed, country, and date for each city in this list. If any sort of error occurs when trying to get the API data for any of the cities, the city in question is skipped. The final values for each city are placed into another list. This list is converted to a dataframe and then turned into a csv file for future use. 

Using this dataframe, a series of scatterplots are created to observe the relationships between each city's data values. The scatterplots are: latitude vs. temperature, latitude vs. humidity, latitude vs. cloudiness, and latitude vs. wind speed. These four plots are saved under the "output_data" folder. 

Next, the dataframe is split into two smaller dataframes, each containing either northern or southern hemisphere data. Scatterplots are made for each hemisphere dataframe, visualizing the relationships between the following variables: maximum temperature, humidity, cloudiness, and wind speed, all plotted against latitude. For each scatterplot, the linear regression equation, and the r-value is calculated to determine the strength of the correlations.   

Based on the scatterplots, the linear regression equations, and the r-values, a few conclusions can be drawn about the relationships. Firstly, there seems to be a negative correlation between the Latitude and the maximum temperature for the northern hemisphere. Also, there seems to be a positive correlation between latitude and maximum temperature for the southern hemisphere. A third conclusion is that the data for both hemispheres do not indicate a strong relationship between latitude and humidity. There also does not appear to be a correlational relationship between cloudiness and latitude for either hemisphere. Lastly, there is not a strong correlational relationship between wind speed and latitude for the northern and the southern hemisphere data. 


## VacationPy

The "cities.csv" file that was created in the first part is used for this portion of the project. This file is converted to a dataframe and all the latitude and longitude values for each city in this data is used to plot on the map. Each point on the map is altered in size proportionally based on the humidity values. 

The next part involves filtering the dataframe based on certain preferred weather conditions. In this case, the preferred weather conditions are: maximum temperature below 23.88 °C, humidity below 60 %, cloudiness between 0 % and 90%, and wind speed below 5 m/s. Some columns from this filtered dataframe are dropped so only the following columns remain: 'City', 'Country', 'Lat', 'Lng', and 'Humidity'. A new, empty column called 'hotel_name' is also created in this dataframe. The Geoapify API is used to find a hotel within 10,000 miles of each city in the dataframe and appended into the empty 'hotel_name' column. If a KeyError or IndexError occurs when trying to find the closest hotel, the term "no hotel found" is appended into the respective row in the 'hotel_name' column. 

Finally, the filtered dataframe containing the cities is plotted on a map and the respective hotel name is added to the hover information for each point on the map. 
 


















