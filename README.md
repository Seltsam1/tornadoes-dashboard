# tornadoes-dashboard
Dashboard with maps and charts depicting tornado data

## Getting Started

This repository contains the final versions of a collaborative project (to see in progress steps, visit https://github.com/sandykolu/project2)

![Example of Dashboard](https://github.com/Seltsam1/tornadoes-dashboard/blob/main/presentation/dashboard-image.png)

Data is from the NOAA's National Weather Service, obtained via Kaggle (https://www.kaggle.com/jtennis/spctornado?select=Tornadoes_SPC_1950to2015.csv)

The dashboard website contains a backend (using a python flask app, json and csv files) and a frontend (html, javascript, and css files)

This utilizes Mongo DB to load and extract data from the source files, mapbox and leaflet to generate maps, d3 for api calls, and bootstrap for the landing page layout


## Features

- Folders and Files:
  - Presentation
    - Contains the powerpoint used to demonstrate the project
    - Contains the image shown above of the landing page of the dashboard
  - Cleaning
    - Contains jupyter notebook files contain draft versions of python cleaning code as part of ETL
  - Dashboard
    - Contains all files for the website as follows:
      - backend folder
        - data folder Contains the raw csv file initially used and the json file from the jupyter notebook steps
        - app.py contains 3 apis
          - /api/mongo reads the json file, loads to Mongo DB, then returns a geojson object
          - /api/top10 and /api/date_loss call the data_cleaning_py file
        - data_cleaning_py contains functions to read csv data, clean it, and produce 2 traces used later for plotly charts
      - frontend folder
        - index.html is the landing page for the dashboard
        - map.html is the page for the interactive map
        - cluster.html is the page for the cluster map
        - static folder
          - css contains 2 css files
            - landing-style.css formats the landing page and style.css formats the two map pages
          - js folder contains javascript files
            - config.js contains a public api key for the mapbox
            - index.js contains d3 calls of the flask app api's and generates the two plotly charts
            - logic.js javascript for the interactive map
            - cluster.js javascript for the cluster map
          - images map contains 3 images used in the landing page dashboard

## Licensing by:

The code in this project is licensed under MIT license.
