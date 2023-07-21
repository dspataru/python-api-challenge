# python-api-challenge
Module 6 Challenge - APIs

## Table of Contents
* [Background](https://github.com/dspataru/python-api-challenge/blob/main/README.md#background)
* [WeatherPy: Weather Variables vs Latitude Analysis](https://github.com/dspataru/python-api-challenge/blob/main/README.md#weatherpy-weather-variables-vs-latitude-analysis)
* [WeatherPy: Linear Regression](https://github.com/dspataru/python-api-challenge/blob/main/README.md#weatherpy-linear-regression)
* [VacationPy](https://github.com/dspataru/python-api-challenge/blob/main/README.md#vacationpy)

## Background

This repository contains two python scripts that help to (1) answer "what is the weather like as we approach the equator?", and (2) find a set of hotels in different locations around the world that match a certain search criteria. Python requests, APIs, and JSON traversals are used to answer these questions, and hvplots are used to visualize the data in a way that is meaningful. Inside the WeatherPy folder are the following:
1. [WeatherPy.ipynb](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/WeatherPy.ipynb) : This Jupyter Notebook file contains python code to show the relationship between weather variables and latitudes, and outputs a csv file called [cities.csv](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/cities.csv).
2. [VacationPy.ipynb](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/VacationPy.ipynb) : This Jupyter Notebook file uses the [cities.csv](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/cities.csv) file to find the nearest hotels given a certain search criteria with respect to ideal weather conditions for a vacation, and displays this information on a map using geoapify and hvplot.
3. [images](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/images) : This folder contains the output files for the VacationPy Jupyter Notebook. NOTE: this folder shows one single instance of the data when running the VacationPy script. Each time the WeatherPy script is run, new data gets pulled and the [cities.csv](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/cities.csv) file is updated.
4. [output_data](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data) : This folder contains the different graphs that are generated from running the [WeatherPy](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/WeatherPy.ipynb) Jupyter Notebook.

## WeatherPy: Weather Variables vs Latitude Analysis

A python script was developed to visualize the weather of over 500 cities of varying distances from the equator. The citipy python library and openweathermap API were both used to create a representative model of weather across cities. The first part of the code imports all the dependencies and randomly generates geographic coordinates and generates a list of cities using the [citipy library](https://pypi.org/project/citipy/). The next part of the WeatherPy project uses the [OpenWeatherMap API](https://openweathermap.org/api) to retreive weather data from the cities list. Using this information, a series of scatter plots are generated to showcase the following relationships:

* Latitude vs. Temperature

![Latitude vs. Temperature](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig1.png)

* Latitude vs. Humidity

![Latitude vs. Humidity](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig2.png)

* Latitude vs. Cloudiness

![Latitude vs. Cloudiness](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig3.png)

* Latitude vs. Wind Speed

![Latitude vs. Wind Speed](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig4.png)

## WeatherPy: Linear Regression

The data was separated into the Northern and Southern Hemisphere's. The linear regression for each of the relationships in the above section were computed and plotted on the graphs for the Northern and Southern Hemisphere's. A function was created to develop these plots and to also display the linear regression equation and r-value on the plots. The following plots were created and can be found in [WeatherPy](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/WeatherPy.ipynb):

* Northern Hemisphere: Temperature vs. Latitude
* Southern Hemisphere: Temperature vs. Latitude
* Northern Hemisphere: Humidity vs. Latitude
* Southern Hemisphere: Humidity vs. Latitude
* Northern Hemisphere: Cloudiness vs. Latitude
* Southern Hemisphere: Cloudiness vs. Latitude
* Northern Hemisphere: Wind Speed vs. Latitude
* Southern Hemisphere: Wind Speed vs. Latitude

In the southern hemisphere, the graph shows a positive linear relationship between the temperature and latitude. As the latitude increases, the temperature also increases. The r value suggests that there is a strong postive correlation between the temperature and latitude in the southern hemisphere. Because of this, you could be somewhat confident that you can predict the temperature in the southern hemisphere using the regression equation.

In contrast, the northern hemisphere has shows a negative linear relationship between the temperature and latitude. As the latitude increases, the temperature decreases. The correlation value r for the northern hemisphere suggests a low positive correlation. There is less confidence that the regression equation could predict the temperature given a particular latitude in the northern hemisphere.

The other results suggest that there is no strong correlation between the humidity and latitude, cloudiness and latitude, or wind speed and latitude in either the northern or southern hemispheres. The regression equation would not be a good equation to use to predict the humidity, cloudiness, or wind speed of a region given the latitude.


## VacationPy

This part of the project uses the [cities.csv](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/cities.csv) file generated from the [WeatherPy](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/WeatherPy.ipynb) project to plan for future vacations. Below is an example of what an instance of the dataframe looks like:

![cities df](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/images/city_data_df.png)

The [geoViews python library](https://pypi.org/project/geoviews/) and [Geoapify API](https://www.geoapify.com/) were used to create map visualizations. The map below displays a point for every city in the csv file. The size of each point is equal to the humidity in each city.

![cities map](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/images/city_map_plot.png)

Using a search criteria, the dataframe is narrowed down to cities with the ideal weather condition. For the purpose of this project, the following conditions were imposed on the dataframe:
* Temperature in between 23-30 degrees
* Wind speeds less than 4.5 m/s
* Cloudiness <= 20
* Humidity in between 50-70 %

Using this narrowed-down version of the dataframe, Geoapify API was used to find the first hotel located within 10,000 meters of the latitude and longitude coordinates of the cities. One instance of what the plot of the ideal weather cities looks like is shown below. The latitude, longitude, humidity, city name, hotel name, and country can be seen when hovering over the points on the map.

![hotels map](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/images/hotel_map_plot_portland.png)

The VacationPy notebook helps find hotels for vacation spots that fit a search criteria.









