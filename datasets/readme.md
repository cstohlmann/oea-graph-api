# Sample Datasets

Sample datasets provided in this module were created using the pipeline integration, landing 3 datasets into stage 1 of the data lake. The following queries were used for this example module, and utilized the beta version of Graph API:
 - ``` beta/users?$select=givenName,surname,userPrincipalName,id ```
 - ``` beta/reports/getM365AppUserDetail(period='D180')/content?$format=application/json ```
 - ``` beta/reports/getTeamsUserActivityUserDetail(period='D180')?$format=application/json ```

In order to use these sample datasets, go through the following instructions:
1. Download all three of the JSON files. 
2. Within the "stage1np" folder in your Azure Synapse environment, you'll have to create a folder, titled "GraphAPI". 
3. Then, in  the "GraphAPI" folder, upload these three files. Now you're ready to use the sample notebook.

### For more info on these queries
| Resource | Description |
| --- | --- |
| [Microsoft Graph query documentation](https://docs.microsoft.com/en-us/graph/) | landing page of all documentation about Graph and queries that can be made |
| [Microsoft Users](https://docs.microsoft.com/en-us/graph/api/user-get?view=graph-rest-beta&tabs=http) | resource doc on the User details query |
| [Microsoft 365 Applications User Detail](https://docs.microsoft.com/en-us/graph/api/reportroot-getm365appuserdetail?view=graph-rest-beta&tabs=http) | resource doc on the M365 App User details query |
| [Teams Activity User Detail](https://docs.microsoft.com/en-us/graph/api/reportroot-getteamsuseractivityuserdetail?view=graph-rest-beta) | resource doc on the Teams Activity User details query |
