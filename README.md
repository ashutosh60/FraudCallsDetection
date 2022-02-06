# Real Time Fraud Detection

## Problem Statement
Detection of fraudulent mobile-phone calls in telecommunications scenario.

## Project Description
This project has been built using Microsoft Azure Portal. This scenario covers the back-end components of a real-time analytics pipeline. Data flows through the scenario as follows: 

Mobile phone call metadata is sent from the source system to an Azure Event Hubs instance. 
A Stream Analytics job is started, which receives data via the event hub source. 
The Stream Analytics job runs a predefined query to transform the input stream and analyze it based on a fraudulent-transaction algorithm. This query uses a tumbling window to segment the stream into distinct temporal units. 
The Stream Analytics job writes the transformed stream representing detected fraudulent calls to an output sink in Power BI.
Then, using Azure App Service, a website  is built from the code of this repository on which the Power BI line-chart is embedded. Thus  signing in to Power BI is required to view the chart on azure website.

Please sign in to Power BI account first in order to view the report graph embedded in the website hosted on Microsoft Azure.

The Azure Services used are as follows:
1. Azure Portal: This is used to create Azure Stream Analytics job in order to analyse the fraud calls from the input data. Also used to create App Service to host website. 
2. Event Hubs: This is used to stoing the input data before analysis.
3. Azure Stream Analytics: Used to analyse the fraud calls from the input data. Input is taken in Event Hubs, SQL query used to detect the fradulent call data, output is sent to Power BI for plotting line chart showing the number of fraud calls at a given instant of time.
4. Azure App Service: Used to create and host a webapp in order to display Power BI chart analysis. 

Other service used is:  Power BI: This is used as output of Azure Stream analytics job.

## Project Description in detail: the building steps

### Sign in to Azure Portal

### Create an Event Hub
![Event Hubs](https://github.com/ashutosh60/FraudCallsDetection/blob/master/event-hubs.png)

After creating the Event hub, the event generator is started to upload sample data by using Telcogenerator.zip file.

![Telcogen](https://github.com/ashutosh60/FraudCallsDetection/blob/master/telco.png)

### Create an Azure Stream Analytics Job
There are three parameters to be set here.
1. Configure the input: Here we take input in the "Event Hubs".
2. Configure the output: Here the output is sent to Power BI.
3. Write the query: The query is written according to the problem statement that is to detect the fraud calls from the input data.

![Azure Stream Analytics](https://github.com/ashutosh60/FraudCallsDetection/blob/master/stream-analytics.png)

### Start the Stream Analytics Job and visualize the output

The Azure Stream Analytics job is started from the portal and the ouptut is visualized on Power BI in terms of a line chart.

![Power BI](https://github.com/ashutosh60/FraudCallsDetection/blob/master/power-bi.png)

### Embedding the Power BI chart in Web application
From the generated Power BI chart, the html tags to include this in a web app is taken and pasted into the web app building code so as to make the chart visible on the live website. But the chart is only visible if the viewer is signed in to Power BI account.

![Webapp chart](https://github.com/ashutosh60/FraudCallsDetection/blob/master/webapp.jpeg)

## Project URL
https://calls-ashutosh.azurewebsites.net

## Video URL
