---
title: Google BigQuery Connector Upgrade Document
keywords: sample
sidebar: bigquery_connector_sidebar
permalink: bq_1.0.0_to_2.0.0_upgrade.html
folder: bigquery_connector
---
Google BigQuery Connector Upgrade Document (v1.0.0 to v2.0.0)
================================

The Google BigQuery connector support following operations of Google BigQuery service:

    -   Create Dataset
	
	-   Get Dataset
	
	-   Update Dataset
	
	-   List Dataset
	
	-   Delete Dataset
	
	-   Create Table
	
	-   Get Table
	
	-   Update Table
	
	-   List Table
	
	-   Delete Table
	
	-   Insert All
	
	-   List Table Data
	
    -   Create Job (Copy Job, Extract Job, Load Job, Query Job)
	
    -   Get Job
	
	-   List Job
	
    -   Get Query Result
	
	-   Query
	
	-   Cancel Job

Google BigQuery connector v2.0.0 has changed and simplified the output of the above operations as compared to v1.0.0.
This document provides the detail of the operations with the change in its output/payload.

### Upgrade (Version 1.0.0 to Version 2.0.0)
The following table provides information about the affected content of the output for different operations.

Note- Information provided in the tables is applicable when output type is application/java as below -
<!-- -->

    %dw 2.0
    output application/java
    ---


#### Affected output in 'Create Dataset, Get Dataset, Update Dataset and List Dataset'

<table border="1">
<tr><th>In v1.0.0</th><th>In v2.0.0</th></tr>
<tr><td>payload.acl[0].role.constant</td><td>payload.acl[0].role</td></tr>
</table>

#### Affected output in 'Create Table, Get Table, Update Table and List Table'

<table border="1">
<tr><th>In v1.0.0</th><th>In v2.0.0</th></tr>
<tr><td>payload.tableDefinition."type".constant</td><td>payload.tableDefinition."type"</td></tr>
<tr><td>payload.tableDefinition.schema.fields[0]."type".constant</td><td>payload.tableDefinition.schema.fields[0]."type"</td></tr>
</table>


#### Affected output in 'Create Job, Get Job and List Job'

<table border="1">
<tr><th>In v1.0.0</th><th>In v2.0.0</th><th>Remark</th></tr>
<tr><td>payload.status.state.constant</td><td>payload.status.state</td><td></td></tr>
<tr><td>payload.configuration.tableDefinitions.{EXTERNAL_TABLE_NAME}."type".constant</td><td>payload.configuration.tableDefinitions.{EXTERNAL_TABLE_NAME}."type"</td><td>Applicable only for Query Job.</td></tr>
<tr><td>payload.configuration.tableDefinitions.{EXTERNAL_TABLE_NAME}.schema.fields[0]."type".constant</td><td>payload.configuration.tableDefinitions.{EXTERNAL_TABLE_NAME}.schema.fields[0]."type"</td><td>Applicable only for Query Job.</td></tr>
<tr><td>payload.statistics.schema.fields[0]."type".constant</td><td>payload.statistics.schema.fields[0]."type"</td><td>Applicable only for Query Job.</td></tr>
<tr><td>payload.configuration.clustering.fields</td><td>payload.configuration.clustering</td><td>Applicable for Query Job and Load Job.</td></tr>
<tr><td>payload.configuration.schema.fields[0]."type".constant</td><td>payload.configuration.schema.fields[0]."type"</td><td>Applicable only for Load Job.</td></tr>
</table>


#### Affected output in 'List Table Data, Query Job and Get Query Result'

<table border="1">
<tr><th>In v1.0.0</th><th>In v2.0.0</th></tr>
<tr><td>ayload.schema.fields[0]."type".constant</td><td>payload.schema.fields[0]."type"</td></tr>
</table>

### Resources

-   [BiqQuery Connector User Guide - Version 2.0.0](bq_v2_user_guide.html).

-   [BiqQuery Connector API docs - Version 2.0.0](bq_v2_api_reference.html).

{% include links.html %}


