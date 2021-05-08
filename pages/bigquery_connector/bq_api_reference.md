---
title: Google BigQuery Connector API Reference 
keywords: sample
sidebar: bigquery_connector_sidebar
permalink: bq_api_reference.html
folder: bigquery_connector
---

<div id="content">
<div class="sect1">
<h2 id="_configurations">Configurations</h2>
<div class="sectionbody">
<hr>
<div class="sect2">
<h3 id="config">Config</h3>
<div class="paragraph">
<p>
Default configuration
</p>
</div>
<div class="sect3">
<h4 id="_parameters">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name for this configuration. Connectors reference the configuration with this name.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Connection</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#config_connection">Service Account File</a> &#160;</p>
</li>
<li>
<p><a href="#config_key-file-content">Service Account File Content</a> &#160;</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The connection types that can be provided to this configuration.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Expiration Policy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#ExpirationPolicy">Expiration Policy</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configures the minimum amount of time that a dynamic configuration instance can remain idle before the runtime considers it eligible for expiration. This does not mean that the platform will expire the instance at the exact moment that it becomes eligible. The runtime will actually purge the instances when it sees it fit.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_connection_types">Connection Types</h4>
<div class="sect4">
<h5 id="config_connection">Service Account File</h5>
<div class="paragraph">
<p>
This class provides connection with Project ID and JSON service account key file name.
</p>
</div>
<div class="sect5">
<h6 id="_parameters_2">Parameters</h6>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project ID</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project Identity</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Service Account Key (JSON) File Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">JSON service account key file name for service authentication credentials.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Reconnection">Reconnection</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">When the application is deployed, a connectivity test is performed on all connectors. If set to true, deployment will fail if the test doesn't pass after exhausting the associated reconnection strategy</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Pooling Profile</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#PoolingProfile">Pooling Profile</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Characteristics of the connection pool</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
</div>
<div class="sect4">
<h5 id="config_key-file-content">Service Account File Content</h5>
<div class="paragraph">
<p>
This class provides connection with Project ID and JSON service account key file content in base64 format.
</p>
</div>
<div class="sect5">
<h6 id="_parameters_3">Parameters</h6>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project ID</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project Identity</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Service Account Key (JSON) File Content (base64 encoded)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">JSON service account key file content in base64 encoded format for service authentication credentials.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Reconnection">Reconnection</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">When the application is deployed, a connectivity test is performed on all connectors. If set to true, deployment will fail if the test doesn't pass after exhausting the associated reconnection strategy</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Pooling Profile</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#PoolingProfile">Pooling Profile</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Characteristics of the connection pool</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
<div class="sect3">
<h4 id="_associated_operations">Associated Operations</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#cancelJob">Cancel Job</a> &#160;</p>
</li>
<li>
<p><a href="#createDataset">Create Dataset</a> &#160;</p>
</li>
<li>
<p><a href="#createJob">Create Job</a> &#160;</p>
</li>
<li>
<p><a href="#createTable">Create Table</a> &#160;</p>
</li>
<li>
<p><a href="#deleteDataset">Delete Dataset</a> &#160;</p>
</li>
<li>
<p><a href="#deleteTable">Delete Table</a> &#160;</p>
</li>
<li>
<p><a href="#getDataset">Get Dataset</a> &#160;</p>
</li>
<li>
<p><a href="#getJob">Get Job</a> &#160;</p>
</li>
<li>
<p><a href="#getQueryResult">Get Query Result</a> &#160;</p>
</li>
<li>
<p><a href="#getTable">Get Table</a> &#160;</p>
</li>
<li>
<p><a href="#insertAll">Insert All</a> &#160;</p>
</li>
<li>
<p><a href="#listDataset">List Dataset</a> &#160;</p>
</li>
<li>
<p><a href="#listJob">List Job</a> &#160;</p>
</li>
<li>
<p><a href="#listTable">List Table</a> &#160;</p>
</li>
<li>
<p><a href="#listTableData">List Table Data</a> &#160;</p>
</li>
<li>
<p><a href="#query">Query</a> &#160;</p>
</li>
<li>
<p><a href="#updateDataset">Update Dataset</a> &#160;</p>
</li>
<li>
<p><a href="#updateTable">Update Table</a> &#160;</p>
</li>
</ul>
</div>
</div>
</div>
</div>
</div>
<div class="sect1">
<h2 id="_operations">Operations</h2>
<div class="sectionbody">
<div class="sect2">
<h3 id="cancelJob">Cancel Job</h3>
<div class="paragraph">
<p><code>&lt;bigquery:cancel-job&gt;</code></p>
</div>
<div class="paragraph">
<p>
CancelJob operation sends a job cancel request. If the location of the job is not "US" or "EU", the jobId must specify the job location. It logs 'Job Not Found', if specified Job does not exist. It won't log/return anything on successful execution.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_3">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job location</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_FAILURE_EXCEPTION &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="createDataset">Create Dataset</h3>
<div class="paragraph">
<p><code>&lt;bigquery:create-dataset&gt;</code></p>
</div>
<div class="paragraph">
<p>
CreateDataset operation creates a new empty dataset. A dataset is a grouping mechanism that holds zero or more tables.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_4">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset identity. Dataset ID must be alphanumeric (plus underscores, dashes, and colons) and must be at most 1024 characters long.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Life Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default lifetime of all tables in the dataset, in milliseconds. Table expiration should not be less than 3600000ms.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User-friendly description for the dataset</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User-friendly name for the dataset</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Labels</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of labels associated with labels</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Geographic location where the dataset should reside</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ACL</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of One of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="#UserAcl">User Acl</a></p>
</li>
<li>
<p><a href="#DomainAcl">Domain Acl</a></p>
</li>
<li>
<p><a href="#ViewAcl">View Acl</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset's access control configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Dataset">Dataset</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_2">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_2">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_EMPTY &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="createJob">Create Job</h3>
<div class="paragraph">
<p><code>&lt;bigquery:create-job&gt;</code></p>
</div>
<div class="paragraph">
<p>
CreateJob operation create and start an asynchronous job.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_5">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Config</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>One of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="#CopyJob">Copy Job</a></p>
</li>
<li>
<p><a href="#ExtractJob">Extract Job</a></p>
</li>
<li>
<p><a href="#LoadJob">Load Job</a></p>
</li>
<li>
<p><a href="#QueryJob">Query Job</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobInfoOptions">Job Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery create job options configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_2">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Job">Job</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_3">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_3">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_FAILURE_EXCEPTION &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="createTable">Create Table</h3>
<div class="paragraph">
<p><code>&lt;bigquery:create-table&gt;</code></p>
</div>
<div class="paragraph">
<p>
CreateTable operation creates a new table in existing dataset.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_6">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInfoConfiguration">Table Info Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table information configuration to create a table</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#TableFieldConfiguration">Table Field Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Schema details , Field Type , Field Name , Field Description , Field Mode , Sub-fields.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Option</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInfoOptions">Table Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Create table information options</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_3">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInformation">Table Information</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_4">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_4">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:TABLE_NOT_FOUND &#160;</p>
</li>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="deleteDataset">Delete Dataset</h3>
<div class="paragraph">
<p><code>&lt;bigquery:delete-dataset&gt;</code></p>
</div>
<div class="paragraph">
<p>
DeleteDataset operation deletes the dataset specified by datasetId.
 It logs 'Dataset Not Empty' if deleting non-empty dataset is disabled and Dataset is still in use. It logs 'Dataset Not Found', if specified dataset does not exist. It won't log/return anything on successful execution.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_7">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery dataset Id</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Delete Non Empty Dataset</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Delete a dataset even if non-empty</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_5">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_5">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_EMPTY &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="deleteTable">Delete Table</h3>
<div class="paragraph">
<p><code>&lt;bigquery:delete-table&gt;</code></p>
</div>
<div class="paragraph">
<p>
DeleteTable operation deletes the specified table from the dataset. This operation logs 'Table Not found', if specified table does not exist. And it won't log/return anything on successful execution.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_8">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Configuration with tableId and datasetId</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_6">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_6">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:TABLE_NOT_FOUND &#160;</p>
</li>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="getDataset">Get Dataset</h3>
<div class="paragraph">
<p><code>&lt;bigquery:get-dataset&gt;</code></p>
</div>
<div class="paragraph">
<p>
GetDataset operation returns the dataset specified by datasetId.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_9">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery dataset identity</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#DatasetInfoOption">Dataset Info Option</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Get dataset options configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_4">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Dataset">Dataset</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_7">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_7">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_EMPTY &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="getJob">Get Job</h3>
<div class="paragraph">
<p><code>&lt;bigquery:get-job&gt;</code></p>
</div>
<div class="paragraph">
<p>
GetJob operation returns information about a specific job.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_10">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job location</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobInfoOptions">Job Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job information options configurations</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_5">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Job">Job</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_8">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_8">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_FAILURE_EXCEPTION &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="getQueryResult">Get Query Result</h3>
<div class="paragraph">
<p><code>&lt;bigquery:get-query-result&gt;</code></p>
</div>
<div class="paragraph">
<p>
GetQueryResult operation returns the results of a query job.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_11">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job location</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Result Options</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobQueryResultsOption">Job Query Results Option</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job query result options configurations</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_6">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableResult">Table Result</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_9">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_9">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_FAILURE_EXCEPTION &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="getTable">Get Table</h3>
<div class="paragraph">
<p><code>&lt;bigquery:get-table&gt;</code></p>
</div>
<div class="paragraph">
<p>
GetTable operation returns the specified table from dataset.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_12">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery dataset identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery table identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Option</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInfoOptions">Table Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Get table information options</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_7">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInformation">Table Information</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_10">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_10">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:TABLE_NOT_FOUND &#160;</p>
</li>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="insertAll">Insert All</h3>
<div class="paragraph">
<p><code>&lt;bigquery:insert-all&gt;</code></p>
</div>
<div class="paragraph">
<p>
InsertAll operation streams data into BigQuery one record at a time without running the load job.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_13">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Rows Data</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Row data to be inserted</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore Unknown Values</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether to accept rows that contain values that do not match the schema.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Skip Invalid Rows</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether to insert all valid rows of a request, even if invalid rows exist.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Template Suffix</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The destination table is treated as a base template.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_8">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#InsertAllResponse">Insert All Response</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_11">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_11">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="listDataset">List Dataset</h3>
<div class="paragraph">
<p><code>&lt;bigquery:list-dataset&gt;</code></p>
</div>
<div class="paragraph">
<p>
ListDataset operation returns partial information on each dataset: DatasetId, FriendlyName and GeneratedId. To get complete information use "Get Dataset" operation.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_14">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List Dataset Option</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#ListDatasetOption">List Dataset Option</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List dataset options configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_9">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#Dataset">Dataset</a></p>
</div></div></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Attributes Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#PageAttribute">Page Attribute</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_12">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_12">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_EMPTY &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="listJob">List Job</h3>
<div class="paragraph">
<p><code>&lt;bigquery:list-job&gt;</code></p>
</div>
<div class="paragraph">
<p>
ListJob operation lists all jobs that you started in the specified project.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_15">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobInfoOptions">Job Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job options configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the token from which to start listing jobs</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the maximum number of jobs returned per page</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">State</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>DONE</p>
</li>
<li>
<p>PENDING</p>
</li>
<li>
<p>RUNNING</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">State of the job (DONE, PENDING, RUNNING)</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_10">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#Job">Job</a></p>
</div></div></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Attributes Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#PageAttribute">Page Attribute</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_13">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_13">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_FAILURE_EXCEPTION &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="listTable">List Table</h3>
<div class="paragraph">
<p><code>&lt;bigquery:list-table&gt;</code></p>
</div>
<div class="paragraph">
<p>
ListTable operation list the tables in the specified dataset. This operation returns partial information on each table: TableId, FriendlyName, Generated and type, which is part of Definition.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_16">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery dataset identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List Table Options</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#ListTableOptions">List Table Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List table options configurations</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_11">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#TableInformation">Table Information</a></p>
</div></div></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Attributes Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#PageAttribute">Page Attribute</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_14">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_14">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:TABLE_NOT_FOUND &#160;</p>
</li>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="listTableData">List Table Data</h3>
<div class="paragraph">
<p><code>&lt;bigquery:list-table-data&gt;</code></p>
</div>
<div class="paragraph">
<p>
ListTableData operation list the content of a table in rows.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_17">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery dataset identity</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery table identity</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the maximum number of rows returned per page</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page token of the request.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Start Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Start row index of the table.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_12">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableResult">Table Result</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_15">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_15">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="query">Query</h3>
<div class="paragraph">
<p><code>&lt;bigquery:query&gt;</code></p>
</div>
<div class="paragraph">
<p>
Runs the query associated with the request, using the given JobId or using an internally-generated random JobId.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_18">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#QueryJob">Query Job</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery query configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Information</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobInfoOptions">Job Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job options configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Google BigQuery job location</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_13">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableResult">Table Result</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_16">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_16">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_FAILURE_EXCEPTION &#160;</p>
</li>
<li>
<p>BIGQUERY:JOB_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="updateDataset">Update Dataset</h3>
<div class="paragraph">
<p><code>&lt;bigquery:update-dataset&gt;</code></p>
</div>
<div class="paragraph">
<p>
UpdateDataset operation updates information in an existing dataset.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_19">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#DatasetInfoOption">Dataset Info Option</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Update dataset options configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset identity. Dataset ID must be alphanumeric (plus underscores, dashes, and colons) and must be at most 1024 characters long.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Life Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default lifetime of all tables in the dataset, in milliseconds. Table expiration should not be less than 3600000ms.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User-friendly description for the dataset</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User-friendly name for the dataset</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Labels</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of labels associated with labels</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Geographic location where the dataset should reside</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ACL</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of One of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="#UserAcl">User Acl</a></p>
</li>
<li>
<p><a href="#DomainAcl">Domain Acl</a></p>
</li>
<li>
<p><a href="#ViewAcl">View Acl</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset's access control configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_14">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Dataset">Dataset</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_17">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_17">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_EMPTY &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:DATASET_NOT_FOUND &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="updateTable">Update Table</h3>
<div class="paragraph">
<p><code>&lt;bigquery:update-table&gt;</code></p>
</div>
<div class="paragraph">
<p>
UpdateTable operation updates information in an existing table.
</p>
</div>
<div class="sect3">
<h4 id="_parameters_20">Parameters</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 20%;">
<col style="width: 35%;">
<col style="width: 20%;">
<col style="width: 5%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Name</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-center valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of the configuration to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInfoConfiguration">Table Info Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table information configuration to update table</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#TableFieldConfiguration">Table Field Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Schema details , Field Type , Field Name , Field Description , Field Mode , Sub-fields.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Option</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInfoOptions">Table Info Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table options configurations</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Variable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The name of a variable on which the operation's output will be placed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Target Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">#[payload]</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A retry strategy in case of connectivity errors</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_output_15">Output</h4>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 50%;">
<col style="width: 50%;">
</colgroup>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock"><strong>Type</strong></p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableInformation">Table Information</a></p>
</div></div></td>
</tr>
</tbody>
</table>
</div>
<div class="sect3">
<h4 id="_for_configurations_18">For Configurations.</h4>
<div class="ulist">
<ul>
<li>
<p><a href="#config">Config</a> &#160;</p>
</li>
</ul>
</div>
</div>
<div class="sect3">
<h4 id="_throws_18">Throws</h4>
<div class="ulist">
<ul>
<li>
<p>BIGQUERY:TABLE_NOT_FOUND &#160;</p>
</li>
<li>
<p>BIGQUERY:EXECUTION &#160;</p>
</li>
<li>
<p>BIGQUERY:CONNECTIVITY &#160;</p>
</li>
<li>
<p>MULE:CONNECTIVITY &#160;</p>
</li>
<li>
<p>BIGQUERY:RETRY_EXHAUSTED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
</div>
</div>
<div class="sect1">
<h2 id="_types">Types</h2>
<div class="sectionbody">
<div class="sect2">
<h3 id="Reconnection">Reconnection</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fails Deployment</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">When the application is deployed, a connectivity test is performed on all connectors. If set to true, deployment will fail if the test doesn&#8217;t pass after exhausting the associated reconnection strategy</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reconnection Strategy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="ulist">
<ul>
<li>
<p><a href="#reconnect">Reconnect</a></p>
</li>
<li>
<p><a href="#reconnect-forever">Reconnect Forever</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The reconnection strategy to use</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="reconnect">Reconnect</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Frequency</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">How often (in ms) to reconnect</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Count</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">How many reconnection attempts to make</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="reconnect-forever">Reconnect Forever</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Frequency</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">How often (in ms) to reconnect</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="PoolingProfile">Pooling Profile</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Active</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Controls the maximum number of Mule components that can be borrowed from a session at one time. When set to a negative value, there is no limit to the number of components that may be active at one time. When maxActive is exceeded, the pool is said to be exhausted.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Idle</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Controls the maximum number of Mule components that can sit idle in the pool at any time. When set to a negative value, there is no limit to the number of Mule components that may be idle at one time.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Wait</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the number of milliseconds to wait for a pooled component to become available when the pool is exhausted and the exhaustedAction is set to WHEN_EXHAUSTED_WAIT.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Min Eviction Millis</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Determines the minimum amount of time an object may sit idle in the pool before it is eligible for eviction. When non-positive, no objects will be evicted from the pool due to idle time alone.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Eviction Check Interval Millis</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the number of milliseconds between runs of the object evictor. When non-positive, no object evictor is executed.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Exhausted Action</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>WHEN_EXHAUSTED_GROW</p>
</li>
<li>
<p>WHEN_EXHAUSTED_WAIT</p>
</li>
<li>
<p>WHEN_EXHAUSTED_FAIL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the behavior of the Mule component pool when the pool is exhausted. Possible values are: "WHEN_EXHAUSTED_FAIL", which will throw a NoSuchElementException, "WHEN_EXHAUSTED_WAIT", which will block by invoking Object.wait(long) until a new or idle object is available, or WHEN_EXHAUSTED_GROW, which will create a new Mule instance and return it, essentially making maxActive meaningless. If a positive maxWait value is supplied, it will block for at most that many milliseconds, after which a NoSuchElementException will be thrown. If maxThreadWait is a negative value, it will block indefinitely.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Initialisation Policy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>INITIALISE_NONE</p>
</li>
<li>
<p>INITIALISE_ONE</p>
</li>
<li>
<p>INITIALISE_ALL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Determines how components in a pool should be initialized. The possible values are: INITIALISE_NONE (will not load any components into the pool on startup), INITIALISE_ONE (will load one initial component into the pool on startup), or INITIALISE_ALL (will load all components in the pool on startup)</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Disabled</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether pooling should be disabled</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ExpirationPolicy">Expiration Policy</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Idle Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A scalar time value for the maximum amount of time a dynamic configuration instance should be allowed to be idle before it&#8217;s considered eligible for expiration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time Unit</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>NANOSECONDS</p>
</li>
<li>
<p>MICROSECONDS</p>
</li>
<li>
<p>MILLISECONDS</p>
</li>
<li>
<p>SECONDS</p>
</li>
<li>
<p>MINUTES</p>
</li>
<li>
<p>HOURS</p>
</li>
<li>
<p>DAYS</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A time unit that qualifies the maxIdleTime attribute</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="Dataset">Dataset</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Acl</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#Acl">Acl</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Dataset's access control configuration.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creation Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The time when this dataset was created, in milliseconds since the epoch.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#DatasetId">Dataset Id</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The dataset identity.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default Table Lifetime</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The default lifetime of all tables in the dataset, in milliseconds.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A user-friendly description for the dataset.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Etag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The hash of the dataset resource.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A user-friendly name for the dataset.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Generated Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The service-generated id for the dataset.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Labels</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A map for labels applied to the dataset.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Last Modified</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The time when this dataset or any of its tables was last modified, in milliseconds since the epoch.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The geographic location where the dataset should reside.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Self Link</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">URL that can be used to access the resource again.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="Acl">Acl</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Entity</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Entity">Entity</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The entity for this ACL.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Role</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The role specified by this ACL.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="Entity">Entity</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Types of BigQuery entities.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="DatasetId">Dataset Id</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Dataset Identity</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Project Name</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="Job">Job</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobConfiguration">Job Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The job's configuration</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Etag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The hash of the job resource.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Generated Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The service-generated id for the job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobId">Job Id</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The job identity.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Self Link</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">URL that can be used to access the resource again.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Statistics</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobStatistics">Job Statistics</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Information about the job, including starting time and ending time of the job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Status</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#JobStatus">Job Status</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The status of this job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User Email</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The email address of the user who ran the job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="JobConfiguration">Job Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Type of a BigQuery Job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="JobId">Job Id</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The job's id.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The job's location.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Job's project id.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="JobStatistics">Job Statistics</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creation Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The creation time of the job in milliseconds since epoch.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">End Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The end time of the job in milliseconds since epoch.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Start Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The start time of the job in milliseconds since epoch.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="JobStatus">Job Status</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Error</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#BigQueryError">Big Query Error</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The final error result of the job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Execution Errors</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#BigQueryError">Big Query Error</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">All errors encountered during the running of the job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">State</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The state of the job.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="BigQueryError">BigQuery Error</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Location where the error occurred, if present.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Message</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A human-readable description of the error.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Reason</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Short error code that summarizes the error.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="JobInfoOptions">Job Info Options</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Configuration</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">E Tag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job eTag</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Identity</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Job Reference</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A job reference is a fully qualified identifier for refering to a job.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Self Link</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A URL that can be used to access the resource again.
 You can use this URL in Get or Update requests to the resource.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Statistics</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Information about the job, including starting time and ending time of the job.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Status</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The status of this job.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User Mail</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The email address of the user who ran the job.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableInformation">Table Information</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creation Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The time when this table was created, in milliseconds since the epoch.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Table Description</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">E Tag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A hash of the page of results.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Encryption Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#EncryptionConfiguration">Encryption Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Custom encryption configuration (e.g., Cloud KMS keys).</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Expiration Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The time when this table expires, in milliseconds since the epoch. If not present, the table will persist indefinitely. Expired tables will be deleted and their storage reclaimed.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The user-friendly name for the table.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Generated Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The service-generated id for the table.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Labels</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A map for labels applied to the table.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Last Modified Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Table last modified time</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Bytes</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The size of the table in bytes</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Long Term Bytes</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The number of bytes considered "long-term storage" for reduced billing purposes.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Rows</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Number of rows in a table</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Self Link</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">An URL that can be used to access the resource again.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableId">Table Id</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The table identity.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Definition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableDefinition">Table Definition</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Table Definition</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="EncryptionConfiguration">Encryption Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Kms Key Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">KMS key name for encryption configuration</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableId">Table Id</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Dataset Identity</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Project's user-defined id.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Table Identity</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableDefinition">Table Definition</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Schema</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Schema">Schema</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The table's schema.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The table's type.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="Schema">Schema</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#Field">Field</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The fields in the current table schema.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="Field">Field</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The field description.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Mode</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The field mode.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The field name.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sub Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#Field">Field</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The list of sub-fields if field type is a RECORD.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The field type.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableInfoConfiguration">Table Info Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Details of table(Table Name, Dataset Name)</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Description</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Kms Key Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creates a EncryptionConfiguration object for KMS key name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Expiration Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The time when this table expires, in milliseconds since the epoch. If not present, the table will persist indefinitely. Expired tables will be deleted and their storage
 reclaimed.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The user-friendly name for the table.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Labels</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The labels associated with the table. Can be used to organize and group your tables.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableConfiguration">Table Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset identity.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableFieldConfiguration">Table Field Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The table field name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The type of the table field Supported types are : BOOLEAN, BYTES, DATE, DATETIME, FLOAT, INTEGER, RECORD, STRING, TIME, TIMESTAMP</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The Table field description</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field Mode</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Mode for a Table field. NULLABLE fields can be set to null, REQUIRED fields must be provided. REPEATED fields can contain more than one value.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field Sub Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#TableFieldConfiguration">Table Field Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sub field of the field name. Type of the parent field must be RECORD to add subfield.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableInfoOptions">Table Info Options</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creation Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The time when this table was created, in milliseconds since the epoch.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Description</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">E Tag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A hash of the page of results.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Expiration Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The time when this table expires, in milliseconds since the epoch.
 If not present, the table will persist indefinitely.
 Expired tables will be deleted and their storage reclaimed.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The user-friendly name for the table.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">An opaque ID of the table.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Last Modified Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table last modified time</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The geographic location where the table should reside.
 Possible values include EU and US. The default value is US.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Bytes</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The size of the table in bytes</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Rows</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Number of rows in a table</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Schema</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Schema</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Self Link</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A URL that can be used to access the resource again.
 You can use this URL in Get or Update requests to the resource.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Streaming Buffer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time Partitioning</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Configures time-based partitioning for the table.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The type of table.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">View</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The view definition of table</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="DatasetInfoOption">Dataset Info Option</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Access</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">It defines dataset access for one or more entities</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creation Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creation time of Dataset</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Reference</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A reference that identifies the dataset.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Description</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset description</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">E Tag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset eTag</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Friendly Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset friendly name</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Labels</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Labels</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Last Modified Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset last modified time</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Location</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The geographic location where the dataset should reside.
 Possible values include EU and US. The default value is US.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Self Link</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A URL that can be used to access the resource again.
 You can use this URL in Get or Update requests to the resource.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset Identity</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableResult">Table Result</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Next Page</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableResult">Table Result</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The next page of result.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Next Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The token of next page of result.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Schema</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#Schema">Schema</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">It represents the schema for a Google BigQuery Table or data source.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Total Rows</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Total number of rows in the complete result set, which can be more than the number of rows in the first page of results returned by getValues().</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Values</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Array of <a href="#FieldValue">Field Value</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Represent rows in returned query result (table row).</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="FieldValue">Field Value</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Attribute</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>PRIMITIVE</p>
</li>
<li>
<p>REPEATED</p>
</li>
<li>
<p>RECORD</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">The attribute of this Field Value.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boolean Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a Boolean.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Bytes Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Binary</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a byte array.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Double Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a Double.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Long Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a long.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Null</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">true if this field's value is null, false otherwise.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Numeric Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a BigDecimal.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Record Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#FieldValue">Field Value</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a list of FieldValue.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Repeated Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#FieldValue">Field Value</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a list of FieldValue.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a String.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timestamp Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as a long, representing a timestamp in microseconds since epoch (UNIX time).</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Value</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Any</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">This field's value as an Object.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="JobQueryResultsOption">Job Query Results Option</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Wait Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">How long to wait for the query to complete, in milliseconds,
 before the request times out and returns.
 Note that this is only a timeout for the request, not the query.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Number of records to be displayed on a page.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specify the page token from which to start listing datasets</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Start Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Zero-based index of the starting row.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="InsertAllResponse">Insert All Response</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Insert Errors</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">All insertion errors as a map whose keys are indexes of rows that failed to insert.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="PageAttribute">Page Attribute</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Has Next Page</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Used for paging results. When this field is true, it indicates additional results are available.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Specify the page token from which to start listing datasets</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ListDatasetOption">List Dataset Option</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">All</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List all datasets, even hidden ones.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specify the maximum number of datasets returned per page</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specify the page token from which to start listing datasets</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ListTableOptions">List Table Options</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specify the maximum number of datasets returned per page</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Page Token</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The page token from which to start listing datasets</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="QueryJob">Query Job</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A query string, following the BigQuery query syntax, of the query to execute.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow Large Results</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets whether the job is enabled to create arbitrarily large results.
 If true the query is allowed to create large results at a slight cost in performance.
 If true Destination Table must be provided.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default Dataset</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies the default datasetId and projectId to assume for any unqualified table names in the query.
 If not set, all table names in the query string must be qualified in the format 'datasetId.tableId'.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dry Run</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If set to true, BigQuery doesn&#8217;t run the job.
  Instead, if the query is valid,
  BigQuery returns statistics about the job such as how many bytes would be processed.
  If the query is invalid, an error returns. The default value is false.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Flatten Results</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets whether nested and repeated fields should be flattened.
 If set to false AllowLargeResults must be true. By default results are flattened.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Maximum Billing Tier</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Limits the billing tier for this job.
 Queries that have resource usage beyond this tier will fail (without incurring a charge).
 If unspecified, this will be set to your project default.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Named Parameters</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#NamedParameterConfiguration">Named Parameter Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">the query parameters to a set of named query parameters to use in the query.
 Named parameters are denoted using an @ prefix, e.g.
 @myParam for a parameter named "myParam".
 SELECT * FROM &lt;table&gt; WHERE &lt;column_name&gt;=@myParam in query</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Positional Query Parameter Values</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#QueryParameterValueConfiguration">Query Parameter Value Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the query parameters to a list of positional query parameters to use in the query.
 Positional parameters are denoted in the query with a question mark (?).
 SELECT * FROM &lt;table&gt; WHERE &lt;column_name&gt;=?</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Priority</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>BATCH</p>
</li>
<li>
<p>INTERACTIVE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">a priority for the query.
 If not specified the priority is assumed to be INTERACTIVE.
 Query is executed as soon as possible and count towards the concurrent rate limit and the daily rate limit.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">External Table Definitions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#ExternalTableDefinitionConfiguration">External Table Definition Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">BigQuery&#8217;s external tables are tables whose data reside outside of BigQuery
 But can be queried as normal BigQuery tables.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Use Legacy Sql</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">UseLegacySql must be set to false to use query parameters</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Use Query Cache</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether to look for the result in the query cache.
 The query cache is a best-effort cache that will be flushed whenever tables in the query are modified.
 Moreover, the query cache is only available when Destination Table is not set.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User Defined Functions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#UserDefinedFunctionConfiguration">User Defined Function Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">For legacy SQL, specify user defined function here.
 For Standard SQL, specify user defined function in Query string.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Create Disposition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>CREATE_IF_NEEDED</p>
</li>
<li>
<p>CREATE_NEVER</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether the job is allowed to create new tables
 CREATE_IF_NEEDED :- Configures the job to create the table if it does not exist.
 CREATE_NEVER :- Configures the job to fail with a not-found error if the table does not exist.
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.CreateDisposition.html">Create Disposition</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Destination Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the table where to put query results.
 If not provided a new table is created.
 This value is required if Allow Large Results is set to true.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Schema Update Option</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>ALLOW_FIELD_ADDITION</p>
</li>
<li>
<p>ALLOW_FIELD_RELAXATION</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specifies options relating to allowing the schema of the destination table
 To be updated as a side effect of the load or query job.
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.SchemaUpdateOption.html">Schema Update Option</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Write Disposition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>WRITE_APPEND</p>
</li>
<li>
<p>WRITE_EMPTY</p>
</li>
<li>
<p>WRITE_TRUNCATE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Action that should occur if the destination table already exists.
 WRITE_APPEND :- Configures the job to append data to the table if it already exists.
 WRITE_EMPTY :- Configures the job to fail with a duplicate error if the table already exists.
 WRITE_TRUNCATE :- Configures the job to overwrite the table data if table already exists.
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.WriteDisposition.html">Write Disposition</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Kms Key Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creates a EncryptionConfiguration object for KMS key name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="NamedParameterConfiguration">Named Parameter Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Key</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A parameter given to a query.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Named Parameter</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#QueryParameterValueConfiguration">Query Parameter Value Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Contains the type of the parameter and value of the parameter.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="QueryParameterValueConfiguration">Query Parameter Value Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Array Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The type of the array's elements, if this is an array.</td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>BOOL</p>
</li>
<li>
<p>BYTES</p>
</li>
<li>
<p>DATE</p>
</li>
<li>
<p>DATETIME</p>
</li>
<li>
<p>FLOAT64</p>
</li>
<li>
<p>INT64</p>
</li>
<li>
<p>NUMERIC</p>
</li>
<li>
<p>STRING</p>
</li>
<li>
<p>TIME</p>
</li>
<li>
<p>TIMESTAMP</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">The type of the parameter.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Values</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The values of the parameter.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ExternalTableDefinitionConfiguration">External Table Definition Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Name of the table</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source Uris</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The fully-qualified URIs that point to your data in Google Cloud Storage. Each URI can contain one '*' wildcard character that must come after the bucket's name. 
Size limits related to load jobs apply to external data sources, plus an additional limit of 10 GB maximum size across all URIs.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Schema</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableSchema">Table Schema</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The Schema for the external data</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Format</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>AVRO</p>
</li>
<li>
<p>CSV</p>
</li>
<li>
<p>DATASTORE_BACKUP</p>
</li>
<li>
<p>GOOGLE_SHEETS</p>
</li>
<li>
<p>JSON</p>
</li>
<li>
<p>ORC</p>
</li>
<li>
<p>PARQUET</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">The source format of the external data</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="TableSchema">Table Schema</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#TableFieldConfiguration">Table Field Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Table field contains Datatype , Field Mode , Field Name , Field Type , Field Description to configure Table Schema</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="UserDefinedFunctionConfiguration">User Defined Function Configuration</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>FROM_URI</p>
</li>
<li>
<p>INLINE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Type of user-defined function. User defined functions can be provided inline as code blobs ({@link #INLINE}) or as a Google Cloud Storage URI ({@link #FROM_URI}).</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Content</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">If type is INLINE, it returns a code blob. If type is FROM_URI, it returns a Google Cloud Storage URI (e.g. gs://bucket/path).</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="UserAcl">User Acl</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Email</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User&#8217;s email address.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User Role</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OWNER</p>
</li>
<li>
<p>READER</p>
</li>
<li>
<p>WRITER</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Role specified to user</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="DomainAcl">Domain Acl</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Domain</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The domain name.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Role</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OWNER</p>
</li>
<li>
<p>READER</p>
</li>
<li>
<p>WRITER</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Role specified to domain</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ViewAcl">View Acl</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Project IDs must contain 6-63 lowercase letters, digits, or dashes. IDs must start with a letter and may not end with a dash.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Dataset identity. Dataset ID must be alphanumeric (plus underscores, dashes, and colons) and must be at most 1024 characters long.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Table IDs must be alphanumeric (plus underscores) and must be at most 1024 characters long.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Role</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OWNER</p>
</li>
<li>
<p>READER</p>
</li>
<li>
<p>WRITER</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Role specified to view</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="CopyJob">Copy Job</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source Tables</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of <a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Contains Table and Dataset name.
 It will copy the data from one or more source tables to a destination table.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Destination Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Data will get copied to a destination table.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Create Disposition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>CREATE_IF_NEEDED</p>
</li>
<li>
<p>CREATE_NEVER</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether the job is allowed to create new tables
 CREATE_IF_NEEDED :- Configures the job to create the table if it does not exist.
 CREATE_NEVER :- Configures the job to fail with a not-found error if the table does not exist.
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.CreateDisposition.html">Create Disposition</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Write Disposition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>WRITE_APPEND</p>
</li>
<li>
<p>WRITE_EMPTY</p>
</li>
<li>
<p>WRITE_TRUNCATE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Action that should occur if the destination table already exists.
 WRITE_APPEND :- Configures the job to append data to the table if it already exists.
 WRITE_EMPTY :- Configures the job to fail with a duplicate error if the table already exists.
 WRITE_TRUNCATE :- Configures the job to overwrite the table data if table already exists.
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.WriteDisposition.html">Write Disposition</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Kms Key Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">KMS key name for encryption configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ExtractJob">Extract Job</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Destination Uris</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The list of fully-qualified Google Cloud Storage URIs where the extracted table should be written.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The table to export.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Compression</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">the compression value of exported files.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field Delimiter</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The delimiter used between fields in the exported data.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Format</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The exported files format.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Print Header</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether an header row is printed with the result.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="LoadJob">Load Job</h3>
<table class="tableblock frame-all grid-all spread">
<colgroup>
<col style="width: 20%;">
<col style="width: 25%;">
<col style="width: 30%;">
<col style="width: 15%;">
<col style="width: 10%;">
</colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-middle">Field</th>
<th class="tableblock halign-left valign-middle">Type</th>
<th class="tableblock halign-left valign-middle">Description</th>
<th class="tableblock halign-left valign-middle">Default Value</th>
<th class="tableblock halign-left valign-middle">Required</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source Uris</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fully-qualified URIs that point to source data in Google Cloud Storage</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Destination Table</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableConfiguration">Table Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Destination table to load the data into</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Autodetect</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Automatic inference of the options and schema for CSV and JSON sources</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Format Option</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>AVRO</p>
</li>
<li>
<p>CSV</p>
</li>
<li>
<p>DATASTORE_BACKUP</p>
</li>
<li>
<p>GOOGLE_SHEETS</p>
</li>
<li>
<p>JSON</p>
</li>
<li>
<p>ORC</p>
</li>
<li>
<p>PARQUET</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source format and parsing options of the external data</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore Unknown Values</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">BigQuery should allow extra values that are not represented in the table
 schema</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Bad Records</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Maximum number of bad records that BigQuery can ignore when running the job</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Null Marker</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">String that represents a null value in a CSV file</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Destination Table Schema</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#TableSchema">Table Schema</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Schema for the destination table</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Create Disposition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>CREATE_IF_NEEDED</p>
</li>
<li>
<p>CREATE_NEVER</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether the job is allowed to create new tables
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.CreateDisposition.html">Create Disposition</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Kms Key Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Creates a EncryptionConfiguration object for KMS key name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Write Disposition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>WRITE_APPEND</p>
</li>
<li>
<p>WRITE_EMPTY</p>
</li>
<li>
<p>WRITE_TRUNCATE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Action that should occur if the destination table already exists
 <a href="https://googleapis.dev/java/google-cloud-clients/latest/com/google/cloud/bigquery/JobInfo.WriteDisposition.html">Write Disposition</a></p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow Fixed Relaxtion</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow relaxing a required field in the original schema to nullable when
 schema of the destination table to be updated as a side effect of the load
 job</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow Field Addition</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow adding a nullable field to the schema when schema of the destination
 table to be updated as a side effect of the load job</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
<div id="footer">
<div id="footer-text">
</div>
</div>