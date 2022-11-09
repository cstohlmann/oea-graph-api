# Test Data

This module includes artificially generated data which matches the format of the three "Get" beta queries (i.e. utilizing the beta version of Graph REST API Reports):
 - Microsoft Users: ``` beta/users ```
 - Microsoft 365 Applications User Detail: ``` beta/reports/getM365AppUserDetail(period='D7')/content?$format=application/json ```
 - Teams Activity User Detail: ``` beta/reports/getTeamsUserActivityUserDetail(period='D7')?$format=application/json ```

one "Get" v1.0 query (i.e. using the v1.0 version of the Graph REST API Education):
 - Education Assignment: ``` v1.0/education/classes/{id}/assignments/{id}?$format=application/json ```
    * The method supports ```$select``` and other [OData query parameters](https://learn.microsoft.com/en-us/graph/query-parameters) to help customize the response.

and one "Get" v1.0 query used in this module (i.e. using the v1.0 version of the Graph REST API Teamwork and Communications):
 - Meeting Attendance Report: ``` v1.0/users/{userId}/onlineMeetings/{meetingId}/attendanceReports/{reportId}?$expand=attendanceRecords$format=application/json ```
 - or: ``` v1.0/users/{userId}/onlineMeetings/{meetingId}/attendanceReports/{reportId}?$expand=attendanceRecords?$format=application/json ```
 - or: ``` v1.0/me/onlineMeetings/{meetingId}/attendanceReports/{reportId}?$expand=attendanceRecords?$format=application/json ```
    * The method also supports the [OData query parameters](https://learn.microsoft.com/en-us/graph/query-parameters) to help customize the response.

<strong><em>[^MAY HAVE TO EDIT THESE LAST FEW v1.0 QUERIES; NOT TESTED YET]</strong></em>.

For more detailed explanations, read the tutorial documentation [here](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/docs/Graph%20Reports%20API%20Module%20Tutorial.pdf). For more information on these queries and others that can be used, [click here](https://docs.microsoft.com/en-us/graph/) to learn more.

### Possible Other Valuable Queries

| Query | Purpose/Value | 
| --- | --- | 
| [List Education Assignment Submissions](https://learn.microsoft.com/en-us/graph/api/educationassignment-list-submissions?view=graph-rest-1.0&tabs=http) | Would give a list of student submissions to the assignment to track context of student engagement with course materials. |
|  |  |
|  |  |
|  |  |

## Data Dictionary 

### [Users Table](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/test_data/GraphAPI/Users/part-00000-cae42818-3572-4824-b396-58587ad01616-c000.json)

See full details on the [Microsoft Graph Users Beta Query](https://docs.microsoft.com/en-us/graph/api/user-get?view=graph-rest-beta&tabs=http)

| Domain | Table Name | Column Name | Description |
| --- | --- | --- | --- |
| SIS | users | surname | user last name |
| | | givenName | user first name |
| | | userPrincipalName | user email identifier |
| | | id | user ID |

### [M365 Applications User Detail](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Microsoft_Graph/test_data/GraphAPI/M365_App_User_Detail)

See full details on the [Microsoft Graph M365 Applications User Detail Beta Query](https://docs.microsoft.com/en-us/graph/api/reportroot-getm365appuserdetail?view=graph-rest-beta&tabs=http)

| Domain | Table Name | Column Name | Description |
| --- | --- | --- | --- |
| O365 Activity| m365_app_user_detail | reportRefreshDate | Date the report was generated |
| | | userPrincipalName | user email identifier |
| | | lastActivationDate | Date of last O365 App Activation |
| | | lastActivityDate | Date of last activity seen across all apps|
| | | reportPeriod | Number of days the data is reporting over |
| | | mobile | Boolean expression of if any O365 app has been used on a mobile device |
| | | web | Boolean expression of if any O365 app has been used on the web |
| | | mac | Boolean expression of if any O365 app has been used on a Mac device|
| | | windows | Boolean expression of if any O365 app has been used on a Windows device|
| | | excel | Boolean expression of if this app has been used |
| | | excelMac | Boolean expression of if this app has been used on a Mac device |
| | | excelMobile | Boolean expression of if this app has been used on a Mobile device|
| | | excelWeb | Boolean expression of if this app has been used on the web |
| | | excelWindows | Boolean expression of if this app has been used on a Windows device|
| | | oneNote(Mac)(Mobile)(Web)(Windows) | Boolean expression of if this app has been used |
| | | outlook(Mac)(Mobile)(Web)(Windows) | Boolean expression of if this app has been used |
| | | powerPoint(Mac)(Mobile)(Web)(Windows) | Boolean expression of if this app has been used |
| | | teams(Mac)(Mobile)(Web)(Windows) | Boolean expression of if this app has been used |
| | | word(Mac)(Mobile)(Web)(Windows) | Boolean expression of if this app has been used |

### [Teams Activity User Detail](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Microsoft_Graph/test_data/GraphAPI/Teams_Activity_User_Detail)

See full details on the [Microsoft Graph Teams Activity User Detail Beta Query](https://docs.microsoft.com/en-us/graph/api/reportroot-getteamsuseractivityuserdetail?view=graph-rest-beta)

| Domain | Table Name | Column Name | Description |
| --- | --- | --- | --- |
| Teams Activity | teams_activity_user_detail | reportRefreshDate | Refer to the query documentation [here](https://docs.microsoft.com/en-us/graph/api/reportroot-getteamsuseractivityuserdetail?view=graph-rest-beta) for details on the columns of this table |
| | | userPrincipalName | |
| | | lastActivityDate | |
| | | reportPeriod | |
| | | adHocMeetingsAttendedCount | |
| | | adHocMeetingsOrganizedCount | |
| | | assignedProducts | |
| | | audioDuration | |
| | | callCount | |
| | | deletedDate | |
| | | hasOtherAction | |
| | | isDeleted | |
| | | isLicensed | |
| | | meetingCount | |
| | | meetingsAttendedCount | |
| | | meetingsOrganizedCount | |
| | | scheduledOneTimeMeetingsAttendedCount | |
| | | scheduledOneTimeMeetingsOrganizedCount | |
| | | scheduledRecurringMeetingsAttendedCount | |
| | | scheduledRecurringMeetingsOrganizedCount | |
| | | screenShareDuration | |
| | | teamChatMessageCount | |
| | | videoDuration | |

### Education Assignment

See full details on the [Microsoft Graph Education Assignment v1.0 Query](https://learn.microsoft.com/en-us/graph/api/educationassignment-get?view=graph-rest-1.0&tabs=http), or details on the [Microsoft Graph Education Assignment ResourceType](https://learn.microsoft.com/en-us/graph/api/resources/educationassignment?view=graph-rest-1.0)

| Domain | Table Name | Column Name | Description |
| --- | --- | --- | --- |
| Assignment Details | education_assignments | classId | Refer to the query documentation [here](https://learn.microsoft.com/en-us/graph/api/educationassignment-get?view=graph-rest-1.0&tabs=http) for details on the columns of this table |
| | | displayName | |
| | | id | |
| | | <em>and many others</em> | |

### Meeting Attendance Report

See full details on the [Microsoft Graph Meeting Attendance Report v1.0 Query](https://learn.microsoft.com/en-us/graph/api/meetingattendancereport-get?view=graph-rest-1.0&tabs=http), or details on the [Microsoft Graph Education Assignment ResourceType](https://learn.microsoft.com/en-us/graph/api/resources/meetingattendancereport?view=graph-rest-1.0)

| Domain | Table Name | Column Name | Description |
| --- | --- | --- | --- |
| Meeting Attendance Report | meeting_attendance_report | id | Refer to the query documentation [here](https://learn.microsoft.com/en-us/graph/api/meetingattendancereport-get?view=graph-rest-1.0&tabs=http) for details on the columns of this table |
| | | totalParticipantCount | |
| | | meetingStartDateTime | |
| | | meetingEndDateTime | |
| | | attendanceRecords_userEmail | |
| | | attendanceRecords_totalAttendanceInSec | |
| | | attendanceRecords_role | |
| | | attendanceRecords_identity_id | |
| | | attendanceRecords_identity_displayName | |
| | | attendanceRecords_identity_tenantId | |
| | | <em>and many others</em> | |

