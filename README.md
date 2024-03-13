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
<img width="460" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/ef2a0654-eeef-4847-8c0f-eb63d377304d">

2. upload uber_data.csv file and open the permission to public. To open permission click the 3 dot at the most right side of the dataset and click edit access. if not enabled go to permission and switch to fine grained and edit access agai. now add entry and open to public
<img width="565" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/cd02ca26-17b2-4682-8fa5-4ff5950b3f71">
<img width="403" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/f7d0401d-8a5a-4a93-a290-a28e3e56c2a9">
<img width="565" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/73343946-323a-4512-8fb4-b1e377660b62">


3. Setup VM. Open Compute Engine and create instances
<img width="496" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/2f5d15ea-1ab5-42e3-8882-7a62b4e020d7">

``
Name: unique
Region Zone: nearest to Malaysia
Series: E2
Machine Type: standard, vcpu:4, 16GB Memory
Firewall: Allow HTTP & HTTPS traffic
`` click create

4. Once complete, click on the SSH beside the instance and the VM will pop up, we need to setup a few things first before moving on. write the command below
<img width="416" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/2239e214-c48c-460d-9178-30cb043b1a13">

``
Install Python and pip 
sudo apt-get update
sudo apt-get install python3-distutils
sudo apt-get install python3-apt
sudo apt-get install wget
wget https://bootstrap.pypa.io/get-pip.py
sudo python3 get-pip.py
Install Mage
sudo pip3 install mage-ai
Install Pandas
sudo pip3 install pandas
Install Google Cloud Library
sudo pip3 install google-cloud
sudo pip3 install google-cloud-bigquery
``



