# python-api-challenge
Module 6 Challenge - APIs

## Table of Contents
* [Background](https://github.com/dspataru/python-api-challenge/blob/main/README.md#background)
* [WeatherPy: Weather Variables vs Latitude Analysis](https://github.com/dspataru/python-api-challenge/blob/main/README.md#study-observations)

## Background

This repository contains two python scripts that help to (1) answer "what is the weather like as we approach the equator?", and (2) find a set of hotels in different locations around the world that match a certain search criteria. Python requests, APIs, and JSON traversals are used to answer these questions, and hvplots are used to visualize the data in a way that is meaningful. Inside the WeatherPy folder are the following:
1. [WeatherPy.ipynb]() : This Jupyter Notebook file contains python code to show the relationship between weather variables and latitudes, and outputs a csv file called cities.csv.
2. [VacationPy.ipynb]() : This Jupyter Notebook file uses the [cities.csv](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/cities.csv) file to find the nearest hotels given a certain search criteria with respect to ideal weather conditions for a vacation, and displays this information on a map using geoapify and hvplot.
3. [images]() : This folder contains the output files for the VacationPy Jupyter Notebook.
4. [output_data](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data) : This folder contains the different graphs that are generated from running the WeatherPy Jupyter Notebook.

## WeatherPy: Weather Variables vs Latitude Analysis

A python script was developed to visualize the weather of over 500 cities of varying distances from the equator. The citipy python library and openweathermap API were both used to create a representative model of weather across cities. The first part of the code imports all the dependencies and randomly generates geographic coordinates and generates a list of cities using the [citipy library](https://pypi.org/project/citipy/). The next part of the WeatherPy project uses the [OpenWeatherMap API](https://openweathermap.org/api) to retreive weather data from the cities list. Using this information, a series of scatter plots are generated to showcase the following relationships:

* Latitude vs. Temperature

![Latitude vs. Temperature](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig1.png)

* Latitude vs. Humidity

![Latitude vs. Humidity](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig2.png)

* Latitude vs. Cloudiness

![Latitude vs. Cloudiness](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig3.png)

* Latitude vs. Wind Speed

![Latitude vs. Wind Speed](https://github.com/dspataru/python-api-challenge/blob/main/WeatherPy/output_data/Fig3.png)

## WeatherPy: Linear Regression

The data was separated into the Northern and Southern Hemisphere's. The linear regression for each of the relationships in the above section were computed and plotted on the graphs for the Northern and Southern Hemisphere's. A function was created to develop these plots and to also display the linear regression equation and r-value on the plots. The following plots were created:

* Northern Hemisphere: Temperature vs. Latitude

* Southern Hemisphere: Temperature vs. Latitude

* Northern Hemisphere: Humidity vs. Latitude

* Southern Hemisphere: Humidity vs. Latitude

* Northern Hemisphere: Cloudiness vs. Latitude

* Southern Hemisphere: Cloudiness vs. Latitude

* Northern Hemisphere: Wind Speed vs. Latitude

* Southern Hemisphere: Wind Speed vs. Latitude


