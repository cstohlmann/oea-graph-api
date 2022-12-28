# Notebooks

This module incorporates two notebooks needed to support the main [module pipeline](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Microsoft_Graph/pipeline). Both notebooks depend on the [OEA python class](https://github.com/microsoft/OpenEduAnalytics/blob/main/framework/synapse/notebook/OEA_py.ipynb) which is a part of the [OEA framework](https://github.com/microsoft/OpenEduAnalytics/tree/main/framework).

## Module Python Class Notebook: [GraphAPI_py.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/notebook/GraphAPI_py.ipynb)

The module python class notebook that defines the data schemas and pseudonymization. Basic functions for data ingestion and processing from Stage 1 to Stage 2 data lakes are also included.

## Module Data Ingestion Notebook: [GraphAPI_module_ingestion.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/notebook/GraphAPI_module_ingestion.ipynb)

Module data ingestion notebook which depends on the module class. Importing the pipeline template will automatically upload this notebook. 
