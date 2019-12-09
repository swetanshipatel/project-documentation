Google BigQuery Connector Documentation Reference
=================================================

Google BigQuery Connector

-   [Configurations](#_configurations)
    -   [Config](#config)
-   [Operations](#_operations)
    -   [Cancel Job](#cancelJob)
    -   [Create Dataset](#createDataset)
    -   [Create Job](#createJob)
    -   [Create Table](#createTable)
    -   [Delete Dataset](#deleteDataset)
    -   [Delete Table](#deleteTable)
    -   [Get Dataset](#getDataset)
    -   [Get Job](#getJob)
    -   [Get Query Result](#getQueryResult)
    -   [Get Table](#getTable)
    -   [Insert All](#insertAll)
    -   [List Dataset](#listDataset)
    -   [List Job](#listJob)
    -   [List Table](#listTable)
    -   [List Table Data](#listTableData)
    -   [Query](#query)
    -   [Update Dataset](#updateDataset)
    -   [Update Table](#updateTable)
-   [Types](#_types)
    -   [Reconnection](#Reconnection)
    -   [Reconnect](#reconnect)
    -   [Reconnect Forever](#reconnect-forever)
    -   [Pooling Profile](#PoolingProfile)
    -   [Expiration Policy](#ExpirationPolicy)
    -   [Dataset](#Dataset)
    -   [Acl](#Acl)
    -   [Entity](#Entity)
    -   [Dataset Id](#DatasetId)
    -   [Job](#Job)
    -   [Job Configuration](#JobConfiguration)
    -   [Job Id](#JobId)
    -   [Job Statistics](#JobStatistics)
    -   [Job Status](#JobStatus)
    -   [Big Query Error](#BigQueryError)
    -   [Job Info Options](#JobInfoOptions)
    -   [Table Information](#TableInformation)
    -   [Encryption Configuration](#EncryptionConfiguration)
    -   [Table Id](#TableId)
    -   [Table Definition](#TableDefinition)
    -   [Schema](#Schema)
    -   [Field](#Field)
    -   [Legacy SQL Type Name](#LegacySQLTypeName)
    -   [Table Info Configuration](#TableInfoConfiguration)
    -   [Table Configuration](#TableConfiguration)
    -   [Table Schema](#TableSchema)
    -   [Table Field Configuration](#TableFieldConfiguration)
    -   [Table Info Options](#TableInfoOptions)
    -   [Dataset Info Option](#DatasetInfoOption)
    -   [Table Result](#TableResult)
    -   [Field Value](#FieldValue)
    -   [Job Query Results Option](#JobQueryResultsOption)
    -   [Insert All Response](#InsertAllResponse)
    -   [Page Attribute](#PageAttribute)
    -   [List Dataset Option](#ListDatasetOption)
    -   [List Table Options](#ListTableOptions)
    -   [Query Job](#QueryJob)
    -   [Named Parameter Configuration](#NamedParameterConfiguration)
    -   [Query Parameter Value
        Configuration](#QueryParameterValueConfiguration)
    -   [External Table Definition
        Configuration](#ExternalTableDefinitionConfiguration)
    -   [User Defined Function
        Configuration](#UserDefinedFunctionConfiguration)
    -   [User Acl](#UserAcl)
    -   [Domain Acl](#DomainAcl)
    -   [View Acl](#ViewAcl)
    -   [Copy Job](#CopyJob)
    -   [Extract Job](#ExtractJob)
    -   [Load Job](#LoadJob)

This is the main class of an extension, is the entry point from which
configurations, connection providers, operations and sources are going
to be declared.

Configurations {#_configurations}
--------------

* * * * *

### Config

Default configuration

#### Parameters {#_parameters}

  Name                Type                                     Description                                                                                                                                                                                                                                                                                                                           Default Value   Required
  ------------------- ---------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Name                String                                   The name for this configuration. Connectors reference the configuration with this name.                                                                                                                                                                                                                                                               **x** 
  Connection          [Connection](#config_connection)         The connection types that can be provided to this configuration.                                                                                                                                                                                                                                                                                      **x** 
  Expiration Policy   [Expiration Policy](#ExpirationPolicy)   Configures the minimum amount of time that a dynamic configuration instance can remain idle before the runtime considers it eligible for expiration. This does not mean that the platform will expire the instance at the exact moment that it becomes eligible. The runtime will actually purge the instances when it sees it fit.                    

#### Connection Types {#_connection_types}

##### Connection {#config_connection}

This class (as it's name implies) provides connection instances and the
funcionality to disconnect and validate those connections.

All connection related parameters (values required in order to create a
connection) must be declared in the connection providers.

This particular example is a PoolingConnectionProvider which declares
that connections resolved by this provider will be pooled and reused.
There are other implementations like CachedConnectionProvider which
lazily creates and caches connections or simply ConnectionProvider if
you want a new connection each time something requires one.

###### Parameters {#_parameters_2}

  Name                              Type                                 Description                                                                                                                                                                                                 Default Value   Required
  --------------------------------- ------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Project ID                        String                               Project Identity                                                                                                                                                                                                            **x** 
  Service Account Key (JSON) File   String                               The service authentication credentials                                                                                                                                                                                       
  Reconnection                      [Reconnection](#Reconnection)        When the application is deployed, a connectivity test is performed on all connectors. If set to true, deployment will fail if the test doesn't pass after exhausting the associated reconnection strategy                    
  Pooling Profile                   [Pooling Profile](#PoolingProfile)   Characteristics of the connection pool                                                                                                                                                                                       

#### Associated Operations {#_associated_operations}

-   [Cancel Job](#cancelJob)  

-   [Create Dataset](#createDataset)  

-   [Create Job](#createJob)  

-   [Create Table](#createTable)  

-   [Delete Dataset](#deleteDataset)  

-   [Delete Table](#deleteTable)  

-   [Get Dataset](#getDataset)  

-   [Get Job](#getJob)  

-   [Get Query Result](#getQueryResult)  

-   [Get Table](#getTable)  

-   [Insert All](#insertAll)  

-   [List Dataset](#listDataset)  

-   [List Job](#listJob)  

-   [List Table](#listTable)  

-   [List Table Data](#listTableData)  

-   [Query](#query)  

-   [Update Dataset](#updateDataset)  

-   [Update Table](#updateTable)  

Operations {#_operations}
----------

### Cancel Job {#cancelJob}

`<bigquery:cancel-job>`

CancelJob operation sends a job cancel request. If the location of the
job is not "US" or "EU", the jobId must specify the job location. It
logs 'Job Not Found', if specified Job does not exist. It won't
log/return anything on successful execution.

#### Parameters {#_parameters_3}

  --------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                       Default Value   Required
  ----------------------- --------------------------------------------- ------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                             **x** 

  Job Name                String                                        Google BigQuery job name                                          **x** 

  Job Location            String                                        Google BigQuery job location                                       

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                    
                                                                                                                                          
                          -   [Reconnect Forever](#reconnect-forever)                                                                     
                                                                                                                                          
                                                                                                                                          
  --------------------------------------------------------------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations}

-   [Config](#config)  

#### Throws {#_throws}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:JOB\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Create Dataset {#createDataset}

`<bigquery:create-dataset>`

CreateDataset operation creates a new empty dataset. A dataset is a
grouping mechanism that holds zero or more tables.

#### Parameters {#_parameters_4}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Dataset Name            String                                        Dataset identity. Dataset ID must be alphanumeric (plus underscores, dashes, and colons) and must be at most 1024 characters long.                             **x** 

  Table Life Time         Number                                        Default lifetime of all tables in the dataset, in milliseconds. Table expiration should not be less than 3600000ms.                                             

  Description             String                                        User-friendly description for the dataset                                                                                                                       

  Friendly Name           String                                        User-friendly name for the dataset                                                                                                                              

  Labels                  Object                                        List of labels associated with labels                                                                                                                           

  Location                String                                        Geographic location where the dataset should reside                                                                                                             

  ACL                     Array of One of:                              Dataset's access control configuration                                                                                                                          
                                                                                                                                                                                                                                       
                          -   [User Acl](#UserAcl)                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                          -   [Domain Acl](#DomainAcl)                                                                                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [View Acl](#ViewAcl)                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output}

  ---------- ---------------------
  **Type**   [Dataset](#Dataset)
  ---------- ---------------------

#### For Configurations. {#_for_configurations_2}

-   [Config](#config)  

#### Throws {#_throws_2}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:DATASET\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Create Job {#createJob}

`<bigquery:create-job>`

CreateJob operation create and start an asynchronous job.

#### Parameters {#_parameters_5}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Job Config              One of:                                       Google BigQuery job configuration                                                                                                                              **x** 
                                                                                                                                                                                                                                       
                          -   [Copy Job](#CopyJob)                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                          -   [Extract Job](#ExtractJob)                                                                                                                                                                               
                                                                                                                                                                                                                                       
                          -   [Load Job](#LoadJob)                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                          -   [Query Job](#QueryJob)                                                                                                                                                                                   
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       

  Job Info                [Job Info Options](#JobInfoOptions)           Google BigQuery create job options configuration                                                                                                               **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_2}

  ---------- -------------
  **Type**   [Job](#Job)
  ---------- -------------

#### For Configurations. {#_for_configurations_3}

-   [Config](#config)  

#### Throws {#_throws_3}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:JOB\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Create Table {#createTable}

`<bigquery:create-table>`

CreateTable operation creates a new table in existing dataset.

#### Parameters {#_parameters_6}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                                             Description                                                                                                                                    Default Value   Required
  ----------------------- ---------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                                           The name of the configuration to use.                                                                                                                          **x** 

  Table Info              [Table Info Configuration](#TableInfoConfiguration)              Table information configuration to create a table                                                                                                              **x** 

  Table Fields            Array of [Table Field Configuration](#TableFieldConfiguration)   Table Schema details , Field Type , Field Name , Field Description , Field Mode , Sub-fields.                                                                   

  Table Option            [Table Info Options](#TableInfoOptions)                          Create table information options                                                                                                                                

  Target Variable         String                                                           The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                                           An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                                      A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                                          
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                     
                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                          
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_3}

  ---------- ----------------------------------------
  **Type**   [Table Information](#TableInformation)
  ---------- ----------------------------------------

#### For Configurations. {#_for_configurations_4}

-   [Config](#config)  

#### Throws {#_throws_4}

-   BIGQUERY:TABLE\_NOT\_FOUND  

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Delete Dataset {#deleteDataset}

`<bigquery:delete-dataset>`

DeleteDataset operation deletes the dataset specified by datasetId. It
logs 'Dataset Not Empty' if deleting non-empty dataset is disabled and
Dataset is still in use. It logs 'Dataset Not Found', if specified
dataset does not exist. It won't log/return anything on successful
execution.

#### Parameters {#_parameters_7}

  -----------------------------------------------------------------------------------------------------------------------------------------------------
  Name                       Type                                          Description                                       Default Value   Required
  -------------------------- --------------------------------------------- ------------------------------------------------- --------------- ----------
  Configuration              String                                        The name of the configuration to use.                             **x** 

  Dataset Id                 String                                        Google BigQuery dataset Id                                        **x** 

  Delete Non Empty Dataset   Boolean                                       Delete a dataset even if non-empty                true             

  Reconnection Strategy      -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                    
                                                                                                                                             
                             -   [Reconnect Forever](#reconnect-forever)                                                                     
                                                                                                                                             
                                                                                                                                             
  -----------------------------------------------------------------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_5}

-   [Config](#config)  

#### Throws {#_throws_5}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:DATASET\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Delete Table {#deleteTable}

`<bigquery:delete-table>`

DeleteTable operation deletes the specified table from the dataset. This
operation logs 'Table Not found', if specified table does not exist. And
it won't log/return anything on successful execution.

#### Parameters {#_parameters_8}

  --------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                       Default Value   Required
  ----------------------- --------------------------------------------- ------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                             **x** 

  Table                   [Table Configuration](#TableConfiguration)    Table Configuration with tableId and datasetId                    **x** 

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                    
                                                                                                                                          
                          -   [Reconnect Forever](#reconnect-forever)                                                                     
                                                                                                                                          
                                                                                                                                          
  --------------------------------------------------------------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_6}

-   [Config](#config)  

#### Throws {#_throws_6}

-   BIGQUERY:TABLE\_NOT\_FOUND  

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Get Dataset {#getDataset}

`<bigquery:get-dataset>`

GetDataset operation returns the dataset specified by datasetId.

#### Parameters {#_parameters_9}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Dataset Id              String                                        Google BigQuery dataset identity                                                                                                                               **x** 

  Field                   [Dataset Info Option](#DatasetInfoOption)     Get dataset options configuration                                                                                                                               

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_4}

  ---------- ---------------------
  **Type**   [Dataset](#Dataset)
  ---------- ---------------------

#### For Configurations. {#_for_configurations_7}

-   [Config](#config)  

#### Throws {#_throws_7}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:DATASET\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Get Job {#getJob}

`<bigquery:get-job>`

GetJob operation returns information about a specific job.

#### Parameters {#_parameters_10}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Job Name                String                                        Google BigQuery job name                                                                                                                                       **x** 

  Job Location            String                                        Google BigQuery job location                                                                                                                                    

  Job Fields              [Job Info Options](#JobInfoOptions)           Job information options configurations                                                                                                                          

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_5}

  ---------- -------------
  **Type**   [Job](#Job)
  ---------- -------------

#### For Configurations. {#_for_configurations_8}

-   [Config](#config)  

#### Throws {#_throws_8}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:JOB\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Get Query Result {#getQueryResult}

`<bigquery:get-query-result>`

GetQueryResult operation returns the results of a query job.

#### Parameters {#_parameters_11}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                                 Description                                                                                                                                    Default Value   Required
  ----------------------- ---------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                               The name of the configuration to use.                                                                                                                          **x** 

  Job Name                String                                               Google BigQuery job name                                                                                                                                       **x** 

  Job Location            String                                               Google BigQuery job location                                                                                                                                    

  Job Result Options      [Job Query Results Option](#JobQueryResultsOption)   Job query result options configurations                                                                                                                         

  Target Variable         String                                               The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                               An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                          A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                              
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                         
                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                              
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_6}

  ---------- ------------------------------
  **Type**   [Table Result](#TableResult)
  ---------- ------------------------------

#### For Configurations. {#_for_configurations_9}

-   [Config](#config)  

#### Throws {#_throws_9}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:JOB\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Get Table {#getTable}

`<bigquery:get-table>`

GetTable operation returns the specified table from dataset.

#### Parameters {#_parameters_12}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Dataset Id              String                                        Google BigQuery dataset identity.                                                                                                                              **x** 

  Table Id                String                                        Google BigQuery table identity.                                                                                                                                **x** 

  Table Option            [Table Info Options](#TableInfoOptions)       Get table information options                                                                                                                                   

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_7}

  ---------- ----------------------------------------
  **Type**   [Table Information](#TableInformation)
  ---------- ----------------------------------------

#### For Configurations. {#_for_configurations_10}

-   [Config](#config)  

#### Throws {#_throws_10}

-   BIGQUERY:TABLE\_NOT\_FOUND  

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Insert All {#insertAll}

`<bigquery:insert-all>`

InsertAll operation streams data into BigQuery one record at a time
without running the load job.

#### Parameters {#_parameters_13}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Rows Data               Array of Object                               Row data to be inserted                                                                                                                                        **x** 

  Ignore Unknown Values   Boolean                                       Whether to accept rows that contain values that do not match the schema.                                                                       true             

  Skip Invalid Rows       Boolean                                       Whether to insert all valid rows of a request, even if invalid rows exist.                                                                     false            

  Template Suffix         String                                        The destination table is treated as a base template.                                                                                                            

  Table Id                String                                        Table identity.                                                                                                                                                **x** 

  Dataset Id              String                                        Dataset identity.                                                                                                                                              **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_8}

  ---------- -------------------------------------------
  **Type**   [Insert All Response](#InsertAllResponse)
  ---------- -------------------------------------------

#### For Configurations. {#_for_configurations_11}

-   [Config](#config)  

#### Throws {#_throws_11}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### List Dataset {#listDataset}

`<bigquery:list-dataset>`

ListDataset operation returns partial information on each dataset:
DatasetId, FriendlyName and GeneratedId. To get complete information use
"Get Dataset" operation.

#### Parameters {#_parameters_14}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  List Dataset Option     [List Dataset Option](#ListDatasetOption)     List dataset options configuration                                                                                                                              

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_9}

  --------------------- ----------------------------------
  **Type**              Array of [Dataset](#Dataset)
  **Attributes Type**   [Page Attribute](#PageAttribute)
  --------------------- ----------------------------------

#### For Configurations. {#_for_configurations_12}

-   [Config](#config)  

#### Throws {#_throws_12}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:DATASET\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### List Job {#listJob}

`<bigquery:list-job>`

ListJob operation lists all jobs that you started in the specified
project.

#### Parameters {#_parameters_15}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Job Info                [Job Info Options](#JobInfoOptions)           Google BigQuery job options configuration                                                                                                                       

  Page Token              String                                        Specifies the token from which to start listing jobs                                                                                                            

  Page Size               Number                                        Specifies the maximum number of jobs returned per page                                                                                                          

  State                   Enumeration, one of:                          State of the job (DONE, PENDING, RUNNING)                                                                                                                       
                                                                                                                                                                                                                                       
                          -   DONE                                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                          -   PENDING                                                                                                                                                                                                  
                                                                                                                                                                                                                                       
                          -   RUNNING                                                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_10}

  --------------------- ----------------------------------
  **Type**              Array of [Job](#Job)
  **Attributes Type**   [Page Attribute](#PageAttribute)
  --------------------- ----------------------------------

#### For Configurations. {#_for_configurations_13}

-   [Config](#config)  

#### Throws {#_throws_13}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:JOB\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### List Table {#listTable}

`<bigquery:list-table>`

ListTable operation list the tables in the specified dataset. This
operation returns partial information on each table: TableId,
FriendlyName, Generated and type, which is part of Definition.

#### Parameters {#_parameters_16}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Dataset Id              String                                        Google BigQuery dataset identity.                                                                                                                              **x** 

  List Table Options      [List Table Options](#ListTableOptions)       List table options configurations                                                                                                                               

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_11}

  --------------------- -------------------------------------------------
  **Type**              Array of [Table Information](#TableInformation)
  **Attributes Type**   [Page Attribute](#PageAttribute)
  --------------------- -------------------------------------------------

#### For Configurations. {#_for_configurations_14}

-   [Config](#config)  

#### Throws {#_throws_14}

-   BIGQUERY:TABLE\_NOT\_FOUND  

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### List Table Data {#listTableData}

`<bigquery:list-table-data>`

ListTableData operation list the content of a table in rows.

#### Parameters {#_parameters_17}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Dataset Id              String                                        Google BigQuery dataset identity                                                                                                                               **x** 

  Table Id                String                                        Google BigQuery table identity                                                                                                                                 **x** 

  Page Size               Number                                        Specifies the maximum number of rows returned per page                                                                                                          

  Page Token              String                                        Page token of the request.                                                                                                                                      

  Start Index             Number                                        Start row index of the table.                                                                                                                                   

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_12}

  ---------- ------------------------------
  **Type**   [Table Result](#TableResult)
  ---------- ------------------------------

#### For Configurations. {#_for_configurations_15}

-   [Config](#config)  

#### Throws {#_throws_15}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Query

`<bigquery:query>`

Runs the query associated with the request, using the given JobId or
using an internally-generated random JobId.

#### Parameters {#_parameters_18}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Query Configuration     [Query Job](#QueryJob)                        Google BigQuery query configuration                                                                                                                            **x** 

  Job Information         [Job Info Options](#JobInfoOptions)           Google BigQuery job options configuration                                                                                                                      **x** 

  Job Name                String                                        Google BigQuery job name                                                                                                                                        

  Job Location            String                                        Google BigQuery job location                                                                                                                                    

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_13}

  ---------- ------------------------------
  **Type**   [Table Result](#TableResult)
  ---------- ------------------------------

#### For Configurations. {#_for_configurations_16}

-   [Config](#config)  

#### Throws {#_throws_16}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:JOB\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Update Dataset {#updateDataset}

`<bigquery:update-dataset>`

UpdateDataset operation updates information in an existing dataset.

#### Parameters {#_parameters_19}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Field                   [Dataset Info Option](#DatasetInfoOption)     Update dataset options configuration                                                                                                                            

  Dataset Name            String                                        Dataset identity. Dataset ID must be alphanumeric (plus underscores, dashes, and colons) and must be at most 1024 characters long.                             **x** 

  Table Life Time         Number                                        Default lifetime of all tables in the dataset, in milliseconds. Table expiration should not be less than 3600000ms.                                             

  Description             String                                        User-friendly description for the dataset                                                                                                                       

  Friendly Name           String                                        User-friendly name for the dataset                                                                                                                              

  Labels                  Object                                        List of labels associated with labels                                                                                                                           

  Location                String                                        Geographic location where the dataset should reside                                                                                                             

  ACL                     Array of One of:                              Dataset's access control configuration                                                                                                                          
                                                                                                                                                                                                                                       
                          -   [User Acl](#UserAcl)                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                          -   [Domain Acl](#DomainAcl)                                                                                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [View Acl](#ViewAcl)                                                                                                                                                                                     
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_14}

  ---------- ---------------------
  **Type**   [Dataset](#Dataset)
  ---------- ---------------------

#### For Configurations. {#_for_configurations_17}

-   [Config](#config)  

#### Throws {#_throws_17}

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   BIGQUERY:DATASET\_NOT\_FOUND  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

### Update Table {#updateTable}

`<bigquery:update-table>`

UpdateTable operation updates information in an existing table.

#### Parameters {#_parameters_20}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                                             Description                                                                                                                                    Default Value   Required
  ----------------------- ---------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                                           The name of the configuration to use.                                                                                                                          **x** 

  Table Info              [Table Info Configuration](#TableInfoConfiguration)              Table information configuration to update table                                                                                                                **x** 

  Table Fields            Array of [Table Field Configuration](#TableFieldConfiguration)   Table Schema details , Field Type , Field Name , Field Description , Field Mode , Sub-fields.                                                                  **x** 

  Table Option            [Table Info Options](#TableInfoOptions)                          Table options configurations                                                                                                                                   **x** 

  Target Variable         String                                                           The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                                           An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                                      A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                                          
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                     
                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                          
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_15}

  ---------- ----------------------------------------
  **Type**   [Table Information](#TableInformation)
  ---------- ----------------------------------------

#### For Configurations. {#_for_configurations_18}

-   [Config](#config)  

#### Throws {#_throws_18}

-   BIGQUERY:TABLE\_NOT\_FOUND  

-   BIGQUERY:EXECUTION  

-   BIGQUERY:CONNECTIVITY  

-   MULE:CONNECTIVITY  

-   BIGQUERY:RETRY\_EXHAUSTED  

Types {#_types}
-----

### Reconnection {#Reconnection}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                   Type                                          Description                                                                                                                                                                                                 Default Value   Required
  ----------------------- --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Fails Deployment        Boolean                                       When the application is deployed, a connectivity test is performed on all connectors. If set to true, deployment will fail if the test doesn’t pass after exhausting the associated reconnection strategy                   

  Reconnection Strategy   -   [Reconnect](#reconnect)                   The reconnection strategy to use                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                    
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                    
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Reconnect

  Field       Type     Description                              Default Value   Required
  ----------- -------- ---------------------------------------- --------------- ----------
  Frequency   Number   How often (in ms) to reconnect                           
  Count       Number   How many reconnection attempts to make                   

### Reconnect Forever

  Field       Type     Description                      Default Value   Required
  ----------- -------- -------------------------------- --------------- ----------
  Frequency   Number   How often (in ms) to reconnect                   

### Pooling Profile {#PoolingProfile}

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                            Type                        Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          Default Value   Required
  -------------------------------- --------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Max Active                       Number                      Controls the maximum number of Mule components that can be borrowed from a session at one time. When set to a negative value, there is no limit to the number of components that may be active at one time. When maxActive is exceeded, the pool is said to be exhausted.                                                                                                                                                                                                                                                                                                                                                                            

  Max Idle                         Number                      Controls the maximum number of Mule components that can sit idle in the pool at any time. When set to a negative value, there is no limit to the number of Mule components that may be idle at one time.                                                                                                                                                                                                                                                                                                                                                                                                                                             

  Max Wait                         Number                      Specifies the number of milliseconds to wait for a pooled component to become available when the pool is exhausted and the exhaustedAction is set to WHEN\_EXHAUSTED\_WAIT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          

  Min Eviction Millis              Number                      Determines the minimum amount of time an object may sit idle in the pool before it is eligible for eviction. When non-positive, no objects will be evicted from the pool due to idle time alone.                                                                                                                                                                                                                                                                                                                                                                                                                                                     

  Eviction Check Interval Millis   Number                      Specifies the number of milliseconds between runs of the object evictor. When non-positive, no object evictor is executed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  Exhausted Action                 Enumeration, one of:        Specifies the behavior of the Mule component pool when the pool is exhausted. Possible values are: "WHEN\_EXHAUSTED\_FAIL", which will throw a NoSuchElementException, "WHEN\_EXHAUSTED\_WAIT", which will block by invoking Object.wait(long) until a new or idle object is available, or WHEN\_EXHAUSTED\_GROW, which will create a new Mule instance and return it, essentially making maxActive meaningless. If a positive maxWait value is supplied, it will block for at most that many milliseconds, after which a NoSuchElementException will be thrown. If maxThreadWait is a negative value, it will block indefinitely.                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                   -   WHEN\_EXHAUSTED\_GROW                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                   -   WHEN\_EXHAUSTED\_WAIT                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                   -   WHEN\_EXHAUSTED\_FAIL                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

  Initialisation Policy            Enumeration, one of:        Determines how components in a pool should be initialized. The possible values are: INITIALISE\_NONE (will not load any components into the pool on startup), INITIALISE\_ONE (will load one initial component into the pool on startup), or INITIALISE\_ALL (will load all components in the pool on startup)                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                   -   INITIALISE\_NONE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                   -   INITIALISE\_ONE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                   -   INITIALISE\_ALL                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

  Disabled                         Boolean                     Whether pooling should be disabled                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Expiration Policy {#ExpirationPolicy}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field           Type                   Description                                                                                                                                                       Default Value   Required
  --------------- ---------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Max Idle Time   Number                 A scalar time value for the maximum amount of time a dynamic configuration instance should be allowed to be idle before it’s considered eligible for expiration                   

  Time Unit       Enumeration, one of:   A time unit that qualifies the maxIdleTime attribute                                                                                                                              
                                                                                                                                                                                                                           
                  -   NANOSECONDS                                                                                                                                                                                          
                                                                                                                                                                                                                           
                  -   MICROSECONDS                                                                                                                                                                                         
                                                                                                                                                                                                                           
                  -   MILLISECONDS                                                                                                                                                                                         
                                                                                                                                                                                                                           
                  -   SECONDS                                                                                                                                                                                              
                                                                                                                                                                                                                           
                  -   MINUTES                                                                                                                                                                                              
                                                                                                                                                                                                                           
                  -   HOURS                                                                                                                                                                                                
                                                                                                                                                                                                                           
                  -   DAYS                                                                                                                                                                                                 
                                                                                                                                                                                                                           
                                                                                                                                                                                                                           
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Dataset {#Dataset}

  Field                    Type                       Description                                                                                           Default Value   Required
  ------------------------ -------------------------- ----------------------------------------------------------------------------------------------------- --------------- ----------
  Acl                      Array of [Acl](#Acl)       Dataset’s access control configuration                                                                                
  Creation Time            Number                     The time when this dataset was created, in milliseconds since the epoch.                                              
  Dataset Id               [Dataset Id](#DatasetId)   The dataset identity.                                                                                                 
  Default Table Lifetime   Number                     The default lifetime of all tables in the dataset, in milliseconds.                                                   
  Description              String                     A user-friendly description for the dataset.                                                                          
  Etag                     String                     The hash of the dataset resource.                                                                                     
  Friendly Name            String                     A user-friendly name for the dataset.                                                                                 
  Generated Id             String                     The service-generated id for the dataset.                                                                             
  Labels                   Object                     A map for labels applied to the dataset.                                                                              
  Last Modified            Number                     The time when this dataset or any of its tables was last modified, in milliseconds since the epoch.                   
  Location                 String                     The geographic location where the dataset should reside.                                                              
  Self Link                String                     URL that can be used to access the resource again.                                                                    

### Acl {#Acl}

Refer
[Acl](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/Acl.html)
for more detailed information

  Field    Type                Description                                                                 Default Value   Required
  -------- ------------------- --------------------------------------------------------------------------- --------------- ----------
  Entity   [Entity](#Entity)   Base class for BigQuery entities that can be grant access to the dataset.                   
  Role     [[Role]](#Role)     Dataset roles supported by BigQuery.                                                        

### Entity {#Entity}

  ---------------------------------------------------------------------------------------
  Field   Type                   Description                   Default Value   Required
  ------- ---------------------- ----------------------------- --------------- ----------
  Type    Enumeration, one of:   Types of BigQuery entities.                   
                                                                               
          -   DOMAIN                                                           
                                                                               
          -   GROUP                                                            
                                                                               
          -   USER                                                             
                                                                               
          -   VIEW                                                             
                                                                               
                                                                               
  ---------------------------------------------------------------------------------------

### Dataset Id {#DatasetId}

  Field     Type     Description        Default Value   Required
  --------- -------- ------------------ --------------- ----------
  Dataset   String   Dataset Identity                   
  Project   String   Project Name                       

### Job {#Job}

  Field           Type                                     Description                                                                     Default Value   Required
  --------------- ---------------------------------------- ------------------------------------------------------------------------------- --------------- ----------
  Configuration   [Job Configuration](#JobConfiguration)   The job’s configuration                                                                         
  Etag            String                                   The hash of the job resource.                                                                   
  Generated Id    String                                   The service-generated id for the job.                                                           
  Job Id          [Job Id](#JobId)                         The job identity.                                                                               
  Self Link       String                                   URL that can be used to access the resource again.                                              
  Statistics      [Job Statistics](#JobStatistics)         Information about the job, including starting time and ending time of the job                   
  Status          [Job Status](#JobStatus)                 The status of this job.                                                                         
  User Email      String                                   The email address of the user who ran the job.                                                  

### Job Configuration {#JobConfiguration}

Refer [Job
Configuration](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobConfiguration.html)
for more detailed information

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field   Type                   Description                                                                                                                                                                           Default Value   Required
  ------- ---------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Type    Enumeration, one of:   Base class for a BigQuery job configuration. [Job Configuration](https://googleapis.dev/java/google-cloud-clients/latest/index.html?com/google/cloud/bigquery/package-summary.html)                   
                                                                                                                                                                                                                                       
          -   COPY                                                                                                                                                                                                                     
                                                                                                                                                                                                                                       
          -   EXTRACT                                                                                                                                                                                                                  
                                                                                                                                                                                                                                       
          -   LOAD                                                                                                                                                                                                                     
                                                                                                                                                                                                                                       
          -   QUERY                                                                                                                                                                                                                    
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Job Id {#JobId}

  Field      Type     Description           Default Value   Required
  ---------- -------- --------------------- --------------- ----------
  Job        String   The job’s id.                         
  Location   String   The job’s location.                   
  Project    String   Job’s project id.                     

### Job Statistics {#JobStatistics}

Refer [Job
Statistics](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobStatistics.html)
for more detailed

  Field           Type     Description                                                 Default Value   Required
  --------------- -------- ----------------------------------------------------------- --------------- ----------
  Creation Time   Number   The creation time of the job in milliseconds since epoch.                   
  End Time        Number   The end time of the job in milliseconds since epoch.                        
  Start Time      Number   The start time of the job in milliseconds since epoch.                      

### Job Status {#JobStatus}

Refer [Job
Status](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobStatus.html)
for more detailed information

  Field              Type                                         Description                                             Default Value   Required
  ------------------ -------------------------------------------- ------------------------------------------------------- --------------- ----------
  Error              [Big Query Error](#BigQueryError)            The final error result of the job.                                      
  Execution Errors   Array of [Big Query Error](#BigQueryError)   All errors encountered during the running of the job.                   
  State              [[State]](#State)                            The state of the job.                                                   

### Big Query Error {#BigQueryError}

Refer [Big Query
Error](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/BigQueryError.html)
for more detailed information

  Field      Type     Description                                   Default Value   Required
  ---------- -------- --------------------------------------------- --------------- ----------
  Location   String   Location where the error occurred                             
  Message    String   A human-readable description of the error.                    
  Reason     String   Short error code that summarizes the error.                   

### Job Info Options {#JobInfoOptions}

  Field           Type      Description                                                                                                            Default Value   Required
  --------------- --------- ---------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration   Boolean   Job Configuration                                                                                                      true            
  E Tag           Boolean   Job eTag                                                                                                               false           
  Id              Boolean   Job Identity                                                                                                           true            
  Job Reference   Boolean   A job reference is a fully qualified identifier for refering to a job.                                                 true            
  Self Link       Boolean   A URL that can be used to access the resource again. You can use this URL in Get or Update requests to the resource.   false           
  Statistics      Boolean   Information about the job, including starting time and ending time of the job.                                         true            
  Status          Boolean   The status of this job.                                                                                                true            
  User Mail       Boolean   The email address of the user who ran the job.                                                                         true            

### Table Information {#TableInformation}

  Field                      Type                                                   Description                                                                                                                                                                           Default Value   Required
  -------------------------- ------------------------------------------------------ ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Creation Time              Number                                                 The time when this table was created, in milliseconds since the epoch.                                                                                                                                
  Description                String                                                 Table Description                                                                                                                                                                                     
  E Tag                      String                                                 A hash of the page of results.                                                                                                                                                                        
  Encryption Configuration   [Encryption Configuration](#EncryptionConfiguration)   Custom encryption configuration (e.g., Cloud KMS keys).                                                                                                                                               
  Expiration Time            Number                                                 The time when this table expires, in milliseconds since the epoch. If not present, the table will persist indefinitely. Expired tables will be deleted and their storage reclaimed.                   
  Friendly Name              String                                                 The user-friendly name for the table.                                                                                                                                                                 
  Generated Id               String                                                 The service-generated id for the table.                                                                                                                                                               
  Labels                     Object                                                 A map for labels applied to the table.                                                                                                                                                                
  Last Modified Time         Number                                                 Table last modified time                                                                                                                                                                              
  Num Bytes                  Number                                                 The size of the table in bytes                                                                                                                                                                        
  Num Long Term Bytes        Number                                                 The number of bytes considered "long-term storage" for reduced billing purposes.                                                                                                                      
  Num Rows                   Number                                                 Number of rows in a table                                                                                                                                                                             
  Self Link                  String                                                 An URL that can be used to access the resource again.                                                                                                                                                 
  Table Configuration        [Table Id](#TableId)                                   Table Identity                                                                                                                                                                                        
  Table Definition           [Table Definition](#TableDefinition)                   Table Definition                                                                                                                                                                                      

### Encryption Configuration {#EncryptionConfiguration}

Refer [Encryption
Configuration](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/EncryptionConfiguration.html)
for more detailed information

  Field          Type     Description                                               Default Value   Required
  -------------- -------- --------------------------------------------------------- --------------- ----------
  Kms Key Name   String   Custom encryption configuration (e.g., Cloud KMS keys).                   

### Table Id {#TableId}

  Field        Type     Description                  Default Value   Required
  ------------ -------- ---------------------------- --------------- ----------
  Dataset      String   Dataset Identity                             
  Project Id   String   Project’s user-defined id.                   
  Table        String   Table Identity                               

### Table Definition {#TableDefinition}

Refer [Table
Definition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/TableDefinition.html)
for more detailed information

  Field    Type                Description           Default Value   Required
  -------- ------------------- --------------------- --------------- ----------
  Schema   [Schema](#Schema)   The table’s schema.                   
  Type     [[Type]](#Type)     The table’s type.                     

### Schema {#Schema}

Refer
[Schema](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/Schema.html)
for more detailed information

  Field    Type                       Description                               Default Value   Required
  -------- -------------------------- ----------------------------------------- --------------- ----------
  Fields   Array of [Field](#Field)   The fields in the current table schema.                   

### Field {#Field}

  ---------------------------------------------------------------------------------------------------------
  Field         Type                                         Description         Default Value   Required
  ------------- -------------------------------------------- ------------------- --------------- ----------
  Description   String                                       Field Description                   

  Mode          Enumeration, one of:                         Field Mode                          
                                                                                                 
                -   NULLABLE                                                                     
                                                                                                 
                -   REQUIRED                                                                     
                                                                                                 
                -   REPEATED                                                                     
                                                                                                 
                                                                                                 

  Name          String                                       Field Name                          

  Sub Fields    Array of [Field](#Field)                     Sub Fields                          

  Type          [Legacy SQL Type Name](#LegacySQLTypeName)   The field type.                     
  ---------------------------------------------------------------------------------------------------------

### Legacy SQL Type Name {#LegacySQLTypeName}

  -------------------------------------------------------------------------------------------------------
  Field           Type                   Description                           Default Value   Required
  --------------- ---------------------- ------------------------------------- --------------- ----------
  Standard Type   Enumeration, one of:   A type used in legacy SQL contexts.                   
                                                                                               
                  -   BOOL                                                                     
                                                                                               
                  -   INT64                                                                    
                                                                                               
                  -   FLOAT64                                                                  
                                                                                               
                  -   NUMERIC                                                                  
                                                                                               
                  -   STRING                                                                   
                                                                                               
                  -   BYTES                                                                    
                                                                                               
                  -   STRUCT                                                                   
                                                                                               
                  -   ARRAY                                                                    
                                                                                               
                  -   TIMESTAMP                                                                
                                                                                               
                  -   DATE                                                                     
                                                                                               
                  -   TIME                                                                     
                                                                                               
                  -   DATETIME                                                                 
                                                                                               
                  -   GEOGRAPHY                                                                
                                                                                               
                                                                                               
  -------------------------------------------------------------------------------------------------------

### Table Info Configuration {#TableInfoConfiguration}

  Field             Type                                         Description                                                                                                                                                                           Default Value   Required
  ----------------- -------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Table             [Table Configuration](#TableConfiguration)   Details of table(Table Name, Dataset Name)                                                                                                                                                            x
  Table Schema      [Table Schema](#TableSchema)                 Details of Table Schema(Table Fields)                                                                                                                                                                 x
  Description       String                                       Table Description                                                                                                                                                                                     
  Kms Key Name      String                                       Creates a EncryptionConfiguration object for KMS key name                                                                                                                                             
  Expiration Time   Number                                       The time when this table expires, in milliseconds since the epoch. If not present, the table will persist indefinitely. Expired tables will be deleted and their storage reclaimed.                   
  Friendly Name     String                                       The user-friendly name for the table.                                                                                                                                                                 
  Labels            Object                                       The labels associated with the table. Can be used to organize and group your tables.                                                                                                                  

### Table Configuration {#TableConfiguration}

  Field     Type     Description         Default Value   Required
  --------- -------- ------------------- --------------- ----------
  Table     String   Table identity.                     x
  Dataset   String   Dataset identity.                   x

### Table Schema {#TableSchema}

  Field          Type                                                             Description                                                                                                          Default Value   Required
  -------------- ---------------------------------------------------------------- -------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Table Fields   Array of [Table Field Configuration](#TableFieldConfiguration)   Table field contains Datatype , Field Mode , Field Name , Field Type , Field Description to configure Table Schema                   

### Table Field Configuration {#TableFieldConfiguration}

  -----------------------------------------------------------------------------------------------------------------------------------
  Field               Type                                                             Description         Default Value   Required
  ------------------- ---------------------------------------------------------------- ------------------- --------------- ----------
  Field Name          String                                                           Field Name                          x

  Field Type          Enumeration, one of:                                             Field Type                          x
                                                                                                                           
                      -   BOOLEAN                                                                                          
                                                                                                                           
                      -   BYTES                                                                                            
                                                                                                                           
                      -   DATE                                                                                             
                                                                                                                           
                      -   DATETIME                                                                                         
                                                                                                                           
                      -   FLOAT                                                                                            
                                                                                                                           
                      -   INTEGER                                                                                          
                                                                                                                           
                      -   RECORD                                                                                           
                                                                                                                           
                      -   STRING                                                                                           
                                                                                                                           
                      -   TIME                                                                                             
                                                                                                                           
                      -   TIMESTAMP                                                                                        
                                                                                                                           
                                                                                                                           

  Field Description   String                                                           Field Description                   

  Field Mode          Enumeration, one of:                                             Field Mode                          
                                                                                                                           
                      -   NULLABLE                                                                                         
                                                                                                                           
                      -   REQUIRED                                                                                         
                                                                                                                           
                      -   REPEATED                                                                                         
                                                                                                                           
                                                                                                                           

  Field Sub Fields    Array of [Table Field Configuration](#TableFieldConfiguration)   Sub Fields                          
  -----------------------------------------------------------------------------------------------------------------------------------

### Table Info Options {#TableInfoOptions}

  Field                Type      Description                                                                                                                                                                           Default Value   Required
  -------------------- --------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Creation Time        Boolean   The time when this table was created, in milliseconds since the epoch.                                                                                                                true            
  Description          Boolean   Table Description                                                                                                                                                                     true            
  E Tag                Boolean   A hash of the page of results.                                                                                                                                                        true            
  Expiration Time      Boolean   The time when this table expires, in milliseconds since the epoch. If not present, the table will persist indefinitely. Expired tables will be deleted and their storage reclaimed.   true            
  Friendly Name        Boolean   The user-friendly name for the table.                                                                                                                                                 true            
  Id                   Boolean   An opaque ID of the table.                                                                                                                                                            true            
  Last Modified Time   Boolean   Table last modified time                                                                                                                                                              true            
  Location             Boolean   The geographic location where the table should reside. Possible values include EU and US. The default value is US.                                                                    true            
  Num Bytes            Boolean   The size of the table in bytes                                                                                                                                                        true            
  Num Rows             Boolean   Number of rows in a table                                                                                                                                                             true            
  Schema               Boolean   Table Schema                                                                                                                                                                          true            
  Self Link            Boolean   A URL that can be used to access the resource again. You can use this URL in Get or Update requests to the resource.                                                                  true            
  Streaming Buffer     Boolean                                                                                                                                                                                         true            
  Time Partitioning    Boolean   Configures time-based partitioning for the table.                                                                                                                                     true            
  Type                 Boolean   The type of table.                                                                                                                                                                    true            
  View                 Boolean   The view definition of table                                                                                                                                                          true            

### Dataset Info Option {#DatasetInfoOption}

  Field                Type      Description                                                                                                            Default Value   Required
  -------------------- --------- ---------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Access               Boolean   It defines dataset access for one or more entities                                                                     true            
  Creation Time        Boolean   Creation time of Dataset                                                                                               true            
  Dataset Reference    Boolean   A reference that identifies the dataset.                                                                               true            
  Description          Boolean   Dataset description                                                                                                    true            
  E Tag                Boolean   Dataset eTag                                                                                                           true            
  Friendly Name        Boolean   Dataset friendly name                                                                                                  true            
  Labels               Boolean   Dataset Labels                                                                                                         true            
  Last Modified Time   Boolean   Dataset last modified time                                                                                             true            
  Location             Boolean   The geographic location where the dataset should reside. Possible values include EU and US. The default value is US.   true            
  Self Link            Boolean   A URL that can be used to access the resource again. You can use this URL in Get or Update requests to the resource.   true            
  Id                   Boolean   Dataset Identity                                                                                                       true            

### Table Result {#TableResult}

  Field             Type                                           Description                                                                                                                                       Default Value   Required
  ----------------- ---------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Next Page         [Table Result](#TableResult)                   The next page of result.                                                                                                                                          
  Next Page Token   String                                         The token of next page of result.                                                                                                                                 
  Schema            [Schema](#Schema)                              It represents the schema for a Google BigQuery Table or data source.                                                                                              
  Total Rows        Number                                         Total number of rows in the complete result set, which can be more than the number of rows in the first page of results returned by getValues()                   
  Values            Array of Array of [Field Value](#FieldValue)   Represent rows in returned query result (table row).                                                                                                              

### Field Value {#FieldValue}

Refer [Field
Value](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/FieldValue.html)
for detail documentation.

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field             Type                                  Description                                                                                      Default Value   Required
  ----------------- ------------------------------------- ------------------------------------------------------------------------------------------------ --------------- ----------
  Attribute         Enumeration, one of:                  The attribute of this Field Value.                                                                               
                                                                                                                                                                           
                    -   PRIMITIVE                                                                                                                                          
                                                                                                                                                                           
                    -   REPEATED                                                                                                                                           
                                                                                                                                                                           
                    -   RECORD                                                                                                                                             
                                                                                                                                                                           
                                                                                                                                                                           

  Boolean Value     Boolean                               The field’s value as a Boolean.                                                                                  

  Bytes Value       Binary                                The field’s value as a byte array.                                                                               

  Double Value      Number                                The field’s value as a Double.                                                                                   

  Long Value        Number                                The field’s value as a long.                                                                                     

  Null              Boolean                               True if this field’s value is null, false otherwise.                                                             

  Numeric Value     Number                                The field’s value as a BigDecimal.                                                                               

  Record Value      Array of [Field Value](#FieldValue)   The field’s value as a FieldValueList instance.                                                                  

  Repeated Value    Array of [Field Value](#FieldValue)   The field’s value as a list of FieldValue.                                                                       

  String Value      String                                The field’s value as a String.                                                                                   

  Timestamp Value   Number                                The field’s value as a long, representing a timestamp in microseconds since epoch (UNIX time).                   

  Value             Any                                   The field’s value as an Object.                                                                                  
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Job Query Results Option {#JobQueryResultsOption}

  Field           Type     Description                                                                                                                                                               Default Value   Required
  --------------- -------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Max Wait Time   Number   How long to wait for the query to complete, in milliseconds, before the request times out and returns. Note that this is only a timeout for the request, not the query.                   
  Page Size       Number   Number of records to be displayed on a page.                                                                                                                                              
  Page Token      String   Specify the page token from which to start listing datasets                                                                                                                               
  Start Index     Number   Zero-based index of the starting row.                                                                                                                                                     

### Insert All Response {#InsertAllResponse}

  Field           Type     Description                                                                                                                                                       Default Value   Required
  --------------- -------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Insert Errors   Object   All insertion errors as a map whose keys are indexes of rows that failed to insert. Each failed row index is associated with a non-empty list of BigQueryError.                   

### Page Attribute {#PageAttribute}

  Field           Type      Description                                                                                        Default Value   Required
  --------------- --------- -------------------------------------------------------------------------------------------------- --------------- ----------
  Has Next Page   Boolean   Used for paging results. When this field is true, it indicates additional results are available.                   
  Page Token      String    Specify the page token from which to start listing datasets                                                        

### List Dataset Option {#ListDatasetOption}

  Field        Type      Description                                                   Default Value   Required
  ------------ --------- ------------------------------------------------------------- --------------- ----------
  All          Boolean   List all datasets, even hidden ones.                          false           
  Page Size    Number    Specify the maximum number of datasets returned per page                      x
  Page Token   String    Specify the page token from which to start listing datasets                   

### List Table Options {#ListTableOptions}

  Field        Type     Description                                                Default Value   Required
  ------------ -------- ---------------------------------------------------------- --------------- ----------
  Page Size    Number   Specify the maximum number of datasets returned per page                   
  Page Token   String   The page token from which to start listing datasets                        

### Query Job {#QueryJob}

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                               Type                                                                                        Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                              Default Value   Required
  ----------------------------------- ------------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Query String                        String                                                                                      A query string, following the BigQuery query syntax, of the query to execute.                                                                                                                                                                                                                                                                                                                                                                                                                            x

  Allow Large Results                 Boolean                                                                                     Sets whether the job is enabled to create arbitrarily large results. If true the query is allowed to create large results at a slight cost in performance. If true Destination Table must be provided.                                                                                                                                                                                                                                                                                   false           

  Default Dataset                     String                                                                                      Specifies the default datasetId and projectId to assume for any unqualified table names in the query. If not set, all table names in the query string must be qualified in the format 'datasetId.tableId'.                                                                                                                                                                                                                                                                                               

  Dry Run                             Boolean                                                                                     If set to true, BigQuery doesn’t run the job. Instead, if the query is valid, BigQuery returns statistics about the job such as how many bytes would be processed. If the query is invalid, an error returns. The default value is false.                                                                                                                                                                                                                                                false           

  Flatten Results                     Boolean                                                                                     Sets whether nested and repeated fields should be flattened. If set to false AllowLargeResults must be true. By default results are flattened.                                                                                                                                                                                                                                                                                                                                           true            

  Maximum Billing Tier                Number                                                                                      Limits the billing tier for this job. Queries that have resource usage beyond this tier will fail (without incurring a charge). If unspecified, this will be set to your project default.                                                                                                                                                                                                                                                                                                                

  Named Parameters                    Array of [Named Parameter Configuration](#NamedParameterConfiguration)                      the query parameters to a set of named query parameters to use in the query. Named parameters are denoted using an @ prefix, e.g. @myParam for a parameter named "myParam". SELECT \* FROM \<table\> WHERE \<column\_name\>=@myParam in query                                                                                                                                                                                                                                                            

  Positional Query Parameter Values   Array of [Query Parameter Value Configuration](#QueryParameterValueConfiguration)           Sets the query parameters to a list of positional query parameters to use in the query. Positional parameters are denoted in the query with a question mark (?). SELECT \* FROM \<table\> WHERE \<column\_name\>=?                                                                                                                                                                                                                                                                                       

  Priority                            Enumeration, one of:                                                                        a priority for the query. If not specified the priority is assumed to be INTERACTIVE. Query is executed as soon as possible and count towards the concurrent rate limit and the daily rate limit.                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   INTERACTIVE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   BATCH                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  External Table Definitions          Array of [External Table Definition Configuration](#ExternalTableDefinitionConfiguration)   BigQuery’s external tables are tables whose data reside outside of BigQuery But can be queried as normal BigQuery tables.                                                                                                                                                                                                                                                                                                                                                                                

  Use Legacy Sql                      Boolean                                                                                     UseLegacySql must be set to false to use query parameters                                                                                                                                                                                                                                                                                                                                                                                                                                false           

  Use Query Cache                     Boolean                                                                                     Whether to look for the result in the query cache. The query cache is a best-effort cache that will be flushed whenever tables in the query are modified. Moreover, the query cache is only available when Destination Table is not set.                                                                                                                                                                                                                                                 true            

  User Defined Functions              Array of [User Defined Function Configuration](#UserDefinedFunctionConfiguration)           For legacy SQL, specify user defined function here. For Standard SQL, specify user defined function in Query string.                                                                                                                                                                                                                                                                                                                                                                                     

  Create Disposition                  Enumeration, one of:                                                                        Whether the job is allowed to create new tables CREATE\_IF\_NEEDED :- Configures the job to create the table if it does not exist. CREATE\_NEVER :- Configures the job to fail with a not-found error if the table does not exist. [Create Disposition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.CreateDisposition.html)                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   CREATE\_IF\_NEEDED                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   CREATE\_NEVER                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  Destination Table                   [Table Configuration](#TableConfiguration)                                                  Sets the table where to put query results. If not provided a new table is created. This value is required if Allow Large Results is set to true.                                                                                                                                                                                                                                                                                                                                                         

  Schema Update Option                Enumeration, one of:                                                                        Specifies options relating to allowing the schema of the destination table To be updated as a side effect of the load or query job. [Schema Update Option](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.SchemaUpdateOption.html)                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   ALLOW\_FIELD\_ADDITION                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   ALLOW\_FIELD\_RELAXATION                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  Write Disposition                   Enumeration, one of:                                                                        Action that should occur if the destination table already exists. WRITE\_APPEND :- Configures the job to append data to the table if it already exists. WRITE\_EMPTY :- Configures the job to fail with a duplicate error if the table already exists. WRITE\_TRUNCATE :- Configures the job to overwrite the table data if table already exists. [Write Disposition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.WriteDisposition.html)                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   WRITE\_TRUNCATE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   WRITE\_APPEND                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                      -   WRITE\_EMPTY                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  Kms Key Name                        String                                                                                      Creates a EncryptionConfiguration object for KMS key name                                                                                                                                                                                                                                                                                                                                                                                                                                                
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Named Parameter Configuration {#NamedParameterConfiguration}

  Field             Type                                                                       Description                                                      Default Value   Required
  ----------------- -------------------------------------------------------------------------- ---------------------------------------------------------------- --------------- ----------
  Key               String                                                                     A parameter given to a query.                                                    x
  Named Parameter   [Query Parameter Value Configuration](#QueryParameterValueConfiguration)   Contains the type of the parameter and value of the parameter.                   x

### Query Parameter Value Configuration {#QueryParameterValueConfiguration}

  -----------------------------------------------------------------------------------------------------------------------
  Field        Type                   Description                                              Default Value   Required
  ------------ ---------------------- -------------------------------------------------------- --------------- ----------
  Array Type   Boolean                The type of the array’s elements, if this is an array.   false           

  Type         Enumeration, one of:   The type of the parameter.                                               x
                                                                                                               
               -   BOOL                                                                                        
                                                                                                               
               -   BYTES                                                                                       
                                                                                                               
               -   DATE                                                                                        
                                                                                                               
               -   DATETIME                                                                                    
                                                                                                               
               -   FLOAT64                                                                                     
                                                                                                               
               -   INT64                                                                                       
                                                                                                               
               -   NUMERIC                                                                                     
                                                                                                               
               -   STRING                                                                                      
                                                                                                               
               -   TIME                                                                                        
                                                                                                               
               -   TIMESTAMP                                                                                   
                                                                                                               
                                                                                                               

  Values       Array of String        The values of the parameter.                                             x
  -----------------------------------------------------------------------------------------------------------------------

### External Table Definition Configuration {#ExternalTableDefinitionConfiguration}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field          Type                           Description                                                                                                                                                                                                                                                                                           Default Value   Required
  -------------- ------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Table Name     String                         Table Identity                                                                                                                                                                                                                                                                                                        x

  Source Uris    Array of String                The fully-qualified URIs that point to your data in Google Cloud Storage. Each URI can contain one '\*' wildcard character that must come after the bucket’s name. Size limits related to load jobs apply to external data sources, plus an additional limit of 10 GB maximum size across all URIs.                   x

  Table Schema   [Table Schema](#TableSchema)   The Schema for the external data                                                                                                                                                                                                                                                                                      x

  Format         Enumeration, one of:           The source format of the external data                                                                                                                                                                                                                                                                                x
                                                                                                                                                                                                                                                                                                                                                                      
                 -   AVRO                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                                                      
                 -   CSV                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                      
                 -   DATASTORE\_BACKUP                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                      
                 -   GOOGLE\_SHEETS                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                                      
                 -   JSON                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                                                      
                 -   ORC                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                      
                 -   PARQUET                                                                                                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                      
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### User Defined Function Configuration {#UserDefinedFunctionConfiguration}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field     Type                   Description                                                                                                                                                                                                  Default Value   Required
  --------- ---------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Type      Enumeration, one of:   Type of user-defined function. User defined functions can be provided inline as code blobs                                                                                                                                   x
                                                                                                                                                                                                                                                                
            -   INLINE                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                
            -   FROM\_URI                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                

  Content   String                 If getType() is UserDefinedFunction.Type.INLINE this method returns a code blob. If getType() is UserDefinedFunction.Type.FROM\_URI the method returns a Google Cloud Storage URI (e.g. gs://bucket/path).                   x
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### User Acl {#UserAcl}

  --------------------------------------------------------------------------------------
  Field       Type                   Description              Default Value   Required
  ----------- ---------------------- ------------------------ --------------- ----------
  Email       String                 User’s email address.                    x

  User Role   Enumeration, one of:   Role specified to user                   x
                                                                              
              -   OWNER                                                       
                                                                              
              -   READER                                                      
                                                                              
              -   WRITER                                                      
                                                                              
                                                                              
  --------------------------------------------------------------------------------------

### Domain Acl {#DomainAcl}

  -------------------------------------------------------------------------------------
  Field    Type                   Description                Default Value   Required
  -------- ---------------------- -------------------------- --------------- ----------
  Domain   String                 The domain name.                           x

  Role     Enumeration, one of:   Role specified to domain                   x
                                                                             
           -   OWNER                                                         
                                                                             
           -   READER                                                        
                                                                             
           -   WRITER                                                        
                                                                             
                                                                             
  -------------------------------------------------------------------------------------

### View Acl {#ViewAcl}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field     Type                   Description                                                                                                                          Default Value   Required
  --------- ---------------------- ------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Project   String                 Project IDs must contain 6-63 lowercase letters, digits, or dashes. IDs must start with a letter and may not end with a dash.                        x

  Dataset   String                 Dataset identity. Dataset ID must be alphanumeric (plus underscores, dashes, and colons) and must be at most 1024 characters long.                   x

  Table     String                 Table IDs must be alphanumeric (plus underscores) and must be at most 1024 characters long.                                                          x

  Role      Enumeration, one of:   Role specified to view                                                                                                                               x
                                                                                                                                                                                        
            -   OWNER                                                                                                                                                                   
                                                                                                                                                                                        
            -   READER                                                                                                                                                                  
                                                                                                                                                                                        
            -   WRITER                                                                                                                                                                  
                                                                                                                                                                                        
                                                                                                                                                                                        
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Copy Job {#CopyJob}

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                Type                                                  Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                              Default Value   Required
  -------------------- ----------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Source Tables        Array of [Table Configuration](#TableConfiguration)   Contains Table and Dataset name. It will copy the data from one or more source tables to a destination table.                                                                                                                                                                                                                                                                                                                                                                                            x

  Destination Table    [Table Configuration](#TableConfiguration)            Data will get copied to a destination table.                                                                                                                                                                                                                                                                                                                                                                                                                                                             x

  Create Disposition   Enumeration, one of:                                  Whether the job is allowed to create new tables CREATE\_IF\_NEEDED :- Configures the job to create the table if it does not exist. CREATE\_NEVER :- Configures the job to fail with a not-found error if the table does not exist. [Create Disposition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.CreateDisposition.html)                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                       -   CREATE\_IF\_NEEDED                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                       -   CREATE\_NEVER                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Write Disposition    Enumeration, one of:                                  Action that should occur if the destination table already exists. WRITE\_APPEND :- Configures the job to append data to the table if it already exists. WRITE\_EMPTY :- Configures the job to fail with a duplicate error if the table already exists. WRITE\_TRUNCATE :- Configures the job to overwrite the table data if table already exists. [Write Disposition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.WriteDisposition.html)                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                       -   WRITE\_TRUNCATE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                       -   WRITE\_APPEND                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                       -   WRITE\_EMPTY                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Kms Key Name         String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Extract Job {#ExtractJob}

  Field              Type                                         Description                                                                                          Default Value   Required
  ------------------ -------------------------------------------- ---------------------------------------------------------------------------------------------------- --------------- ----------
  Destination Uris   Array of String                              The list of fully-qualified Google Cloud Storage URIs where the extracted table should be written.                   x
  Source Table       [Table Configuration](#TableConfiguration)   The table to export.                                                                                                 x
  Compression        String                                       the compression value of exported files.                                                                             
  Field Delimiter    String                                       The delimiter used between fields in the exported data.                                                              
  Format             String                                       The exported files format.                                                                                           
  Print Header       Boolean                                      Whether an header row is printed with the result.                                                    false           

### Load Job {#LoadJob}

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                      Type                                         Description                                                                                                                                                                                             Default Value   Required
  -------------------------- -------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Source Uris                Array of String                              Fully-qualified URIs that point to source data in Google Cloud Storage                                                                                                                                                  x

  Destination Table          [Table Configuration](#TableConfiguration)   Destination table to load the data into                                                                                                                                                                                 x

  Autodetect                 Boolean                                      Automatic inference of the options and schema for CSV and JSON sources                                                                                                                                  true            

  Format Option              Enumeration, one of:                         Source format and parsing options of the external data                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                  
                             -   AVRO                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                  
                             -   CSV                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                  
                             -   DATASTORE\_BACKUP                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                  
                             -   GOOGLE\_SHEETS                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                  
                             -   JSON                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                  
                             -   ORC                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                  
                             -   PARQUET                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                  

  Ignore Unknown Values      Boolean                                      BigQuery should allow extra values that are not represented in the table schema                                                                                                                         false           

  Max Bad Records            Number                                       Maximum number of bad records that BigQuery can ignore when running the job                                                                                                                                             

  Null Marker                String                                       String that represents a null value in a CSV file                                                                                                                                                                       

  Destination Table Schema   [Table Schema](#TableSchema)                 Schema for the destination table                                                                                                                                                                                        

  Create Disposition         Enumeration, one of:                         Whether the job is allowed to create new tables [Create Disposition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.CreateDisposition.html)                                  
                                                                                                                                                                                                                                                                                                  
                             -   CREATE\_IF\_NEEDED                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                  
                             -   CREATE\_NEVER                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                  

  Kms Key Name               String                                       Creates a EncryptionConfiguration object for KMS key name                                                                                                                                                               

  Write Disposition          Enumeration, one of:                         Action that should occur if the destination table already exists [Write Disposition](https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.WriteDisposition.html)                   
                                                                                                                                                                                                                                                                                                  
                             -   WRITE\_TRUNCATE                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                  
                             -   WRITE\_APPEND                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                  
                             -   WRITE\_EMPTY                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                  

  Allow Fixed Relaxtion      Boolean                                      Allow relaxing a required field in the original schema to nullable when schema of the destination table to be updated as a side effect of the load job                                                  true            

  Allow Field Addition       Boolean                                      Allow adding a nullable field to the schema when schema of the destination table to be updated as a side effect of the load job                                                                         true            
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


