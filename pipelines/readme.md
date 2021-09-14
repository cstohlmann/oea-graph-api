# Pipelines
> These pipelines demonstrate how to extract data from M365 via the Microsoft Graph
## Setting up a Pipeline to Pull User Data from Graph API
1. Create linked service to GraphAPI
     - First go to ADD &#3604 App registrations &#3604 New registration
          - Now create a new app registration specifically for accessing the Graph API from Synapse.
     - Then click "Add Permission" -> select Microsoft Graph -> select Application Permissions -> choose the "User.Read.All permission" -> click on the "Add Permissions" button.
