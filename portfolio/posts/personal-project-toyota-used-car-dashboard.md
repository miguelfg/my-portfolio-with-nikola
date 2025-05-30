<!--
.. title: [Personal project] Toyota Used Car Dashboard
.. slug: personal-project-toyota-used-car-dashboard
.. date: 2025-05-30 14:26:06 UTC+02:00
.. tags: dashboard,streamlit,python,GCP
.. category: 
.. link: 
.. description: 
.. type: text
-->

### Unlocking the Toyota Used Car Market in Spain: with Python Streamlit Dashboard on Google Cloud

## Introduction
I built this dashboard to provide some hidden insights about the used car market in Spain. Toyota is probably the most sold brand of the country, and this dashboard allows users to explore Toyota’s used car listings through an interactive web application. The dashboard is built using Python and Streamlit, providing a user-friendly interface for data analysis.

## Exploring the Dashboard
The dashboard is divided into the following sections: geo, counts, price vs mileage, and price ranges. Each section provides python seaborn visualizations and filters to drill down into the data.

It currently contains close to 5000 used Toyota cars listed in Spain, with data sourced from the Toyota España website. Some of the car’s attributes are: model, year, mileage, transmission, fuel, eco badge, price, and dealer location.

It maps the dealers’ locations, allowing users to see where the cars are being sold and how many. The dashboard also provides various statistics and analytics, such as the number of cars registered per year, the most common car packages, and the distribution of prices by model and package.

## Technology Stack
The project is divided into two modules:
The ETL (Extract, Transform, Load) module, which scrapes the Toyota España website to gather used car data, clean and transform it, to store it in a local SQLite database.
The dashboard Streamlit app, which provides Python seaborn data visualizations and extensive filtering capabilities.

### The ETL Module

Here I used the Python requests library to scrape the Toyota España website, extracting data on used cars. After it is converted into a Pandas DataFrame, it is cleaned and transformed to ensure data quality. The cleaned data is then stored in a local SQLite database for easy access by the dashboard.

### The Dashboard Module
The dashboard is built using Streamlit, a powerful framework for creating interactive web applications in Python. It provides a user-friendly interface for exploring the used car data, with various filters and visualizations to help users gain insights into the market.
It has enabled a simple Authentication using the streamlit_authenticator extension.

User/pass: demo/cars

It is deployed on Google Cloud Run with a repository type. This eases the deployment process by automatically building the container image from the source code in the repository with any updates on the main branch.
The ETL is scheduled to run on Tuesdays and Fridays with Github Actions, thanks to the workflow file that runs the full ETL process and updates the local SQLite database with the latest data, and finally pushes the new db to Github.

## Conclusion: Empowering Your Used Toyota Search
This dashboard empowers users with data-driven insights understanding the market trends in Spain. It provides a comprehensive view of the used car listings, allowing future car buyers to make a better deal based on various factors such as price, mileage, car status, and dealer location.

### You can find me on:

- LinkedIn
- GitHub
- X / Twitter

