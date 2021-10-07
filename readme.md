# OEA Module: Microsoft Graph API
Microsoft Graph is an all-inclusive tool which provides a gateway to data and intelligence in Microsoft 365, Microsoft Teams, and more. Data is freely available for students, teachers, and staff and includes: productivity data (e.g. Outlook, Calendar, Excel), people and workspace intellegence, device and app management, and usage reports (e.g. Teams, Onedrive, Skype). 

![alt text](https://github.com/cstohlmann/oea-graph-api/blob/main/docs/images/Graph%20visual.png)
<p align="center">
    <em>(Provided by Microsoft from https://docs.microsoft.com/en-us/graph/overview)</em>
</p>

## Problem Statement [NEEDS TO BE REWORKED]
As an online educator, one of the most difficult things to see is whether students are actually participating, asking questions, or using their resources. 

Using Microsoft Teams, you may build intuition during online sessions/lectures, but using data trends as to which students are contributing the most/least is crucial to making sure students are truly active and learning. If you were to assign longterm projects, you may want to see if students are using the Microsoft 365 resources to complete the project (e.g. Word, PowerPoint, Excel). 

Pulling data using this Graph API module provides solutions to these scenarios, as well as many more instances to extract a wide variety of activities that students engage in, while online.
## Module Impact 
This OEA module will leverage the Azure Synapse environment to aid education systems in bringing this data to their own Azure data lake for analysis. This includes a pipeline for extracting digital activity from Microsoft Teams and 365, providing a more detailed and accurate representation of students' online activities. The example within this module would be used by school administrators and teachers to show:

 - Which people within the system are interacting on Microsoft Teams (i.e. message counts, meetings attended, etc), to give a detailed breakdown of student engagement within Teams, over a reporting period of 180 days. 
 - Which people within the system are utilizing Microsoft 365 applications online or via desktop (i.e. Word, Outlook, PowerPoint, Excel, Teams), over a reporting period of 180 days.

This example module currently represents data from Microsoft Teams and 365 for Digital Activities, but can be combined with other Graph queries of data within the use of Microsoft platforms; to identify how patterns of online activity affect learning outcomes. With such combined data, schools and teachers can start to analyze whether new programs or interventions help to improve learning outcomes.  

## Module Components
Sample out-of-the box assets for this OEA module include: 
1. [Tutorial](https://github.com/cstohlmann/oea-graph-api/blob/main/docs/documents/Graph%20API%20Pipeline%20Tutorial.pdf): A tutorial of how to use this module within your own Synapse workspace, as well as demonstration to build custom queries to pull data for your education tennant from Graph API.
2. [Sample Datasets](https://github.com/cstohlmann/oea-graph-api/tree/main/datasets): Ingest sample data to understand the utility and funcationality of the notebook(s).
3. [Pipeline(s)](https://github.com/cstohlmann/oea-graph-api/tree/main/pipelines): A pipeline which connects Graph API to the Synapse workspace.
4. [Notebooks](https://github.com/cstohlmann/oea-graph-api/tree/main/notebooks): An example notebook on processing the data from stage 1 to stage 2 within Synapse. 
5. [PowerBI Templates](https://github.com/cstohlmann/oea-graph-api/tree/main/powerbi): A Power BI sample template making it easy to interact with Graph data.

![alt text](https://github.com/cstohlmann/oea-graph-api/blob/main/docs/images/Graph%20API%20Example%20Dashboard.png)
<p align="center">
    <em> <strong>(NEEDS TO BE EDITED)</em></strong>
</p>

The Graph API module welcome contributions.

This module was developed by Christian Stohlmann & Chad Vidden. The architecture and reference implementation for all modules is built on Azure Synapse Analytics - with Azure Data Lake Storage as the storage backbone, and Azure Active Directory providing the role-based access control.

### For more info
| Resource | Description |
| --- | --- |
| [Overview of Microsoft Graph](https://docs.microsoft.com/en-us/graph/overview) | Intro to Graph API and what it can do. |
| [Microsoft Graph query documentation](https://docs.microsoft.com/en-us/graph/) | Landing page of all documentation about Graph and queries that can be made. |
| [Microsoft Graph beta endpoint reference](https://docs.microsoft.com/en-us/graph/api/overview?view=graph-rest-beta) | API reference doc for Graph's beta version (used in this sample module). |
| [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) | Utility that allows you to easily try out Graph API endpoints. |
| [Use Postman with the Microsoft Graph API](https://docs.microsoft.com/en-us/graph/use-postman) | Info on setting up Postman to work with Graph API. |
| [Microsoft Graph data connect](https://docs.microsoft.com/en-us/graph/data-connect-concept-overview) | The Graph data connect provides access to [some M365 data](https://docs.microsoft.com/en-us/graph/data-connect-datasets) at scale, using Azure Data Factory. This module demonstrates the use of Graph API only; for an example of how to use data connect with Azure Data Factory, see [msgraph-training-dataconnect](https://github.com/microsoftgraph/msgraph-training-dataconnect) |

# Legal Notices
Microsoft and any contributors grant you a license to the Microsoft documentation and other content in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode), see the [LICENSE] file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the [LICENSE-CODE] file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries. The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks. Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents, or trademarks, whether by implication, estoppel or otherwise.
