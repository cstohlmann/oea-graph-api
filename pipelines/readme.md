# Pipelines
> These pipelines demonstrate how to extract data from M365 via the Microsoft Graph
## Setting up a Pipeline to Pull User Data from Graph API
1. Create linked service to GraphAPI
     - First go to ADD &#8594; App registrations &#8594; New registration
          - Now create a new app registration specifically for accessing the Graph API from Synapse.
     - Then click "Add Permission" &#8594; select "Microsoft Graph" &#8594; select "Application Permissions" &#8594; choose the "User.Read.All permission" &#8594; click on the "Add Permissions" button.
     - Go to "Certificates & Secrets" &#8594; add a new client secret &#8594; copy that value
     - (INSERT THE SCREENSHOT HERE)
     - Now in Synapse studio, go to "Linked services" &#8594; add a REST service for Graph API &#8594; select "AAD Service Principal" as the Authentication type.
     - (INSERT THE SCREENSHOT HERE)
     - Under "Service principle key", paste the value of the secret you copied in the previous steps.
     - Under "Service principle ID, enter the "Application (client) ID" of the app registration created in the previous step (go to the "Overview" section of the app registration). 
2. Create a pipeline
     - Create a pipeline &#8594; create a new REST dataset as the source, referring to the GraphAPIv1 linked service
     - (INSERT SCREENSHOT HERE)
3. Create a sink dataset going to the data lake
     - (INSERT SCREENSHOTS HERE)
