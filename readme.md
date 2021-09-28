# OEA Module: Microsoft Graph API
## Updates:
### Landing page synopsis
Microsoft Graph is an all-inclusive tool which provides a gateway to data and intelligence in Microsoft 365, Microsoft Teams, and more. Data is freely available for students, teachers, and staff and includes productivity data (Outlook, Calendar, Excel, etc), people and workspace intellegence, device and app management, and usage reports (Teams, Onedrive, Skype, etc). 

![alt text](https://github.com/cstohlmann/oea-graph-api/blob/main/images/Graph%20visual.png)
(Provided by Microsoft from [Microsoft Graph overview](https://docs.microsoft.com/en-us/graph/overview))

This OEA module will leverage the Azure Synapse environment to aid education systems in bringing this data to their own Azure data lake for analysis. This includes a pipeline for extracting digital activity from Microsoft 365 and Microsoft Teams, providing a more detailed representation of student activities. This can be used by school administrators, and teachers to show:

 - Which people within the system are utilizing Microsoft 365 applications online or via desktop (i.e. Word, Outlook, PowerPoing, Excel, Teams), over a reporting period of 180 days.
 - Which people within the system are interacting on Microsoft Teams, (i.e. message counts, meetings attended, etc), to give a detailed breakdown of student engagement within Teams. 
 - (INCLUDE A SAMPLE PICTURE OF POWERBI DASHBOARD)

Sample out-of-the box assets for this OEA module include a pipeline which connects Graph API to the Synapse workspace. This pipeline stores the raw data to stage 1 storage in JSON format and processes this data to stage 2 in parquet format. Stage 2 data served to a Spark database making data easily queried and accessed. The complete OEA module will include: a sample dataset, a tutorial on setting up the pipeline and demonstration to build custom queries to pull data for your education tennant from Graph API, a notebook on processing the data from stage 1 to stage 2 within Synapse, and a Power BI template making it easy to interact with Graph data.
### For more info
| Resource | Description |
| --- | --- |
| [Overview of Microsoft Graph](https://docs.microsoft.com/en-us/graph/overview) | intro to Graph API and what it can do |
| [Microsoft Graph documentation/resources](https://docs.microsoft.com/en-us/graph/) | landing page of all documentation about Graph |
| [Microsoft Graph beta endpoint reference](https://docs.microsoft.com/en-us/graph/api/overview?view=graph-rest-beta) | API reference doc for Graph's beta version (used in this sample module) |
| [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) | utility that allows you to easily try out Graph API endpoints |
| [Use Postman with the Microsoft Graph API](https://docs.microsoft.com/en-us/graph/use-postman) | info on setting up Postman to work with Graph API |

## What Gene originally had:
### Microsoft Graph module 
> We plan to publish these assets soon - until then, here is a brief doc that describes how to create an integration pipeline and how to process the json data that is returned: Setting up a Graph API pipeline
>
> Once fully published, this module will provide:
>
> - data extraction pipelines demonstrating how to utilize Azure Data Factory to pull data from the Graph API
> - example data sets that demonstrate the json format that the data will come in
> - Synapse notebooks that demonstrate how the json data landed in stage 1 of the data lake can be processed and landed as parquet in stage 2 of the data lake
> - A simple Power BI report that demonstrates how to connect to your data lake and construct a semantic model and basic report on the data from the Graph API
### For more info
| Resource | Description |
| --- | --- |
| [Overview of Microsoft Graph](https://docs.microsoft.com/en-us/graph/overview) | intro to Graph API and what it can do |
| [Microsoft Graph REST API v1.0 reference](https://docs.microsoft.com/en-us/graph/api/overview?view=graph-rest-1.0) | API ref doc for v1.0 |
| [Microsoft Graph beta endpoint reference](https://docs.microsoft.com/en-us/graph/api/overview?view=graph-rest-beta) | API ref doc for beta version |
| [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) | utility that allows you to easily try out Graph API endpoints |
| [Use Postman with the Microsoft Graph API](https://docs.microsoft.com/en-us/graph/use-postman) | info on setting up Postman to work with Graph API |
### A word about Graph data connect...
> [Microsoft Graph data connect](https://docs.microsoft.com/en-us/graph/data-connect-concept-overview) provides access to [some M365 data](https://docs.microsoft.com/en-us/graph/data-connect-datasets) at scale, using Azure Data Factory.
>
> This module demonstrates the use of Graph API only - for an example of how to use data connect with Azure Data Factory, see: [msgraph-training-dataconnect](https://github.com/microsoftgraph/msgraph-training-dataconnect)
