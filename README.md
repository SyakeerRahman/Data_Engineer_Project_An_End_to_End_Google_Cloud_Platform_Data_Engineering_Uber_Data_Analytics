# Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics

## Introduction

The goal of this project is to perform data analytics on Uber data using various tools and technologies, including GCP Storage, Python, Compute Instance, Mage Data Pipeline Tool, BigQuery, and Looker Studio.

## Architecture

<img width="583" alt="Screenshot 2024-03-12 140733" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/fe17e12c-8924-4f0e-857c-68062af1b32a">

## Technology Used

Programming Language - Python
Google Cloud Platform

Google Storage
Compute Instance
BigQuery
Looker Studio
Modern Data Pipeine Tool - https://www.mage.ai/

Contibute to this open source project - https://github.com/mage-ai/mage-ai

## Dataset Used

TLC Trip Record Data Yellow and green taxi trip records include fields capturing pick-up and drop-off dates/times, pick-up and drop-off locations, trip distances, itemized fares, rate types, payment types, and driver-reported passenger counts.

Here is the dataset used in the video - https://github.com/darshilparmar/uber-etl-pipeline-data-engineering-project/blob/main/data/uber_data.csv

More info about dataset can be found here:

Website - https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
Data Dictionary - https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf

## Data Model

![image](https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/542ef557-ff46-4a79-bfc4-61af9716f1d6)


## Process

Python Jupyter
1. Clean the uber_data.csv by splittig the data from flat file and staging it to few dimension table and join back to the fact table. The transformation tools we used is Python in Jupyter Notebook

Google Cloud Platform
1. Create a new bucket cloud storage
<img width="614" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/1326dc83-d9d2-4c87-99d8-06b78a4d0cfe">


   
