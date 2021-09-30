# Notebooks

All data generated from the use of Graph API is taken in JSON format, and landed in stage 1 of the data lake in your Azure Synapse environment. Upload this notebook to the Develop tab of your Azure Synapse Analytics, attach to your configured Spark pool and run. This notebook takes the JSON data from stage 1 and transforms/lands the processed data as a Parquet in stage 2 of the data lake. The data is pulled from the Graph API pipeline integration, or from the uploaded datasets.

## Databases and Tables
| Databases Created | Tables Created | Table Purpose | Data Source Used | Data Used |
| --- | --- | --- | --- | --- |
| graphapi | users | Contains all students' and teachers' Microsoft user information | stage 1np GraphAPI data: users | surname |
| | | | | givenName |
| | | | | userPrincipalName |
| | | | | givenName |
| graphapi | m365_app_user_detail | Contains past 180 days of students' and teachers' Microsoft 365 applications activity per user | stage 1np GraphAPI data: m365_app_user_detail | reportRefreshDate |
| | | | | userPrincipalName |
| | | | | lastActivityDate |
| | | | | details: \[excelWeb, outlookWeb, powerPoint, teamsWeb, teams, outlook, reportPeriod, excel, powerPointWeb, wordWeb, word\]|
| graphapi | teams_activity_user_details | Contains past 180 days of students' and teachers' Microsoft Teams activity per user | stage 1np GraphAPI data: teams_activity_user_details | reportRefreshDate |
| | | | | reportPeriod |
| | | | | userPrincipalName |
| | | | | privateChatMessageCount |
| | | | | teamsChatMessageCount |
| | | | | meetingsAttendedCount |
| | | | | meetingsCount |
| | | | | audioDuration |
