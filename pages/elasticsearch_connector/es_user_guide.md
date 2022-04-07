---
title: Elasticsearch Connector User Guide
toc: true
sidebar: elasticsearch_connector_sidebar
permalink: es_user_guide.html
folder: elasticsearch_connector
---
Overview
========

The Elasticsearch connector allows you to access the Elasticsearch REST
API through Anypoint Platform. Elasticsearch is a distributed, open
source search and analytics engine, designed for horizontal scalability,
reliability, and easy management. The connector exposes Elasticsearch
operations by executing their API calls as per configuration. It
supports HTTP, HTTP with basic authentication and HTTPS connections to
Elasticsearch instance. Read through this user guide to understand how
to set up and configure a basic flow using the connector.

Track features and API version updates using the Elasticsearch connector
release notes. Review the connector operations and see how they work by
reviewing the technical reference alongside the demo applications.

Important Concepts
==================

This document assumes that you are familiar with Elasticsearch,
[Anypoint Connectors](https://docs.mulesoft.com/connectors/), and
[Anypoint Studio](https://www.mulesoft.com/platform/studio). To increase
your familiarity with Studio, consider completing a [Anypoint Studio
Tutorial](https://docs.mulesoft.com/anypoint-studio/v/7.1/). This page
requires basic knowledge of [Mule Key
Concepts](https://docs.mulesoft.com/mule4-user-guide/v/4.1/) and
[Elasticsearch](https://www.elastic.co/).

Software Requirements
=====================

For software requirements, visit the [Connector Release
Notes](es_release_notes.html).

How to Install
==============

You can install the connector in Anypoint Studio using the instructions
in [Installing a Connector from Anypoint
Exchange](https://docs.mulesoft.com/anypoint-studio/v/7.1/add-modules-in-studio-to).

Additionally, we recommend you to keep Studio up to date with its latest
version.

Connector Namespace and Schema
==============================

While designing your application in Anypoint Studio, when you drag the
connector from the palette onto the Anypoint Studio canvas, studio
automatically populates the XML code with the connector **namespace**
and **schema location**.

**Namespace:**
`+http://www.mulesoft.org/schema/mule/elasticsearch+`**Schema
Location:**
`+http://www.mulesoft.org/schema/mule/elasticsearch/current/mule-elasticsearch.xsd+`

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

Maven Dependency Information
============================

After you download and install the connector, use the following steps to
make the Elasticsearch connector available inside a Mule application for
use and to package the application with connector. If you use Anypoint
Studio, it will do this automatically for you.For Maven dependency
management, include this XML snippet in your `pom.xml` file.

                    <dependency>
                            <groupId>org.mule.extension.elasticsearch</groupId>
                            <artifactId>elasticsearch-connector</artifactId>
                            <version>1.0.0</version>
                            <classifier>mule-plugin</classifier>
                    </dependency>

How to Configure
================

Creating a New Project
----------------------

To use the Elasticsearch connector in a Mule application project:

1.  In Anypoint Studio, click **File \> New \> Project**![Create New
    Project](./images/mulesoft/elasticsearch-connector/create-new-project.png)
    <br>
    Select Mule project from the dialog box. 
    
    ![Mule Project](./images/mulesoft/elasticsearch-connector/select-mule-project.png)

2.  Enter a name for your new project and leave the remaining options
    with their default values ![Create new project dialogue
    box](./images/mulesoft/elasticsearch-connector/create-new-project-dialogue-box.png)

3.  Click **Finish** to create the project

Configuring the Elasticsearch Global Element
--------------------------------------------

Place the connector in your flow as applicable for your use case. To use
the Elasticsearch connector in your Mule application, you must configure
a global Elasticsearch element that is used by the Elasticsearch
connector. The Elasticsearch connector provides the following global
configuration(s).

![Elasticsearch-connector-config](./images/mulesoft/elasticsearch-connector/Elasticsearch-connector-configuration.png)

Authentication
--------------

To access Elasticsearch you have two following possible ways :

### 1. NO AUTHENTICATION (HTTP)

In NO AUTHENTICATION, you need to provide your Elasticsearch host and
port in a global configuration. NO AUTHENTICATION is generally
recommended for quick testing.For installation and starting
Elasticsearch, refer
[Installation](https://www.elastic.co/guide/en/elasticsearch/reference/current/_installation.html).

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
<td align="left"><p>Elasticsearch host IP or host name to connect</p></td>
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
external users, as it ensures better security.To make the Elasticsearch
run on HTTPS, generate server and client certificates on Elasticsearch
host using X-pack. Please refer [Encrypting communications in
Elasticseach](https://www.elastic.co/guide/en/elasticsearch/reference/current/configuring-tls.html#node-certificates)
for detailed information about running Elasticsearch on HTTPS and
generating required certificates.

-   Following parameters are required for **HTTPS** (Certificate Based
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
<td align="left"><p>Enter the Elasticsearch host IP or host name to connect</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Elasticsearch Port</strong></p></td>
<td align="left"><p>Enter the port of Elasticsearch engine</p></td>
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
> Access
> [X-Pack](https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-xpack.html)
> for detailed information to provide security and many other
> capabilities. By default, when you install Elasticsearch, X-Pack is
> also installed.

Understanding the Elasticsearch Connector
-----------------------------------------

The Elasticsearch connector functions within a Mule application. Using
the connector, your application can perform several operations that
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
    your application must deliver to, or can expect from, Elasticsearch.
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
    structure it must work with so you don’t have to figure it out
    manually.

Common Use Cases
================

-   [Elasticsearch as Document store](#use-case-1)

-   [Search for the phrases from particular dataset](#use-case-2)

-   [Different Elasticsearch operations that can be performed on Documents](#use-case-3)

Elasticsearch stores JSON documents. This is an example of a simple
document :

    {
            "speaker": "KING HENRY IV",
            "type": "line",
            "line_id": 7,
            "play_name": "Henry IV",
            "speech_number": 1,
            "line_number": "1.1.4",
            "text_entry": "To be commenced in strands afar remote"
    }

### 	  1.Elasticsearch as a Document Store {#use-case-1}

-   We will use the readily available dataset that can be found at [the
    complete works of William
    Shakespeare](https://www.elastic.co/guide/en/kibana/current/tutorial-load-dataset.html)
    and the Bulk operation of Elasticsearch connector for the usecase

    -   In Anypoint Studio, click **File \> New \> Mule Project**, name
        the project, and click **OK**

    -   In the search field, type **http** and drag the **HTTP
        connector** to the canvas

    -   Click the HTTP connector, click the **green plus** sign to the
        right of Connector Configuration, and in the next screen add the
        host as well as port, click **OK**

    -   In the Palette search for **Elasticsearch** and drag the **Bulk
        Operation** onto the canvas

    -   Select the connection configuration with connection as **HTTP
        connection** and add the host and port of Elasticsearch

    -   Configure the **Bulk Operation** options like index, type and
        the input dataset location

    -   Drag the **logger** onto the canvas and log `#[payload]` to log
        low level information of the operation

    -   In the Palette search for **Elasticsearch** and drag the **Get
        Document** operation onto the canvas

    -   Configure the **Get Document** operation options like index,
        type and document id along with other optional parameters

    -   Drag the **logger** onto the canvas and log `#[payload]` to log
        low level information of the operation

    -   After you create the flow, right-click the project and click
        **Run As \> Mule Applciation**
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
            <http:listener-config name="HTTP_Listener_config" doc:name="HTTP Listener config" doc:id="109dff29-90fb-4ed0-b474-22487e49ea1d" >
                    <http:listener-connection host="0.0.0.0" port="8081" />
            </http:listener-config>
            <elasticsearch:config name="Elasticsearch_Config1" doc:name="Elasticsearch Config" doc:id="fa6c73c9-56e8-45de-a5bd-dc0c4ba211cc" >
                    <elasticsearch:http-connection host="${host}" />
            </elasticsearch:config>
            <flow name="bulkoperationFlow" doc:id="6f18edae-31ae-44f8-819a-9cf062a92acc" >
                    <http:listener doc:name="Listener" doc:id="7226082d-691d-46ed-b9cf-39a19f0ecf9b" config-ref="HTTP_Listener_config" path="/bulky"/>
                    <elasticsearch:bulk-operation doc:name="Dataset Upload" doc:id="2c8400f3-7cb0-4a66-b24d-24c0a6fcdbe2" index="${index}" type="${indexType}" jsonfile="${datasetPath}" config-ref="Elasticsearch_Config1"/>
                    <logger level="INFO" doc:name="Log dataset insert response" doc:id="8ff5a4ae-10d0-4c07-94f0-e7e976b4b83e" message="Inserted Dataset #[payload]"/>
                    <elasticsearch:get-document doc:name="Get document" doc:id="d3ec0cd4-f1d9-44de-90cf-f4a78cfbdb1f" config-ref="Elasticsearch_Config1" index="${index}" type="${indexType}" documentId="${documentId}"/>
                    <logger level="INFO" doc:name="Log the get document details" doc:id="6c9112f9-4216-445a-bdb5-b64f6e6a469e" message="Document Generated #[payload]"/>
            </flow>
    </mule>


### 	2.Search for the phrases from particular dataset {#use-case-2}

-   To visually analyze the datasets, user can also use of
    [Kibana](https://www.elastic.co/guide/en/kibana/6.2/index.html)

-   Elasticsearch is preferred when you’re doing a lot of text search,
    where traditional RDBMS databases are not performing really well
    (poor configuration, acts as a black-box, poor performance).
    Elasticsearch is highly customizable, extendable through plugins.
    You can build robust search without much knowledge quite fast.

-   Please refer the previous use case to insert the dataset in
    Elasticsearch using bulk operation if the dataset is not available.

-   We will use different queries of search operation available in
    Elasticsearch connector for searching in this use case.

-   In this use case we will use **Query and Fetch**, **DFS query then
    Fetch** and **Query then Fetch** search type also **multi-query**,
    **multi-match-query**, **match-phrase-query** and
    **match-all-query** options of Elasticsearch.

    -   In Anypoint Studio, click **File \> New \> Mule Project**, name
        the project, and click **OK**

    -   In the search field, type **http** and drag the **HTTP
        connector** to the canvas

    -   Click the HTTP connector, click the **green plus** sign to the
        right of Connector Configuration, and in the next screen add the
        host as well as port, click **OK**

    -   In the search field, type **set variable** and drag the **Set
        Variable** component to the canvas

    -   Use the **Choice** connector to switch between the different
        query types depending on the condition variable value in the
        **set variable** component.

    -   In the Palette, search for **Elasticsearch** and drag the
        **Search** operation onto the canvas and set the different query
        and configuration options. Refer the sample XML provided below
        to set the values.

    -   Drag the **logger** whereever required and log `#[payload]` to
        log low level information of the operation.

    -   Click the **green plus** sign to the right of Connector
        Configuration to select among the HTTP, HTTP with basic
        authentication or HTTPS configuration.

    -   Drag the **logger** onto the canvas and log `#[payload]` to log
        low level information of the operation.

    -   After you create the flow, right-click the project and click
        **Run As \> Mule Applciation**

![search-flow](./images/mulesoft/elasticsearch-connector/usecase-2.png)

**Example Use Case Code :**

Paste this XML code into Anypoint Studio to experiment with the flow
described in the previous section.

    <flow name="Usecase_B" doc:id="1cdc935c-3ef6-469a-94e7-22fa49e84edb">
                    <http:listener doc:name="Listener"
                            doc:id="13285cd4-bb7f-40ba-93b8-e113ba3cce1c" config-ref="HTTP_Listener_config"
                            path="/choice" />
                    <set-variable value="2" doc:name="Set Variable"
                            doc:id="a33aaf60-23e7-4c8e-8738-9796feaf8937" variableName="test" />
                    <logger level="INFO" doc:name="Logger"
                            doc:id="96bafaeb-1fcb-4971-b06f-d06187ca240c" message="Set variable value #[vars.test]" />
                    <choice doc:name="Choice" doc:id="d1355aea-0240-4a79-aca3-db228412e8c4">
                            <when expression="#[vars.test=='4']">
                                    <elasticsearch:search doc:name="Multi Match"
                                            doc:id="d45b3b45-f5e8-4509-bac9-e7554f1f1d91" config-ref="Elasticsearch_Config"
                                            index="shakespeare" searchType="DFS_QUERY_THEN_FETCH">
                                            <elasticsearch:query-configuration>
                                                    <elasticsearch:multi-match-query
                                                            minimumShouldMatch="10%" searchString="limits of the charge set down"
                                                            operator="OR" autoGenerateSynonymsPhraseQuery="true" type="BEST_FIELDS"
                                                            tieBreaker="1.0" zeroTermsQuery="ALL">
                                                            <elasticsearch:fields>
                                                                    <elasticsearch:field value="line_number" />
                                                                    <elasticsearch:field value="speaker" />
                                                                    <elasticsearch:field value="text_entry" />
                                                            </elasticsearch:fields>
                                                    </elasticsearch:multi-match-query>
                                            </elasticsearch:query-configuration>
                                            <elasticsearch:search-source-configuration
                                                    size="100" timeout="50" sortOrder="ASC">
                                                    <elasticsearch:include-fields>
                                                            <elasticsearch:include-field value="text_entry" />
                                                    </elasticsearch:include-fields>
                                            </elasticsearch:search-source-configuration>
                                    </elasticsearch:search>
                                    <logger level="INFO" doc:name="Logger"
                                            doc:id="3d69a761-c71e-4948-b98d-2490af08ebb3" message="#[payload]" />

                            </when>
                            <when expression="#[vars.test=='1']">
                                    <elasticsearch:search doc:name="Match Query"
                                            doc:id="f072cb50-cd00-44b5-b6b3-f7a8cd28e969" config-ref="Elasticsearch_Config"
                                            index="shakespeare" searchType="DFS_QUERY_THEN_FETCH">
                                            <elasticsearch:query-configuration>
                                                    <elasticsearch:match-query field="speaker"
                                                            searchString="WESTMORELAND" zeroTermsQuery="ALL"
                                                            autoGenerateSynonymsPhraseQuery="true" />
                                            </elasticsearch:query-configuration>
                                            <elasticsearch:search-source-configuration
                                                    size="100" timeout="50">
                                                    <elasticsearch:include-fields>
                                                            <elasticsearch:include-field value="text_entry" />
                                                    </elasticsearch:include-fields>
                                                    <elasticsearch:exclude-fields>
                                                            <elasticsearch:exclude-field value="type" />
                                                            <elasticsearch:exclude-field value="line_id" />
                                                            <elasticsearch:exclude-field value="speech_number" />
                                                            <elasticsearch:exclude-field value="line_number" />
                                                    </elasticsearch:exclude-fields>
                                            </elasticsearch:search-source-configuration>
                                    </elasticsearch:search>
                                    <logger level="INFO" doc:name="Logger"
                                            doc:id="b4522649-745c-4a32-b6c2-1efd94f03021" message="#[payload]" />
                            </when>
                            <when expression="#[vars.test=='2']">
                                    <elasticsearch:search doc:name="Match Phrase"
                                            doc:id="ddf3528b-59f0-40df-a763-b2e2d92eca22" config-ref="Elasticsearch_Config"
                                            index="shakespeare" searchType="DFS_QUERY_THEN_FETCH">
                                            <elasticsearch:query-configuration>
                                                    <elasticsearch:match-phrase-query
                                                            field="play_name" queryString="Alls well that ends well" />
                                            </elasticsearch:query-configuration>
                                            <elasticsearch:search-source-configuration
                                                    size="100" timeout="50" sortOrder="ASC" sortByFieldName="line_id">
                                                    <elasticsearch:include-fields>
                                                            <elasticsearch:include-field value="speaker" />
                                                    </elasticsearch:include-fields>
                                            </elasticsearch:search-source-configuration>
                                    </elasticsearch:search>
                                    <logger level="INFO" doc:name="Logger"
                                            doc:id="e58a0d5e-2bba-4fe4-8cdf-3f134013d0a9" message="#[payload]" />
                            </when>
                            <otherwise>
                                    <elasticsearch:search doc:name="MatchAllQuery"
                                            doc:id="de99202c-3df7-4b17-b882-f29cf47e6d91" config-ref="Elasticsearch_Config"
                                            index="${search.index}" searchType="QUERY_THEN_FETCH">
                                            <elasticsearch:query-configuration>
                                                    <elasticsearch:match-all-query />
                                            </elasticsearch:query-configuration>
                                            <elasticsearch:search-source-configuration
                                                    size="100" timeout="50">
                                                    <elasticsearch:include-fields>
                                                            <elasticsearch:include-field value="speaker" />
                                                            <elasticsearch:include-field value="text_entry" />
                                                    </elasticsearch:include-fields>
                                            </elasticsearch:search-source-configuration>
                                    </elasticsearch:search>
                                    <logger level="INFO" doc:name="Logger"
                                            doc:id="70571ee6-9112-4e32-b45b-45bf5b90c2ca" message="#[payload]" />

                            </otherwise>

                    </choice>
    </flow>

###		3.Different Elasticsearch operations that can be performed on Documents {#use-case-3}

-   We will use different operations to implement the usecase like :

    1.  Create Index

    2.  Index Document

    3.  Get Document

    4.  Update Document

    5.  Delete Document

    6.  Delete Index

-   In Anypoint Studio, click **File \> New \> Mule Project**, name the
    project, and click **OK**

-   In the search field, type **http** and drag the **HTTP connector**
    to the canvas

-   Click the HTTP connector, click the **green plus** sign to the right
    of Connector Configuration, and in the next screen add the host as
    well as port, click **OK**

-   Select the connection configuration with connection as **HTTP
    connection** and add the host and port of Elasticsearch

-   In the Palette search for **Elasticsearch** and drag the **Create
    Index** onto the canvas

-   Similarly drag all the operations like Index Document, Get Document,
    Update Document, Delete Document and Delete Index as shown in the
    diagram below and configure the options using sample XML as a
    reference.

-   Drag the **logger** onto the canvas whereever required and log
    `#[payload]` to log low level information of the operation

-   After you create the flow, right-click the project and click **Run
    As \> Mule Applciation**
    ![Usecase\_C-flow](./images/mulesoft/elasticsearch-connector/usecase_3.png)

**Example Use Case Code :**

Paste this XML code into Anypoint Studio to experiment with the flow
described above.

    <flow name="bulkoperationFlow1" doc:id="712c5ec8-4d0a-46d7-96ea-115076ec24e6" >
            <http:listener doc:name="Listener" doc:id="f24fa5ea-c596-4bae-85b1-671aaf4a07b1" config-ref="HTTP_Listener_config" path="/random"/>
            <elasticsearch:create-index doc:name="Create a new index" doc:id="231bf462-814f-479f-82c4-8efe8c206b55" config-ref="Elasticsearch_Config1" index="demoapplication"/>
            <logger level="INFO" doc:name="Log the Index Information" doc:id="ea587347-f73c-4b7d-9c25-f997cffcc696" message="Created Index Response  #[payload]"/>
            <elasticsearch:index-document doc:name="Index a new document " doc:id="9cef6386-47cf-4b8f-9c63-4fadfabbacac" config-ref="Elasticsearch_Config1" index="demoapplication" type="doc" documentId="1" jsonInputPath="src/test/resources/indexDocument.json"></elasticsearch:index-document>
            <logger level="INFO" doc:name="Log the Index Document Information" doc:id="f46ccd14-401b-4665-89b5-c34174b86d1e" message="Index Document Response #[payload]"/>
            <elasticsearch:get-document doc:name="Get the indexed document" doc:id="5aac73c0-e05e-46dd-ae85-99579c3d431b" config-ref="Elasticsearch_Config1" type="doc" documentId="1" index="demoapplication"/>
            <logger level="INFO" doc:name="Log the Get Document Information" doc:id="55f3fa3f-06b2-4ae8-bf0b-c22b8d9d7122" message="Get Document Reponse #[payload]"/>
            <elasticsearch:update-document doc:name="Update the Indexed Document " doc:id="dd1e2813-9ff6-47da-b6b7-d9bcb9c0b6a0" config-ref="Elasticsearch_Config1" index="demoapplication" type="doc" documentId="1" jsonInputPath="src/test/resources/UpdateIndexdDocument.json"/>
            <logger level="INFO" doc:name="Log the Update Document Information" doc:id="6197318a-8f8e-492b-a461-7983d46471aa" message="Update document response #[payload]"/>
            <elasticsearch:get-document doc:name="Get the Updated Document" doc:id="2516658a-76d7-47a3-ac91-f674db705513" config-ref="Elasticsearch_Config1" index="demoapplication" type="doc" documentId="1"/>
            <logger level="INFO" doc:name="Log the Get Document Reponse" doc:id="72b0c17d-d343-4c7a-a8e7-f24aa5fda8db" message="Response of Get Document #[payload] "/>
            <elasticsearch:delete-document doc:name="Delete the Indexed Document" doc:id="58df7fac-907d-408c-8758-b35adfc57d57" config-ref="Elasticsearch_Config1" index="demoapplication" type="doc" documentId="1"/>
            <logger level="INFO" doc:name="Log the Delete Document Response" doc:id="6b5759ed-ecfe-4d10-8c60-dc4e0bde3a09" message="Delete Document Response #[payload]"/>
            <elasticsearch:delete-index doc:name="Delete the Index from Elasticsearch" doc:id="b804de26-594a-4cd8-ac35-2ff09d81833e" config-ref="Elasticsearch_Config1" index="demoapplication"/>
            <logger level="INFO" doc:name="Log the Delete Index Information" doc:id="e28fb4fc-ec2a-4843-8f3d-435225075bf0" message="Delete Index Response #[payload]"/>
    </flow>

Resources
=========

-   [Elasticsearch Connector Release Notes](https://opendoc.gslab.com/es_release_notes.html).

-   [Elasticsearch Connector API docs - Version 1](https://opendoc.gslab.com/es_api_reference.html).

{% include links.html %}