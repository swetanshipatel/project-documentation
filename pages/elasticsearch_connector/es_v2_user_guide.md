---
title: Elasticsearch Connector User Guide
toc: true
sidebar: elasticsearch_connector_sidebar
permalink: es_v2_user_guide.html
folder: elasticsearch_connector
---
Elasticsearch Connector
=========================

![Elasticsearch](./images/mulesoft/elasticsearch-connector/elasticsearch-logo.png)

Overview
--------

The Elasticsearch connector allows you to access the Elasticsearch REST
API through Anypoint Platform. Elasticsearch is a distributed, open
source search and analytics engine, designed for horizontal scalability,
reliability, and easy management. The connector exposes Elasticsearch
operations by executing their API calls as per configuration. It
supports HTTP, HTTP with basic authentication and HTTPS connections to
Elasticsearch instance. Read through this user guide to understand how
to set up and configure a basic flow using the connector.

Track features and API version updates using the [Elasticsearch connector
release notes](https://opendoc.gslab.com/es_release_notes.html). 
Review the connector operations and see how they work by
reviewing the technical reference alongside the demo applications.

Introduction
------------

This document assumes that user is familiar with Elasticsearch,
[Anypoint Connectors](https://docs.mulesoft.com/connectors/), and
[Anypoint Studio](https://www.mulesoft.com/platform/studio). To increase
your familiarity with Studio, consider completing a [Anypoint Studio
Tutorial](https://docs.mulesoft.com/studio/7.5/). This page
requires basic knowledge of [Mule Key
Concepts](https://docs.mulesoft.com/mule-runtime/4.2/) and
[Elasticsearch](https://www.elastic.co/).

Software Requirements {#requirements}
---------------------

For software requirements, visit the [Connector Release
Notes](https://opendoc.gslab.com/es_release_notes.html).

Installation
-------------

To install the connector in Anypoint Studio using the instructions
in [Installing a Connector from Anypoint
Exchange](https://docs.mulesoft.com/anypoint-studio/v/7.1/add-modules-in-studio-to).

Additionally, we recommend to keep Studio up to date with its latest
version.

### Connector Namespace and Schema {#ns-schema}

While designing Mule application in Anypoint Studio, when user drag the
connector from the palette onto the Anypoint Studio canvas, studio
automatically populates the XML code with the connector **namespace**
and **schema location**.

**Namespace:** `http://www.mulesoft.org/schema/mule/elasticsearch`

**Schema Location:** `http://www.mulesoft.org/schema/mule/elasticsearch/current/mule-elasticsearch.xsd`

> **Tip**
>
> If you are manually coding the Mule application in Studio’s XML editor
> or another text editor, define the namespace and schema location in
> the header of your **Configuration XML**, inside the `<mule>` tag.

    <mule xmlns:elasticsearch="http://www.mulesoft.org/schema/mule/elasticsearch"
            xmlns:http="http://www.mulesoft.org/schema/mule/http"
            xmlns="http://www.mulesoft.org/schema/mule/core"
            xmlns:doc="http://www.mulesoft.org/schema/mule/documentation"
            xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
            xsi:schemaLocation="http://www.mulesoft.org/schema/mule/core
            http://www.mulesoft.org/schema/mule/core/current/mule.xsd
    http://www.mulesoft.org/schema/mule/http http://www.mulesoft.org/schema/mule/http/current/mule-http.xsd
    http://www.mulesoft.org/schema/mule/elasticsearch http://www.mulesoft.org/schema/mule/elasticsearch/current/mule-elasticsearch.xsd
    </mule>

**Note:** Use `current` in the schema path. Studio interprets this to
the current Mule version.

### Maven Dependency Information {#maven}

After downloading and installing the connector, following steps make the
Elasticsearch connector available inside a Mule application for use
and to package the application with connector. If using Anypoint Studio,
it will do this automatically. For Maven dependency management, include
this XML snippet in pom.xml file of the Mule project.
					
	<dependency>
			<groupId>com.mulesoft.connectors</groupId>
			<artifactId>mule-elasticsearch-connector</artifactId>
			<version>2.0.0</version>
			<classifier>mule-plugin</classifier>
	</dependency>

Configuration
-------------

### Creating a New Project

To use the Elasticsearch connector in a Mule application project:

1.  In Anypoint Studio, click **File \> New \> Mule Project**
	![Create New Project](./images/mulesoft/elasticsearch-connector/create-new-project.png)
	<br>
	
2.  Enter project name and specify Runtime, API Implementation and
    Project Location if needed. ![Create new project dialogue
    box](./images/mulesoft/elasticsearch-connector/new-project-setting.png)

3.  Click **Finish** to create the project

### Configuring the Elasticsearch Global Element

Place the connector in the mule flow as per the use case. To use the
Elasticsearch connector in the Mule application, user must configure a global
Elasticsearch element that is used by the Elasticsearch connector to
authenticate.

![Elasticsearch-connector-config-1](./images/mulesoft/elasticsearch-connector/elasticsearch-connector-configuration-1.png)
<br>
The Elasticsearch connector provides the following global configuration(s).
![Elasticsearch-connector-config-2](./images/mulesoft/elasticsearch-connector/Elasticsearch-connector-configuration-2.png)

### Authentication

To access Elasticsearch, there are two following possible ways :

### 1. NO AUTHENTICATION (HTTP)

In NO AUTHENTICATION, you need to provide your Elasticsearch host and
port in a global configuration. NO AUTHENTICATION is generally
recommended for quick testing. For installation and starting
Elasticsearch, refer
[Installation](https://www.elastic.co/guide/en/elasticsearch/reference/current/setup.html).

Following parameters are required for **HTTP** configuration:

<table>
<col width="50%" />
<col width="50%" />
<tbody>
<tr class="odd">
<td align="left"><p>Field</p></td>
<td align="left"><p>Description</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Elasticsearch Host</strong></p></td>
<td align="left"><p>Host IP or host name of Elasticsearch</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Elasticsearch Port</strong></p></td>
<td align="left"><p>Port of Elasticsearch</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Username</strong></p></td>
<td align="left"><p>Username from user credentials</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Password</strong></p></td>
<td align="left"><p>Password from user credentials</p></td>
</tr>
</tbody>
</table>

![Elasticsearch-HTTP-config](./images/mulesoft/elasticsearch-connector/Elasticsearch-http-global-element-props.png)

> **Tip**
>
> Keep Elasticsearch instance username and password credentials blank
> for anonymous user.

> **Note**
>
> Default Elasticsearch port is 9200.

### 2. CERTIFICATE BASED AUTHENTICATION (HTTPS)

Implementing CERTIFICATE BASED AUTHENTICATION mechanism involves a few
extra steps, but ìs preferred if your Elasticsearch is exposed to
external users, as it ensures better security. To make the Elasticsearch
run on HTTPS, generate server and client certificates on Elasticsearch
host using X-pack. Please refer [Encrypting communications in
Elasticseach](https://www.elastic.co/guide/en/elasticsearch/reference/current/configuring-tls.html#node-certificates)
for detailed information about running Elasticsearch on HTTPS and
generating required certificates.

-   Following parameters are required for **HTTPS** configuration (Certificate Based
    Authentication):

<table>
<col width="50%" />
<col width="50%" />
<tbody>
<tr class="odd">
<td align="left"><p>Field</p></td>
<td align="left"><p>Description</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Elasticsearch Host</strong></p></td>
<td align="left"><p>Host IP or host name of Elasticsearch</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Elasticsearch Port</strong></p></td>
<td align="left"><p>Port of Elasticsearch</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Username</strong></p></td>
<td align="left"><p>Username from user credentials</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Password</strong></p></td>
<td align="left"><p>Password from user credentials</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Type</strong></p></td>
<td align="left"><p>Truststore certificate type e.g. <strong>JKS</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Path</strong></p></td>
<td align="left"><p>Path of Truststore</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Truststore Password</strong></p></td>
<td align="left"><p>Password for the Truststore</p></td>
</tr>
</tbody>
</table>

![Elasticsearch-HTTPS-config](./images/mulesoft/elasticsearch-connector/Elasticsearch-https-global-element-props.png)

> **Tip**
>
> Keep Elasticsearch instance username and password credentials blank
> for anonymous user.

> **Note**
>
> Access [X-Pack](https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-xpack.html)
> for detailed information about security and many other
> capabilities. By default, when you install Elasticsearch, X-Pack is
> also installed.

Understanding the Elasticsearch Connector
-----------------------------------------

The Elasticsearch connector functions within a Mule application. Using
the connector, mule application can perform several operations that
Elasticsearch exposes via their APIs. When building an application that
connects with Elasticsearch you don’t have to go through the effort of
custom-coding (and securing!) a connection. Rather, you can just drop a
connector into your flow, configure a few connection details, then begin
application running on Elasticsearch.

The real value of the Elasticsearch connector is in the way you use it
at design-time in conjunction with other functional features available
in Mule.

-   **DataSense** DataSense extracts metadata for Elasticsearch standard
    response to automatically determine the data type and format that
    your application must deliver to, or can expect from Elasticsearch.
    Mule does the heavy lifting of discovering the type of data you must
    send to, or be prepared to receive from Elasticsearch.

-   **Transform Message Component** This component’s integrated
    scripting language called DataWeave can automatically extract
    response metadata that you can use to visually map and/or transform
    to a different data format or structure. Essentially, DataWeave
    let’s you control the mapping between data types. For example, if
    you configure a Elasticsearch connector in your application, then
    drop a Transform Message component after the connector, the
    component uses DataWeave to gather information that DataSense
    extracted to pre-populate the input values for mapping. In other
    words, DataSense makes sure that DataWeave knows the data format and
    it's structure so that you don’t have to figure it out manually. Mule
    developer can refer to [Elasticsearch Connector API
    docs](https://opendoc.gslab.com/es_v2_api_reference.html)
    for more information about complex input or return types.

Common Use Cases
----------------

-   [Elasticsearch as Document store](#use-case-1)

-   [Search for the phrases from particular dataset](#use-case-2)

-	[Different Elasticsearch operations that can be performed on Documents and Indices](#use-case-3)

### Elasticsearch as a Document Store {#use-case-1}

-	This use case demonstrates uploading bulk of data to Elasticsearch 
	using **Document - Bulk** operation. Once data is uploaded, it uses **Document - Get**
	operation to retrieve one of the document from the uploaded dataset. 
	
-	This usecase uses readily available dataset 'shakespeare_6.0.json' present in the resource folder of demo application.
	
Elasticsearch stores JSON documents. This is an example of a sample document :
    
	{
		"type":"line",
		"line_id":6672,
		"play_name":"Henry VI Part 2",
		"speech_number":22,
		"line_number":"1.3.91",
		"speaker":"SUFFOLK",
		"text_entry":"For I am bold to counsel you in this."
	}


-   In Anypoint Studio, click **File \> New \> Mule Project**, name
    the project, and click **OK**

-   In the search field, type **Http** and drag the **HTTP Listener** to
    the canvas.

-   Click the **HTTP Listener**, click the **green plus** sign to the
    right of Connector Configuration. On the next screen, add the host
    and port, click **OK**.

-   Provide **Path** to HTTP Listener (Example: /documentstore)

-   On the Mule Palette, search for **Document - Bulk** and drag it 
	onto the canvas.

-   Select the **Document - Bulk** operation and create a new connector configuration. 
	Select connection as **HTTP connection** and add host and port of Elasticsearch.

-   Configure the **Document - Bulk**, provide appropriate **index** and browse **the input data file**.
	(Example: shakespeare_6.0.json)

-   Drag the **Logger** onto the canvas and log **payload** as
    expression to log the output of the operation.

-   In the Mule Palette, search for **Document - Get** and drag it 
	onto the canvas.

-   Configure the **Document - Get** operation. Provide **index** and 
	**document id** along with other optional parameters.

-   Drag the **Logger** onto the canvas and log **payload** as
    expression to log the output of the operation.
	
-	After you create the flow, right-click the project and click **Run
    As \> Mule Applciation**

-   Once application is deployed, use **HTTP Listener’s Path** to
    execute the Mule Flow.

![Documentstore-flow](./images/mulesoft/elasticsearch-connector/usecase-1.png)

**Example Use Case Code :**

Paste this XML code into Anypoint Studio to experiment with the flow
described above.

    <?xml version="1.0" encoding="UTF-8"?>

	<mule xmlns:elasticsearch="http://www.mulesoft.org/schema/mule/elasticsearch" xmlns:http="http://www.mulesoft.org/schema/mule/http"
		xmlns="http://www.mulesoft.org/schema/mule/core"
		xmlns:doc="http://www.mulesoft.org/schema/mule/documentation" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.mulesoft.org/schema/mule/core http://www.mulesoft.org/schema/mule/core/current/mule.xsd
	http://www.mulesoft.org/schema/mule/http http://www.mulesoft.org/schema/mule/http/current/mule-http.xsd
	http://www.mulesoft.org/schema/mule/elasticsearch http://www.mulesoft.org/schema/mule/elasticsearch/current/mule-elasticsearch.xsd">
		<http:listener-config name="HTTP_Listener_config" doc:name="HTTP Listener config" doc:id="8392248e-98e1-42da-bd19-1faee78c422c" >
			<http:listener-connection host="0.0.0.0" port="8081" />
		</http:listener-config>
		<elasticsearch:config name="Elasticsearch_Config" doc:name="Elasticsearch Config" doc:id="88f2eedb-53cc-498a-985d-1c9eb8be2042" >
			<elasticsearch:http-connection host="${elastic.host}" />
		</elasticsearch:config>
		
		<configuration-properties doc:name="Configuration properties" doc:id="96e66225-99ad-4221-a68c-4c596fb50c57" file="mule-application.properties" />
		<flow name="DocumentStore" doc:id="6f18edae-31ae-44f8-819a-9cf062a92acc" >
			<http:listener doc:name="Listener" doc:id="7226082d-691d-46ed-b9cf-39a19f0ecf9b" config-ref="HTTP_Listener_config" path="/documentstore"/>
			<elasticsearch:bulk-operation doc:name="Dataset Upload" doc:id="2c8400f3-7cb0-4a66-b24d-24c0a6fcdbe2" index="${bulk.index}" jsonfile="${bulk.dataset}" config-ref="Elasticsearch_Config"/>
			<logger level="INFO" doc:name="Log dataset insert response" doc:id="8ff5a4ae-10d0-4c07-94f0-e7e976b4b83e" message="Inserted Dataset #[payload]"/>
			<elasticsearch:get-document doc:name="Get document" doc:id="d3ec0cd4-f1d9-44de-90cf-f4a78cfbdb1f" config-ref="Elasticsearch_Config" index="${get.index}" documentId="${get.id}"/>
			<logger level="INFO" doc:name="Log the get document details" doc:id="6c9112f9-4216-445a-bdb5-b64f6e6a469e" message="Document Generated #[payload]"/>
		</flow>
	</mule>


### Search for the phrases from particular dataset {#use-case-2}

-	This usecase demonstrates different search queries like **match-query**,
    **multi-match-query**, **match-phrase-query** and **match-all-query** 
	of search operation available in Elasticsearch connector for searching.
	
-	The HTTP listener of this use case, expect a query parameter named **querytype** with
	one of the query type (Ex: match-query, multi-match-query, match-phrase-query or match-all-query)
	to perform search operation based on passed query type.

> **Note**
>
> If data is not available on Elasticsearch, please refer the use case: 
> ***Elasticsearch as a Document Store*** to insert the data in Elasticsearch 
> using bulk operation.

-   In Anypoint Studio, click **File \> New \> Mule Project**, name
	the project, and click **OK**
	
-   In the search field, type **Http** and drag the **HTTP Listener** to
    the canvas.

-   Click the **HTTP Listener**, click the **green plus** sign to the
    right of Connector Configuration. On the next screen, add the host
    and port, click **OK**.

-   Provide **Path** to HTTP Listener (Example: /searchOperation)

-   In the search field, type **Set Variable** and drag it to the canvas. 
	Configure name of the variable as 'searchQuery' and value **attributes.queryParams.querytype** as
    expression.
	
-   Drag the **Logger** onto the canvas and log 'vars.searchQuery' as
    expression to log the value of the variable.
	
-   Use the **Choice** connector to switch between different query types (Ex: match-query, 
	multi-match-query, match-phrase-query or match-all-query) depending on the value of 'vars.searchQuery'.

-   Drag the **Choice** onto the canvas and add three **When** clauses and one default/otherwise clause to it.

-	In first when clause, add expression as **#[vars.searchQuery=='multi-match-query']**.

-	In the Palette, search for **Search - Query** operation and drag it into first **when** clause.

-	Select the **Search - Query** operation and create a new connector configuration. 
	Select connection as **HTTP connection** and add host and port of Elasticsearch.
	
-	Configure 'Search - Query' operation with query type as 'Multi match query' and configuration 
	other parameters as required. Refer the sample XML provided below to set the values.

-   Drag the **Logger** onto the canvas and log 'payload' as
    expression to log the output of 'Multi match query' search operation.

-	In second when clause, add expression as **#[vars.searchQuery=='match-query']**.

-	Drag **Search - Query** operation into second **when** clause and provide the connector configuration. 
	
-	Configure 'Search - Query' operation with query type as 'Match query' and configuration 
	other parameters as required. Refer the sample XML provided below to set the values.

-   Drag the **Logger** onto the canvas and log 'payload' as expression to log the output of 'Match query' search operation.

-	In third when clause, add expression as **#[vars.searchQuery=='match-phrase-query']**.

-	Drag **Search - Query** operation into third **when** clause and provide the connector configuration. 
	
-	Configure 'Search - Query' operation with query type as 'Match phrase query' and configuration 
	other parameters as required. Refer the sample XML provided below to set the values.

-   Drag the **Logger** onto the canvas and log 'payload' as expression to log the output of 'Match phrase query' search operation.

-	In default/otherwise clause, there is no expression and it will execute in all the other cases.

-	Finally drag **Search - Query** operation into default/otherwise clause and provide the connector configuration. 
	
-	Configure 'Search - Query' operation with query type as 'Match all query' and configuration 
	other parameters as required. Refer the sample XML provided below to set the values.

-   Drag the **Logger** onto the canvas and log 'payload' as expression to log the output of 'match all query' search operation.

-	After you create the flow, right-click the project and click **Run
    As \> Mule Applciation**

-   Once application is deployed, use **HTTP Listener’s Path** to
    execute the Mule Flow.

![search-flow](./images/mulesoft/elasticsearch-connector/usecase-2.png)

**Example Use Case Code :**

Paste this XML code into Anypoint Studio to experiment with the flow
described in the previous section.

    <?xml version="1.0" encoding="UTF-8"?>

	<mule xmlns:elasticsearch="http://www.mulesoft.org/schema/mule/elasticsearch" xmlns:http="http://www.mulesoft.org/schema/mule/http"
		xmlns="http://www.mulesoft.org/schema/mule/core"
		xmlns:doc="http://www.mulesoft.org/schema/mule/documentation" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.mulesoft.org/schema/mule/core http://www.mulesoft.org/schema/mule/core/current/mule.xsd
	http://www.mulesoft.org/schema/mule/http http://www.mulesoft.org/schema/mule/http/current/mule-http.xsd
	http://www.mulesoft.org/schema/mule/elasticsearch http://www.mulesoft.org/schema/mule/elasticsearch/current/mule-elasticsearch.xsd">
		<http:listener-config name="HTTP_Listener_config" doc:name="HTTP Listener config" doc:id="9f66c6d5-fe9b-438c-929b-da29282872c8" >
			<http:listener-connection host="0.0.0.0" port="8081" />
		</http:listener-config>
		<elasticsearch:config name="Elasticsearch_Config" doc:name="Elasticsearch Config" doc:id="e7e261e5-1ce9-498a-ad82-7e62fd8f11eb" >
			<elasticsearch:http-connection host="${elastic.host}" />
		</elasticsearch:config>
		
		<configuration-properties doc:name="Configuration properties" doc:id="38d3c87e-921d-45a0-ac72-da61463ccbc7" file="mule-application.properties" />
		<flow name="SearchPhrase" doc:id="1cdc935c-3ef6-469a-94e7-22fa49e84edb">
			<http:listener doc:name="Listener"
				doc:id="13285cd4-bb7f-40ba-93b8-e113ba3cce1c" config-ref="HTTP_Listener_config"
				path="/searchOperation" >
			</http:listener>
			<set-variable value="#[attributes.queryParams.querytype]" doc:name="Set Variable"
				doc:id="a33aaf60-23e7-4c8e-8738-9796feaf8937" variableName="searchQuery" />
			<logger level="INFO" doc:name="Logger"
				doc:id="96bafaeb-1fcb-4971-b06f-d06187ca240c" message="Set variable value #[vars.searchQuery]" />
			<choice doc:name="Choice" doc:id="d1355aea-0240-4a79-aca3-db228412e8c4">
				<when expression="#[vars.searchQuery=='multi-match-query']">
					<elasticsearch:search doc:name="Multi Match"
						doc:id="d45b3b45-f5e8-4509-bac9-e7554f1f1d91" config-ref="Elasticsearch_Config"
						searchType="DFS_QUERY_THEN_FETCH">
						<elasticsearch:query-configuration>
							<elasticsearch:query-type >
								<elasticsearch:multi-match-query
									minimumShouldMatch="10%" searchString="${searchMultiMatch.searchString}"
									operator="OR" autoGenerateSynonymsPhraseQuery="true" type="BEST_FIELDS"
									tieBreaker="1.0" zeroTermsQuery="ALL">
									<elasticsearch:fields>
										<elasticsearch:field value="${searchMultiMatch.fieldA}" />
										<elasticsearch:field value="${searchMultiMatch.fieldB}" />
										<elasticsearch:field value="${searchMultiMatch.fieldC}" />
									</elasticsearch:fields>
								</elasticsearch:multi-match-query>
							</elasticsearch:query-type>
						</elasticsearch:query-configuration>
						<elasticsearch:search-source-configuration
							size="${searchSource.size}" timeout="${searchSource.timeout}" sortOrder="ASC" from="${searchSource.from}">
							<elasticsearch:include-fields>
								<elasticsearch:include-field value="${searchMultiMatch.includeField}" />
							</elasticsearch:include-fields>
						</elasticsearch:search-source-configuration>
						<elasticsearch:indices>
							<elasticsearch:index value="${search.index}" />
						</elasticsearch:indices>
					</elasticsearch:search>
					<logger level="INFO" doc:name="Logger"
						doc:id="3d69a761-c71e-4948-b98d-2490af08ebb3" message="#[payload]" />

				</when>
				<when expression="#[vars.searchQuery=='match-query']">
					<elasticsearch:search doc:name="Match Query"
						doc:id="f072cb50-cd00-44b5-b6b3-f7a8cd28e969" config-ref="Elasticsearch_Config"
						searchType="DFS_QUERY_THEN_FETCH">
						<elasticsearch:query-configuration>
							<elasticsearch:query-type >
								<elasticsearch:match-query field="${searchMatchQuery.field}"
									searchString="${searchMatchQuery.searchString}" zeroTermsQuery="ALL"
									autoGenerateSynonymsPhraseQuery="true" />
							</elasticsearch:query-type>
						</elasticsearch:query-configuration>
						<elasticsearch:search-source-configuration
							size="${searchSource.size}" timeout="${searchSource.timeout}" from="${searchSource.from}">
							<elasticsearch:include-fields>
								<elasticsearch:include-field value="${searchMatchQuery.fieldA}" />
							</elasticsearch:include-fields>
							<elasticsearch:exclude-fields>
								<elasticsearch:exclude-field value="${searchMatchQuery.excludeFieldA}" />
								<elasticsearch:exclude-field value="${searchMatchQuery.excludeFieldB}" />
								<elasticsearch:exclude-field value="${searchMatchQuery.excludeFieldC}" />
								<elasticsearch:exclude-field value="${searchMatchQuery.excludeFieldD}" />
							</elasticsearch:exclude-fields>
						</elasticsearch:search-source-configuration>
						<elasticsearch:indices>
							<elasticsearch:index value="${search.index}" />
						</elasticsearch:indices>
					</elasticsearch:search>
					<logger level="INFO" doc:name="Logger"
						doc:id="b4522649-745c-4a32-b6c2-1efd94f03021" message="#[payload]" />
				</when>
				<when expression="#[vars.searchQuery=='match-phrase-query']">
					<elasticsearch:search doc:name="Match Phrase"
						doc:id="ddf3528b-59f0-40df-a763-b2e2d92eca22" config-ref="Elasticsearch_Config"
						searchType="DFS_QUERY_THEN_FETCH">
						<elasticsearch:query-configuration>
							<elasticsearch:query-type >
								<elasticsearch:match-phrase-query
									field="${searchMatchPhrase.field}" queryString="${searchMatchPhrase.queryString}" />
							</elasticsearch:query-type>
						</elasticsearch:query-configuration>
						<elasticsearch:search-source-configuration
							size="${searchSource.size}" timeout="${searchSource.timeout}" sortOrder="ASC" sortByFieldName="${searchMatchPhrase.sortBy}" from="${searchSource.from}">
							<elasticsearch:include-fields>
								<elasticsearch:include-field value="${searchMatchPhrase.fieldA}" />
							</elasticsearch:include-fields>
						</elasticsearch:search-source-configuration>
						<elasticsearch:indices>
							<elasticsearch:index value="${search.index}" />
						</elasticsearch:indices>
					</elasticsearch:search>
					<logger level="INFO" doc:name="Logger"
						doc:id="e58a0d5e-2bba-4fe4-8cdf-3f134013d0a9" message="#[payload]" />
				</when>
				<otherwise>
					<elasticsearch:search doc:name="Match All Query"
						doc:id="de99202c-3df7-4b17-b882-f29cf47e6d91" config-ref="Elasticsearch_Config"
						searchType="QUERY_THEN_FETCH">
						<elasticsearch:query-configuration>
							<elasticsearch:query-type >
								<elasticsearch:match-all-query />
							</elasticsearch:query-type>
						</elasticsearch:query-configuration>
						<elasticsearch:search-source-configuration
							size="${searchSource.size}" timeout="${searchSource.timeout}" from="${searchSource.from}">
							<elasticsearch:include-fields>
								<elasticsearch:include-field value="${searchMatchAll.fieldB}" />
								<elasticsearch:include-field value="${searchMatchAll.fieldA}" />
							</elasticsearch:include-fields>
						</elasticsearch:search-source-configuration>
						<elasticsearch:indices>
							<elasticsearch:index value="${search.index}" />
						</elasticsearch:indices>
					</elasticsearch:search>
					<logger level="INFO" doc:name="Logger"
						doc:id="70571ee6-9112-4e32-b45b-45bf5b90c2ca" message="#[payload]" />
				</otherwise>
			</choice>
		</flow>
	</mule>


###	Different Elasticsearch operations that can be performed on Documents and Indices {#use-case-3}

-	This usecase demonstrates the use of different document and index operations of Elasticsearch connector as mentioned below and if successful returns the ***true*** message.

    1.  Create Index

    2.  Index Document

    3.  Get Document

    4.  Update Document

    5.  Delete Document

    6.  Delete Index

-   In Anypoint Studio, click **File \> New \> Mule Project**, name the
    project, and click **OK**
	
-	In the search field, type **Http** and drag the **HTTP Listener** to
    the canvas.

-   Click the **HTTP Listener**, click the **green plus** sign to the
    right of Connector Configuration. On the next screen, add the host
    and port, click **OK**.

-   Provide **Path** to HTTP Listener (Example: /documentIndicesOperations)

-	Drag **Flow Reference** on the canvas and provide flow name of the new sub flow 'create-index-and-insert-document'. 
	This sub flow will create an index and add a document to it.

	1. Now in the search field, type **Sub Flow** and drag it to the canvas. Create 
	a new sub flow 'create-index-and-insert-document'.
	
	2. In the Mule Palette, search for **Index- Create** operation and drag it into the
	newly created sub flow 'create-index-and-insert-document'.

	3. Select the 'Index- Create' operation and create a new connector configuration. 
	Select connection as **HTTP connection** and add host and port of Elasticsearch.
	
	4. Configure 'Index - Create' operation with index and other optional parameters.
	
	5. Drag the **Logger** onto the canvas and log **payload** as
    expression to log the output of the operation.
	
	6. Drag **Document - Index** operation onto the canvas. Provide index (created above) and document id.
	
	7. Also provide either 'JSON input file path' or 'Document source'. In the sample XML 
	provided below, 'JSON input file path' is set to **indexDocument.json** (copied in 
	src/main/resource folder of demo application)

	8. Drag the **Logger** onto the canvas and log **payload** as
    expression to log the output of the operation.
	
-	Again drag a **Flow Reference** in the main flow and provide flow name of the new sub flow 'update-document'.
	This sub flow will get a document from an index and will update that document.

	1. Drag a **Sub Flow** into the canvas and create a new sub flow named 'update-document'.
	
	2. In the Mule Palette, search for **Document- Get** operation and drag it into 
	newly created sub flow 'update-document'.

	3. Configure 'Document - Get' operation with **index** and **document id** (created in above steps).
		
	5. Drag the **Logger** onto the canvas and log **payload** as expression to log the output of the operation.
	
	6. Drag **Document - Update** operation onto the canvas to update the document created in 'create-index-and-insert-document' sub flow.

	7. Configure 'Document - Update' operation with **index** and **document id** of the document which you want to update.
	
	8. Provide either 'JSON input file path' or 'Document source' with other optional arguments.
	In the sample XML provided below, 'JSON input file path' is set to **UpdateIndexDocument.json** (copied in 
	src/main/resource folder of demo application)

	9. Drag the **Logger** onto the canvas and log **payload** as
    expression to log the output of the operation.
	
-	Drag one more **Flow Reference** in the main flow and provide flow name of the new sub flow 'delete-resources'.
	This sub flow will do clean up by deleting the index and the document created above.

	1. Now drag a **Sub Flow** into the canvas and create a new sub flow named 'delete-resources'.
	
	2. In the Mule Palette, search for **Document- Delete** operation and drag it into 
	newly created sub flow 'delete-resources'.

	3. Configure 'Document- Delete' operation with index, document id and other optional parameters.
		
	4. Drag the **Logger** onto the canvas and log **payload** as expression to log the output of the operation.
	
	5. Drag **Index - Delete** operation onto the canvas.

	6. Configure 'Index - Delete' operation with index and other optional parameters.
	
	7. Drag the **Logger** onto the canvas and log **payload** as expression to log the output of the operation.

-	Finally drag a **Logger** onto the canvas in the main flow and log **payload.acknowledged** as
    expression.

-	After you create the flow, right-click the project and click **Run
    As \> Mule Applciation**

-   Once application is deployed, use **HTTP Listener’s Path** to
    execute the Mule Flow.
    
![Usecase3-main-flow](./images/mulesoft/elasticsearch-connector/usecase-3-main-flow.png)
![Usecase3-sub-flow](./images/mulesoft/elasticsearch-connector/usecase-3-sub-flows.png)

**Example Use Case Code :**

Paste this XML code into Anypoint Studio to experiment with the flow
described above.

    <?xml version="1.0" encoding="UTF-8"?>

	<mule xmlns:elasticsearch="http://www.mulesoft.org/schema/mule/elasticsearch"
		xmlns:http="http://www.mulesoft.org/schema/mule/http"
		xmlns:ee="http://www.mulesoft.org/schema/mule/ee/core" xmlns="http://www.mulesoft.org/schema/mule/core"
		xmlns:doc="http://www.mulesoft.org/schema/mule/documentation"
		xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="
	http://www.mulesoft.org/schema/mule/http http://www.mulesoft.org/schema/mule/http/current/mule-http.xsd 
	http://www.mulesoft.org/schema/mule/ee/core http://www.mulesoft.org/schema/mule/ee/core/current/mule-ee.xsd http://www.mulesoft.org/schema/mule/core http://www.mulesoft.org/schema/mule/core/current/mule.xsd
	http://www.mulesoft.org/schema/mule/elasticsearch http://www.mulesoft.org/schema/mule/elasticsearch/current/mule-elasticsearch.xsd">
		
		<http:listener-config name="HTTP_Listener_config" doc:name="HTTP Listener config" doc:id="85a8f372-7f62-4473-ba31-5912cc3625bf" >
			<http:listener-connection host="0.0.0.0" port="8081" />
		</http:listener-config>

		<elasticsearch:config name="Elasticsearch_Config" doc:name="Elasticsearch Config" doc:id="78723584-fcbc-465d-9e82-96acb083e67f" >
			<elasticsearch:http-connection host="${elastic.host}" />
		</elasticsearch:config>

		<configuration-properties doc:name="Configuration properties" doc:id="9ea50978-2158-4586-979a-00b81adc6a67" file="mule-application.properties" />
		
		<flow name="document-index-operations-main-flow" doc:id="d760bb0d-45c8-4240-89b5-84b113c391c0">
			<http:listener doc:name="Listener"
				doc:id="abfb108b-af2d-4324-89d8-eb8f53793b55" config-ref="HTTP_Listener_config"
				path="/documentIndicesOperations" />
			<flow-ref doc:name="create-index-insert-document" doc:id="71cd0fb3-554a-44d9-bef7-6c6376fe13ef" name="create-index-and-insert-document" />
			<flow-ref doc:name="update-document" doc:id="985838ae-f840-4ce3-b043-ffd70971e71a" name="update-document" />
			<flow-ref doc:name="delete-resources" doc:id="6d13e110-b88b-4945-9ad9-0d9034a98408" name="delete-resources" />
			<logger level="INFO" doc:name="Logger"
				doc:id="4f400a6e-32b8-4822-900e-a0297050b3d9" message="Response: #[payload.acknowledged]" />
		</flow>
		
		<sub-flow name="create-index-and-insert-document" doc:id="54454fbf-1175-457a-a0ce-e851288ec831" >
			<elasticsearch:create-index doc:name="Index - Create" doc:id="acd7020b-b3b4-4ebf-b1d7-ac5a87e6edc9" config-ref="Elasticsearch_Config" index="${index}" />
			<logger level="INFO" doc:name="Logger" doc:id="4891c5b3-f76a-4005-8969-ff7b3e1b857c" message="Create Index Response  #[payload]" />
			<elasticsearch:index-document doc:name="Document - Index" doc:id="a29e392d-b1d7-4b86-aa6e-e82ac5fbbb70" config-ref="Elasticsearch_Config" index="${index}" documentId="${document.id}" jsonInputPath="${document.path}">
			</elasticsearch:index-document>
			<logger level="INFO" doc:name="Logger"
				doc:id="cb651e84-6fa6-4b13-b0f4-8b2b76daaeb8" message="Index Document Response: #[payload]" />
		</sub-flow>
		
		<sub-flow name="update-document" doc:id="0dc6f8ad-ff88-45a7-b994-d63f317ad78c">
			<elasticsearch:get-document doc:name="Document - Get" doc:id="b86cf9cd-4f2c-4396-8511-88112b253dcd" config-ref="Elasticsearch_Config" documentId="${document.id}" index="${index}" />
			<logger level="INFO" doc:name="Logger" doc:id="5116d872-57fa-42b6-aab9-3682927c51d6" message="Get Document Reponse: #[payload]" />
			<elasticsearch:update-document doc:name="Document - Update" doc:id="fff2fe88-b7fa-4eb5-baa0-a66b5e734567" config-ref="Elasticsearch_Config" index="#[payload.index]" documentId="#[payload.id]" jsonInputPath="${document.updatepath}" />
			<logger level="INFO" doc:name="Logger" doc:id="86ff892d-869a-43c0-b6b5-d2df02b807f4" message="Update document response: #[payload]" />
		</sub-flow>
		
		<sub-flow name="delete-resources" doc:id="fc3a6a9a-4631-48b7-8c7c-399ac5f54951">
			<elasticsearch:delete-document doc:name="Document - Delete" doc:id="93b942f1-7e95-40b0-a089-9328eeb00723" config-ref="Elasticsearch_Config" index="${index}" documentId="${document.id}" />
			<logger level="INFO" doc:name="Logger" doc:id="78ac511f-397d-41a2-945c-2cc3691d140b" message="Delete Document Response: #[payload]" />
			<elasticsearch:delete-index doc:name="Index - Delete" doc:id="ca5bcd5c-7ce3-4742-a642-2c3617393400" config-ref="Elasticsearch_Config" index="${index}" />
			<logger level="INFO" doc:name="Logger" doc:id="f3ce7936-5189-4c66-925d-96ab4bae974f" message="Delete Index Response: #[payload] " />
		</sub-flow>
	</mule>

Resources
=========

-   [Elasticsearch Connector Release Notes](https://opendoc.gslab.com/es_release_notes.html).

-   [Elasticsearch Connector API docs - Version 2](https://opendoc.gslab.com/es_v2_api_reference.html).

{% include links.html %}