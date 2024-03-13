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
Install Pandas
sudo pip3 install pandas
Install Google Cloud Library
sudo pip3 install google-cloud
sudo pip3 install google-cloud-bigquery
``

5. Click on the name (nic0), click on firewall and create firewall rule and fill the details as below
<img width="430" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/43cb9399-e88a-4f54-a1f9-20c748b456e1">
<img width="446" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/af328260-cf07-4322-94cc-82e91987737b">
<img width="254" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/299ac00d-49df-45f8-bae6-ead1a8ed94d4">
<img width="308" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/9ceb1f73-859e-4c27-abbb-0a86d32a6d51">


6. open mage ai using the (external ip: port) and click data loader and copy the url from GCP instances and paste inside the code. Then click data transformer and insert the code we have written in the Jupyter notebook because we will now do transformation to the data and save it in JSON format
<img width="424" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/cab277d1-cf30-4ce8-b104-064c8c3f7d54">
<img width="467" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/7b83f234-e0af-43cf-9dc2-1268382f9343">

7. Now we are going to load the data inside Bigquery, click the data exporter and click python>bigquery. Now we need credentials from Bigquery so go to GCP and search API & Service> credentials > create credentials > service account > fill details, give Bigquery Admin access and create > go back to the service account > add keys > create new key > JSON.
<img width="398" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/e33cefe0-8179-4bd3-<img width="368" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/732274cc-3061-44ca-bc23-9885aa7eafaf">
a5e2-f76d46add4e6">
<img width="272" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/fb43cf8f-5d88-457e-b802-3cd386bb5b8e">
<img width="377" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/7c914095-a351-468d-8d6e-1eac1c4ac191">

8. Open the JSON credentials file and now copy the details and paste it in to the Mage io_config.yaml. After finish copy paste the details and go to Google BigQuery and create a new dataset. Copy the dataset name and paste it inside the exporter code.
<img width="385" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/25e33ddf-8f94-4f00-b5a2-7249518a5722">

9. sudo pip3 install google-cloud, sudo pip3 instal google-cloud-bigquery. Now run the pipeline and see if it succeed or not
<img width="395" alt="image" src="https://github.com/SyakeerRahman/Data_Engineer_Project_An_End_to_End_Google_Cloud_Platform_Data_Engineering_Uber_Data_Analytics/assets/105381652/ada833d9-340e-4eb8-a7e0-ce2baa8b04c0">

