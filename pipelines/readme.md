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
     - (INSERT SCREENSHOT HERE)
     - (INSERT SECOND SCREENSHOT HERE)
     - You can reduce the data returned by selecting specific attributes in the relativeURL, like this:
     ```
     users?$select=givenName,surname,userPrincipalName,id
     ```
     - Use the Graph Explorer to try it out:
     - (INSERT SCREENSHOT HERE)
4. Troubleshotting 
     - If you run the pipeline and get a failure because of lack of access, like this:
     - (INSERT SAMPLE ERROR MESSAGE HERE)
     You will need to double check the app registration you created and the API permissions assigned to it.
5. Running the notebook, pipeline, and finishing touches
     - You can then go into Synapse &#8594; navigate to your data lake and see the JSON file &#8594; right click on it &#8594; select "Load to dataframe &#8594; run the Synapse notebook.
     - (INSERT SCREENSHOT HERE)
     - (INSERT SECOND SCREENSHOT HERE)
     - Now you need to process this user data and write to stage 2 in a more usable way, and also create a spark database that can be easily queried from Power BI.
          - Run this notebook to do that:
          - (INSERT SCREENSHOT HERE)
          - Here's the script (you have to change the URL values to use your storage account name):
          ```python
          %%pyspark
          from pyspark.sql.types import StructType, StructField, StringType, IntegerType, DoubleType, ArrayType
          from pyspark.sql.functions import explode
          
          user_schema = StructType(fields=[
              StructField('value', ArrayType(
                  StructType([
                      StructField('surname', StringType(), False),
                      StructField('givenName', StringType(), False),
                      StructField('userPrincipalName', StringType(), False),
                      StructField('id', StringType(), False)
                  ])
              ])
          ])
          
          df = spark.read.load('abfss://stage1@storacisd3demo4.dfs.core.windows.net/AAD/users', format='json', schema=user_schema)
          df = df.select(explode('value').alias('exploded_values')).select("exploded_values.*")
          display(df.limit(10))
          df.write.format('parquet').mode('overwrite').save('abfss://stage2@stoeacisd3demo4.dfs.core.windows.net/AAD/users')
          
          # Create spark db to allow for access to the data in the data lake via SQL on-demand.
          spark.sql('CREATE DATABASE IF NOT EXISTS AAD')
          spark.sql("create table if not exists AAD.users using PARQUET location 'abfss://stage2@stoeacisd3demo4.dfs.core.windows.net/AAD/users'")
          ```
          - Now you're able to query the user data from the spark database:
          - (INSERT SCREENSHOT HERE)
          
