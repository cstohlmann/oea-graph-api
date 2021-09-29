# OEA Module: Microsoft Graph API
Microsoft Graph is an all-inclusive tool which provides a gateway to data and intelligence in Microsoft 365, Microsoft Teams, and more. Data is freely available for students, teachers, and staff and includes: productivity data (e.g. Outlook, Calendar, Excel), people and workspace intellegence, device and app management, and usage reports (e.g. Teams, Onedrive, Skype). 

![alt text](https://github.com/cstohlmann/oea-graph-api/blob/main/images/Graph%20visual.png)
<p align="center">
    <em>(Provided by Microsoft from https://docs.microsoft.com/en-us/graph/overview)</em>
</p>


This OEA module will leverage the Azure Synapse environment to aid education systems in bringing this data to their own Azure data lake for analysis. This includes a pipeline for extracting digital activity from Microsoft 365 and Microsoft Teams, providing a more detailed representation of student activities. The example within this module would be used by school administrators and teachers to show:

 - Which people within the system are utilizing Microsoft 365 applications online or via desktop (i.e. Word, Outlook, PowerPoing, Excel, Teams), over a reporting period of 180 days.
 - Which people within the system are interacting on Microsoft Teams (i.e. message counts, meetings attended, etc), to give a detailed breakdown of student engagement within Teams, over a reporting period of 180 days. 
 <p align="center">
    <em><strong>(INCLUDE A SAMPLE PICTURE OF POWERBI DASHBOARD)</em></strong>
</p>
 

Sample out-of-the box assets for this OEA module include: 
- A pipeline which connects Graph API to the Synapse workspace,
- a [tutorial on setting up your own pipeline](https://github.com/cstohlmann/oea-graph-api/tree/main/pipelines) and demonstration to build custom queries to pull data for your education tennant from Graph API,
- a sample dataset, 
- a sample notebook on processing the data from stage 1 to stage 2 within Synapse, and 
- a Power BI sample template making it easy to interact with Graph data.

### For more info
| Resource | Description |
| --- | --- |
| [Overview of Microsoft Graph](https://docs.microsoft.com/en-us/graph/overview) | intro to Graph API and what it can do |
| [Microsoft Graph query documentation](https://docs.microsoft.com/en-us/graph/) | landing page of all documentation about Graph and queries that can be made |
| [Microsoft Graph beta endpoint reference](https://docs.microsoft.com/en-us/graph/api/overview?view=graph-rest-beta) | API reference doc for Graph's beta version (used in this sample module) |
| [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) | utility that allows you to easily try out Graph API endpoints |
| [Use Postman with the Microsoft Graph API](https://docs.microsoft.com/en-us/graph/use-postman) | info on setting up Postman to work with Graph API |

### A word about Graph data connect...
[Microsoft Graph data connect](https://docs.microsoft.com/en-us/graph/data-connect-concept-overview) provides access to [some M365 data](https://docs.microsoft.com/en-us/graph/data-connect-datasets) at scale, using Azure Data Factory.

This module demonstrates the use of Graph API only - for an example of how to use data connect with Azure Data Factory, see: [msgraph-training-dataconnect](https://github.com/microsoftgraph/msgraph-training-dataconnect)
