# Notebooks

This module has three notebooks:
 1. One notebook is used to demonstrate an alternate method of data processing (i.e. landing, ingesting, and refining Insights data) with examples of explorative possbilities.
 2. The schema_correction notebook is necessary to support the main [module pipeline](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Microsoft_Graph/pipeline) for correcting each table's schema from the data source. 
 3. The refine notebook is necessary to support the main [module pipeline](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Microsoft_Graph/pipeline) for pseudonymizing each table per table schema from the data source. 

All notebooks depend on the [OEA python class](https://github.com/microsoft/OpenEduAnalytics/blob/main/framework/synapse/notebook/OEA_py.ipynb) which is a part of the [OEA framework](https://github.com/microsoft/OpenEduAnalytics/tree/main/framework), and are automatically imported upon running the ```module_graph_v0.1rc1.zip``` setup script.

## Module Example Notebook: [Graph_example.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/notebook/Graph_example.ipynb)

This Graph module example notebook:
 - lands either K-12 or higher education test data into ```stage1/Transactional/graph_api/beta``` of your data lake (as well as ```stage1/Transactional/graph_api/v1.0``` if higher education test data is chosen; refer to steps in the notebook for how to choose which dataset to land), 
 - cleans meeting_attendance_report table and ingests the unstructured tables into ```stage2/Ingested/graph_api/(beta and/or v1.0)```, 
 - corrects the each table's schema to structure the tables properly - overwriting the tables in ```stage2/Ingested/graph_api/(beta and/or v1.0)```, 
 - refines the data into ```stage2/Refined/graph_api/(beta and/or v1.0)/(general and sensitive)``` by pseudonymizing (i.e. hashing or masking) sensitive information. 

Basic functions for data exploration and visualization from Stage 1 to Stage 2 data lakes are also included. Steps are clearly outlined and commented.

## Module Schema Correction Notebook: [Graph_schema_correction.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/notebook/Graph_schema_correction.ipynb)

Module table-schema correction notebook, necessary for adding column names and correcting column data types. Steps are clearly outlined in the notebook.

## Module Refinement Notebook: [Graph_refine.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Microsoft_Graph/notebook/Graph_refine.ipynb)

Module-specific pseudonymization notebook, necessary for speeding up the process of refining the module tables. Steps are clearly outlined in the notebook.
