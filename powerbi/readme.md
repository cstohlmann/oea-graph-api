# PowerBI template

The Graph PowerBI template consists of 1 page:

1. <strong> Teams Activity</strong>: visualizes students that have used or interacted with Teams using the sample data.
 - Total Private and Public Teams Messages by userPrincipleName and Audio Duration - shows the breakdown of all users' private and public Teams messages, per audio duration (length of time they were speaking). This shows the interaction levels within Teams for any particular user.
 - Total Meetings Attended and Scheduled by userPrincipalName - shows a comparison of how many users attended the meetings that were scheduled in Teams (by default, in this example, everyone attended the meeting that was scheduled).

![alt text](https://github.com/cstohlmann/oea-graph-api/blob/main/docs/images/Graph%20API%20Example%20Dashboard.png)

## Star Schema
This PowerBI module is made up of the following tables: users, m365_app_user_detail, and teams_activity_user_details. The dimension table is users and the fact tables are m365_app_user_detail and teams_activity_user_details.

![alt text](https://github.com/cstohlmann/oea-graph-api/blob/main/docs/images/star%20schema%20for%20Graph%20example.png)

### Table Details 
| Table | Column | Description |
| --- | --- | --- |
| users | givenName | First name of a user |
| | id | Unique ID assigned to a user |
| | surname | Last name of a user |
| | userPrincipalName | Email address identifier of a user |
| m365_app_user_detail | name of column | description of column |
| | name of column | description of column |
| | name of column | description of column |
| | name of column | description of column |
| | name of column | description of column |
