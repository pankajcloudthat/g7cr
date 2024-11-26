## Spark Job Definition

### Create a Spark job definition for PySpark (Python)

To create a Spark job definition for PySpark:

1. Download the sample Parquet file [yellow_tripdata_2024-07.parquet](https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2024-07.parquet) and upload it to the files section of the lakehouse.

1. Create a new Spark job definition.

1. Select **PySpark (Python)** from the **Language** dropdown.

1. Download the [createTablefromParquet.py](https://github.com/pankajcloudthat/g7cr/blob/main/sjd/sjddefinition.py) sample and upload it as the main definition file. The main definition file (*job.Main*) is the file that contains the application logic and is mandatory to run a Spark job. For each Spark job definition, you can only upload one main definition file.

   You can upload the main definition file from your local desktop, or you can upload from an existing Azure Data Lake Storage (ADLS) Gen2 by providing the full ABFSS path of the file. For example, `abfss://your-storage-account-name.dfs.core.windows.net/your-file-path`.

1. Upload reference files as *.py* files. The reference files are the python modules that are imported by the main definition file. Just like the main definition file, you can upload from your desktop or an existing ADLS Gen2. Multiple reference files are supported.

   > [!TIP]
   > If you use an ADLS Gen2 path, to make sure the file is accessible, you must give the user account that runs the job the proper permission to the storage account. We suggest two different ways to do this:
   >
   >- Assign the user account a Contributor role for the storage account.
   >- Grant Read and Execution permission to the user account for the file via the ADLS Gen2 Access Control List (ACL).
   >  
   > For a manual run, the account of the current login user is used to run the job.
   
1. Add the lakehouse reference to the job. You must have at least one lakehouse reference added to the job. This lakehouse is the default lakehouse context for the job.

   Multiple lakehouse references are supported. Find the non-default lakehouse name and full OneLake URL in the **Spark Settings** page.
