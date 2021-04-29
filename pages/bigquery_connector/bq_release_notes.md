---
title: Google BigQuery Connector Release Notes
keywords: sample
sidebar: bigquery_connector_sidebar
permalink: bq_release_notes.html
folder: bigquery_connector
---
Google BigQuery Connector Release Notes
================================

The Google BigQuery connector allows you to access the Google BigQuery
REST API through Anypoint Platform.

BigQuery is a RESTful web service that enables interactive analysis of
massive datasets working in conjunction with Google Storage. The
connector exposes Google BigQuery operations by executing their API
calls as per configuration.

Read through the User Guide to understand how to set up and configure a
basic flow using the connector. Review the connector operations and see
how they work by reviewing the API Reference document alongside the demo
applications.



### Google BigQuery Connector v2.1.0

#### Version V2.1.0 Compatibility
<table border="1">
<tr><th>Software</th><th>Version</th></tr>
<tr><td>Mule Runtime</td><td>4.2.1</td></tr>
</table>

#### Fixed Issues

1. Error - 'Could not serialize object' in the output of 'Get Query Result, Query and List Table Data'.

2. NullPointerException occurred while trying to access property 'nextPage' if nextPage does not exist in result.

#### Features

1. Connector configuration allows passing service account key file content directly in BASE64 encoded string format along with service key file name.



### Google BigQuery Connector v2.0.0

#### Version V2.0.0 Compatibility
<table border="1">
<tr><th>Software</th><th>Version</th></tr>
<tr><td>Mule Runtime</td><td>4.2.1</td></tr>
</table>

#### Features

1. Output of Google BigQuery connector operations are changed and simplified. Please refer [Connector Upgrade Document](bq_1.0.0_to_2.0.0_upgrade.html) for more details.



### Google BigQuery Connector v1.0.0

#### Version V1.0.0 Compatibility
<table border="1">
<tr><th>Software</th><th>Version</th></tr>
<tr><td>Mule Runtime</td><td>4.2.1</td></tr>
</table>

#### Features

1.  Authentication using Service Account Key

2.  Supports following operations of Google BigQuery service:

    -   Cancel Job

    -   Create Dataset

    -   Create Job

        -   Copy Job

        -   Extract Job

        -   Load Job

        -   Query Job

    -   Create Table

    -   Delete Dataset

    -   Delete Table

    -   Get Dataset

    -   Get Job

    -   Get Query Result

    -   Get Table

    -   Insert All

    -   List Dataset

    -   List Job

    -   List Table

    -   List Table Data

    -   Query

    -   Update Dataset

    -   Update Table

### Support Resources

-   Learn how to [Install Anypoint
    Connectors](https://docs.mulesoft.com/anypoint-studio/v/7.1/add-modules-in-studio-to).

-   Access [MuleSoft Help
    Center](https://help.mulesoft.com/s/) for support, training and to post
    questions and get help from Mule’s broad community of users.

-   To access MuleSoft’s expert support team,
    [subscribe](http://www.mulesoft.com/mule-esb-subscription) to Mule
    ESB Enterprise and log in to MuleSoft’s [Customer
    Portal](http://www.mulesoft.com/support-login).

{% include links.html %}
