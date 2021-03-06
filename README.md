# DataLake_Wildfires_California
*Academic project on Data Lake and Data Warehouse*
## Introduction
This project is splitted in 2 phases, the first stage is to set up a data lake about one topic and collect data from more than 3 different sources, the second part consist in exploiting this data lake.
The data lake is hosetd by Amazon Web Service, therefore you will find in this repository, lambda function, Apache AirFLow DAG script that can be run only in their respective environment. There is other folders with Jupyter Notebooks or data, that were used to assist us to build the data lake. Finally, python script in the repository, are actual layers that trigger data from API and load it to a RDS table hosted by AWS.

## Goal
We have decided to study Wildfires in California, the overallo goal is to provide a real-time visualization as a supporting tool to decision makers and first responders, with all the collected data, plus the prediction/projection of ongoing fires and thermal anomalies. The data lake consist in 2 pipeplines, historical pipe with wildfires and related weather, drought and a real-time pipe with thermal anomalies related weather and. We aim to build a predictive model based on Machine Learning concept to predict wildfire's development, for instance magnitude of a fire according to the current weather condition. 

## GitHub content

**aws_lambda:** Folder contain lambda function to process and load data. Those files are supposed to run only in AWS. There is environment variables and other functions, only declared in the AWS environment. Therfore, it is impossible to run those files, it is only for information purposes. 

**dag:** Folder contain DAG script to execute lambda function in AWS. Those files are also only for information, they cannot be run in a python enviroment, only Apache AirFLow.

**data:** Folder conatin data, not supposed to be displayed (.gitignore)

**notebooks:** Folder contain Jupyter Notebooks. Help and visualization tools to build datalake, not formatted and not clean.

**historical_weather_data.py:** python script to run to access wildfires data table hosted in AWS, access locations and date to get weather data, from Visaul Crossing API, and then load those data in a RDS table also hosted by AWS but a different account. Endpoint, database name, user and APIkey also declared in as environment variables in a .env file (not display cause of .gitignore). 

**utils.py:** function used to build API query and extract information from JSON files, used in <historical_weather_data.py'>

**Drought_history.ipynb:** Jupyter Notebook for loading historical drought indices data from API to RDS table.

**Wildfire_History.ipynb:** Jupyter Notebook for loading historical wildfires data from ArcGIS API to RDS table.

**credentialsForrer.json:** JSON file with AWS access point

**.env:** not displayed for security reason, contact me for access

## Final Output

Here, you can find different visualization from Tableau

*Real-Time pipeline*
https://public.tableau.com/views/CaliforniaWildfires_16542072566010/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link

*Historical pipeline*
Wildfires in California: https://public.tableau.com/views/Californian_wildfires/Wildfires?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link 

Monthly Analysis: https://public.tableau.com/views/Californian_wildfires/Monthlyanalysis?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link 

Weather and Drought overview: https://public.tableau.com/views/Californian_wildfires/WDOverview?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link 
