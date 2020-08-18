---
title: Elasticsearch Connector API Reference 
keywords: sample
sidebar: elasticsearch_connector_sidebar
permalink: es_v2_api_reference.html
folder: elasticsearch_connector
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
<p><a href="#config_http-connection">HTTP Connection</a> &#160;</p>
</li>
<li>
<p><a href="#config_https-connection">HTTPS Connection</a> &#160;</p>
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
<h5 id="config_http-connection">HTTP Connection</h5>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Host</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ElasticSearch instance host IP or DNS name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Port</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ElasticSearch instance port</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">9200</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Elasticsearch instance username. Keep this blank for anonymous user.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Password</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Elasticsearch instance password. Keep this blank for anonymous user.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
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
</tbody>
</table>
</div>
</div>
<div class="sect4">
<h5 id="config_https-connection">HTTPS Connection</h5>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Host</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ElasticSearch instance host IP or DNS name</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Port</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ElasticSearch instance port</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">9200</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">User Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Elasticsearch instance username. Keep this blank for anonymous user.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Password</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Elasticsearch instance password. Keep this blank for anonymous user.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type of the TrustStore</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">jks</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Path</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">TrustStore file path</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Password</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Trust store password</p></td>
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
<p><a href="#bulkOperation">Document - Bulk</a> &#160;</p>
</li>
<li>
<p><a href="#clearScroll">Search - Clear Scroll</a> &#160;</p>
</li>
<li>
<p><a href="#closeIndex">Index - Close</a> &#160;</p>
</li>
<li>
<p><a href="#createIndex">Index - Create</a> &#160;</p>
</li>
<li>
<p><a href="#deleteDocument">Document - Delete</a> &#160;</p>
</li>
<li>
<p><a href="#deleteIndex">Index - Delete</a> &#160;</p>
</li>
<li>
<p><a href="#getDocument">Document - Get</a> &#160;</p>
</li>
<li>
<p><a href="#indexDocument">Document - Index</a> &#160;</p>
</li>
<li>
<p><a href="#info">Elasticsearch - Info</a> &#160;</p>
</li>
<li>
<p><a href="#openIndex">Index - Open</a> &#160;</p>
</li>
<li>
<p><a href="#search">Search - Query</a> &#160;</p>
</li>
<li>
<p><a href="#searchScroll">Search - Scroll</a> &#160;</p>
</li>
<li>
<p><a href="#searchUsingJsonData">Search - JSON Query</a> &#160;</p>
</li>
<li>
<p><a href="#updateDocument">Document - Update</a> &#160;</p>
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
<h3 id="bulkOperation">Document - Bulk</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:bulk-operation&gt;</code></p>
</div>
<div class="paragraph">
<p>
Bulk operation makes it possible to perform many create, index, delete and update operations in a single API call.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index name on which bulk operation performed.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">File</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the JSON file path</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Text</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the JSON string</p></td>
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
<p><a href="#Response">Response</a></p>
</div></div></td>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="clearScroll">Search - Clear Scroll</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:clear-scroll&gt;</code></p>
</div>
<div class="paragraph">
<p>
Clear scroll operation release search contexts as soon as they are not necessary anymore. This happens automatically when the scroll expires
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll IDs</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of scroll identifiers to clear</p></td>
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
<p><a href="#ClearScrollResponse">Clear Scroll Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="closeIndex">Index - Close</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:close-index&gt;</code></p>
</div>
<div class="paragraph">
<p>
A closed index has almost no overhead. It is used to close an Index. If you want to keep your data but save resources (memory/CPU), a good alternative to deleting an index is to close them.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The index to close</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout (Seconds)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to wait for the all the nodes to acknowledge if the index is closed</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Mater Node Timeout (Seconds)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to connect to the master node</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indices Opt</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#IndexOptions">Index Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">IndicesOptions controls how unavailable indices are resolved and how wildcard expressions are expanded</p></td>
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
<p><a href="#CloseIndexResponse">Close Index Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="createIndex">Index - Create</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:create-index&gt;</code></p>
</div>
<div class="paragraph">
<p>
The createIndex operation allows to instantiate an index.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The index to create</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#IndexConfiguration">Index Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The index configuration</p></td>
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
<p><a href="#CreateIndexResponse">Create Index Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="deleteDocument">Document - Delete</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:delete-document&gt;</code></p>
</div>
<div class="paragraph">
<p>
Delete Document operation allows to delete a typed JSON document from a specific index based on its id
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name of the index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Document Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ID of the document</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Delete Document Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#DocumentConfiguration">Document Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Delete document configuration</p></td>
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
<p><a href="#DeleteResponse">Delete Response</a></p>
</div></div></td>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="deleteIndex">Index - Delete</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:delete-index&gt;</code></p>
</div>
<div class="paragraph">
<p>
The Delete index operation allows to delete an existing index.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The index to delete</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout (Seconds)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to wait for the all the nodes to acknowledge the index deletion.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Mater Node Timeout (Seconds)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to connect to the master node.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indices Opts</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#IndexOptions">Index Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">IndicesOptions controls how unavailable indices are resolved and how wildcard expressions are expanded</p></td>
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
<p><a href="#AcknowledgedResponse">Acknowledged Response</a></p>
</div></div></td>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="getDocument">Document - Get</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:get-document&gt;</code></p>
</div>
<div class="paragraph">
<p>
Get Document operation allows to get a typed JSON document from the index based on its id.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name of the index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Document Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ID of the document</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Get Document Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#GetDocumentConfiguration">Get Document Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Get Document configuration</p></td>
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
<p><a href="#GetResponse">Get Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="indexDocument">Document - Index</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:index-document&gt;</code></p>
</div>
<div class="paragraph">
<p>
Index Document operation adds or updates a typed JSON document in a specific index, making it searchable.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name of the index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Document Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ID of the document</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Document Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#IndexDocumentConfiguration">Index Document Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Document Configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">JSON Input file path</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the JSON file path</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Document Source</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the Document source</p></td>
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
<p><a href="#IndexResponse">Index Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="info">Elasticsearch - Info</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:info&gt;</code></p>
</div>
<div class="paragraph">
<p>
Retrieves the cluster information.
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
<p><a href="#MainResponse">Main Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="openIndex">Index - Open</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:open-index&gt;</code></p>
</div>
<div class="paragraph">
<p>
Open Index operation allow to open an index.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The index to open</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout (Seconds)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to wait for the all the nodes to acknowledge the index is opened. It is the time to wait for an open index to become available to elasticsearch.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Mater Node Timeout (Seconds)</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to connect to the master node</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Wait for Active Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The number of active shard copies to wait for</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indices Opts</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#IndexOptions">Index Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">IndicesOptions controls how unavailable indices are resolved and how wildcard expressions are expanded</p></td>
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
<p><a href="#OpenIndexResponse">Open Index Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="search">Search - Query</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:search&gt;</code></p>
</div>
<div class="paragraph">
<p>
The search operation returns search hits that match the query defined in the request.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#QueryConfiguration">Query Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Elasticsearch query configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search Source</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#SearchSourceConfiguration">Search Source Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search source configuration to control the search behavior.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search Config</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#SearchRequestOptionalConfiguration">Search Request Optional Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Some optional parameters for search request configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indices</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Restricts the search request to one or more indices.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>DFS_QUERY_THEN_FETCH</p>
</li>
<li>
<p>QUERY_THEN_FETCH</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The type of the search operation to perform</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search the document using routing</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll Interval Time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll interval time keep the search context alive(minutes). If value is non-zero, scroll search is initiated.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Preference</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The preference to execute the search. Use the preference parameter e.g. to execute the search to prefer local shards. The default is to randomize across shards.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indices Options</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#IndexOptions">Index Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">It controls how unavailable indices are resolved and how wildcard expressions are expanded</p></td>
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
<p><a href="#SearchResponse">Search Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="searchScroll">Search - Scroll</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:search-scroll&gt;</code></p>
</div>
<div class="paragraph">
<p>
The Search Scroll operation is used to retrieve a large number of results from a search request.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll identifier returned in last scroll/search request</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Keep alive time</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll time interval (in seconds) to keep the search context alive</p></td>
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
<p><a href="#SearchResponse">Search Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="searchUsingJsonData">Search - JSON Query</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:search-using-json-data&gt;</code></p>
</div>
<div class="paragraph">
<p>
This search operation returns search hits based on JSON data.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Restricts the search request to an index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">File</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the JSON file path</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Text</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the JSON string</p></td>
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
<p><a href="#Response">Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect2">
<h3 id="updateDocument">Document - Update</h3>
<div class="paragraph">
<p><code>&lt;elasticsearch:update-document&gt;</code></p>
</div>
<div class="paragraph">
<p>
Update Document operation allows to update a document based on a script provided.
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name of the index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Document Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">ID of the document</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Update Document Configuration</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#UpdateDocumentConfiguration">Update Document Configuration</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Update document configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">JSON Input file path</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the JSON file path</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Document Source</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Provide the Document source</p></td>
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
<p><a href="#UpdateResponse">Update Response</a></p>
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
<p>ELASTICSEARCH:EXECUTION &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:CONNECTIVITY &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:RETRY_EXHAUSTED &#160;</p>
</li>
<li>
<p>ELASTICSEARCH:OPERATION_FAILED &#160;</p>
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
<h3 id="Response">Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Headers</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of org.apache.http.Header</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">All the response headers.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Entity</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The response body available (as String), null otherwise</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Host</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>org.apache.http.HttpHost</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The node that returned this response. </td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Request Line</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>org.apache.http.RequestLine</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The request line that generated this response</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Status Line</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>org.apache.http.StatusLine</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The status line of the current response</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Warnings</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">A list of all warning headers returned in the response</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="ClearScrollResponse">Clear Scroll Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Freed</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The number of search contexts that were freed. If this is 0 the assumption can be made, that the scroll id specified in the request did not exist. (never existed, was expired, or completely consumed)</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Succeeded</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Whether the attempt to clear a scroll was successful.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="CloseIndexResponse">Close Index Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Whether the response is acknowledged or not</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indices</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Object</p>
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>exception</p>
</li>
<li>
<p>index</p>
</li>
<li>
<p>shards</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Indices</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shards Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Returns true if the requisite number of shards were started before returning from the index creation operation.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="IndexOptions">Index Options</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore Unavailable</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether specified concrete indices should be ignored when unavailable (missing or closed).</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow No Indices</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether to ignore if a wildcard expression resolves to no concrete indices.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Expand Wildcards Open</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether wildcard expressions should get expanded to open indices.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Expand Wildcards Closed</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether wildcard expressions should get expanded to closed indices.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow Aliases To Multiple Indices</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether aliases pointing to multiple indices are allowed.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Forbid Closed Indices</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether execution on closed indices is allowed.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore Aliases</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether aliases should be ignored (when resolving a wildcard).</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore Throttled</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether indices that are marked as throttled should be ignored.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="CreateIndexResponse">Create Index Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Whether the response is acknowledged or not.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shards Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Returns true if the requisite number of shards were started before returning from the index creation operation.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="IndexConfiguration">Index Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Settings</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Settings for the index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Settings JSON File</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Path of the JSON file which specifies Index Settings.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Mappings JSON File</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Path of the JSON file which specifies Index Mapping.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index Alias</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The alias of the index</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source JSON File</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Path of the JSON file. The whole source including all of its sections (mappings, settings and aliases) can be provided in this json file.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout In Sec</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to wait for the all the nodes to acknowledge the index creation.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Master Node Timeout In Sec</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout in seconds to connect to the master node.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Wait For Active Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The number of active shard copies to wait for before the create index.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="DeleteResponse">Delete Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Forced Refresh</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Did this request force a refresh? Requests that set WriteRequest.setRefreshPolicy(RefreshPolicy) to WriteRequest.RefreshPolicy.IMMEDIATE will always return true for this.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The id of the document changed.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The index the document was changed in.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Primary Term</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The primary term for this change.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Result</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The change that occurred to the document, primarily used to communicate the type of operation that occurred</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Seq No</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The sequence number assigned for this change.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>id</p>
</li>
<li>
<p>index</p>
</li>
<li>
<p>indexName</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">The exact shard the document was changed in.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>failed</p>
</li>
<li>
<p>failures</p>
</li>
<li>
<p>successful</p>
</li>
<li>
<p>total</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Shard Info</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Type of the doc</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The current version of the doc.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="DocumentConfiguration">Document Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version number of the indexed document. It will control the version of the document the operation is intended to be executed against.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>EXTERNAL</p>
</li>
<li>
<p>EXTERNAL_GTE</p>
</li>
<li>
<p>INTERNAL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version type: internal, external, external_gte</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing is used to determine in which shard the document will reside in</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout In Sec</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time in seconds to wait for primary shard to become available</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh Policy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>IMMEDIATE</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>WAIT_UNTIL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh policy is used to control when changes made by the requests are made visible to search. Option for refresh policy A) true : Refresh the relevant primary
 and replica shards (not the whole index) immediately after the operation occurs, so that the updated document appears in search results immediately. B) wait_for :
 Wait for the changes made by the request to be made visible by a refresh before replying. This doesn�t force an immediate refresh, rather, it waits for a
 refresh to happen. C) false (default) : Take no refresh related actions. The changes made by this request will be made visible at some point after the request
 returns.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="AcknowledgedResponse">Acknowledged Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Whether the response is acknowledged or not.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="GetResponse">Get Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The id of the document.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The index the document was fetched from.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Primary Term</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The primary term of the last primary that has changed this document, if found.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Seq No</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The sequence number assigned to the last operation that has changed this document, if found.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Source As String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The source of the document (as a string).</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The type of the document.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The version of the doc.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Found</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Does the document exists.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="GetDocumentConfiguration">Get Document Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fetch Source Context</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p><a href="#DocumentFetchSourceOptions">Document Fetch Source Options</a></p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable or disable source retrieval</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing is used to determine in which shard the document will reside in</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Preference</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Preference value</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Realtime</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set realtime flag</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Perform a refresh before retrieving the document</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version number of the indexed document</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>EXTERNAL</p>
</li>
<li>
<p>EXTERNAL_GTE</p>
</li>
<li>
<p>INTERNAL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version type: internal, external, external_gte</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="DocumentFetchSourceOptions">Document Fetch Source Options</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fetch Source</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Fetch the source of the search document</td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Include Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">List of the field that are included into the document source.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Exclude Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">List of the field that are excluded from the document source.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="IndexResponse">Index Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Forced Refresh</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Did this request force a refresh? Requests that set WriteRequest.setRefreshPolicy(RefreshPolicy) to WriteRequest.RefreshPolicy.IMMEDIATE will always return true for this.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The id of the document changed.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The index the document was changed in.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Primary Term</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The primary term for this change.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Result</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The change that occurred to the document, primarily used to communicate the type of operation that occurred</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Seq No</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The sequence number assigned for this change.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>id</p>
</li>
<li>
<p>index</p>
</li>
<li>
<p>indexName</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">The exact shard the document was changed in.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>failed</p>
</li>
<li>
<p>failures</p>
</li>
<li>
<p>successful</p>
</li>
<li>
<p>total</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Shard Info</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Type of the doc</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The current version of the doc.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="IndexDocumentConfiguration">Index Document Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Operation Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>CREATE</p>
</li>
<li>
<p>DELETE</p>
</li>
<li>
<p>INDEX</p>
</li>
<li>
<p>UPDATE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type of the operation. When create type is used, the index operation will fail if a document by that id already exists in the index.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Pipeline</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Name of the ingest pipeline to be executed before indexing the document</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version number of the indexed document. It will control the version of the document the operation is intended to be executed against.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>EXTERNAL</p>
</li>
<li>
<p>EXTERNAL_GTE</p>
</li>
<li>
<p>INTERNAL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version type: internal, external, external_gte</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing is used to determine in which shard the document will reside in</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout In Sec</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time in seconds to wait for primary shard to become available</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh Policy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>IMMEDIATE</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>WAIT_UNTIL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh policy is used to control when changes made by the requests are made visible to search. Option for refresh policy A) true : Refresh the relevant primary
 and replica shards (not the whole index) immediately after the operation occurs, so that the updated document appears in search results immediately. B) wait_for :
 Wait for the changes made by the request to be made visible by a refresh before replying. This doesn�t force an immediate refresh, rather, it waits for a
 refresh to happen. C) false (default) : Take no refresh related actions. The changes made by this request will be made visible at some point after the request
 returns.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="MainResponse">Main Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Cluster Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Name of the cluster.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Cluster Uuid</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">UUID of the cluster.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Node Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Node Name</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Tagline</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Tagline</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>number</p>
</li>
<li>
<p>build_flavor</p>
</li>
<li>
<p>build_type</p>
</li>
<li>
<p>build_hash</p>
</li>
<li>
<p>build_date</p>
</li>
<li>
<p>build_snapshot</p>
</li>
<li>
<p>lucene_version</p>
</li>
<li>
<p>minimum_wire_compatibility_version</p>
</li>
<li>
<p>minimum_index_compatibility_version</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Version of elasticsearch instance.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="OpenIndexResponse">Open Index Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Whether the response is acknowledged or not.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shards Acknowledged</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Returns true if the requisite number of shards were started before returning from the index creation operation.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="SearchResponse">Search Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Aggregations</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Any</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Represents a set of computed Aggregation.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Clusters</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>skipped</p>
</li>
<li>
<p>successful</p>
</li>
<li>
<p>total</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Returns info about what clusters the search was executed against.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Failed Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The failed number of shards the search was executed on.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Hits</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Array of Array of Any</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The search hits.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Num Reduce Phases</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The number of reduce phases applied to obtain this search response</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Profile Results</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Any</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">If profiling was enabled, this returns an object containing the profile results from each shard.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scroll Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">If scrolling was enabled, the scroll id that can be used to continue scrolling.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Failures</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Any</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The failures that occurred during the search.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Skipped Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The number of shards skipped due to pre-filtering</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Successful Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The successful number of shards the search was executed on.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Suggest</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of Array of Array of Any</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Top level suggest result, containing the result for each suggestion.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timed Out</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Has the search operation timed out.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Took</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>days</p>
</li>
<li>
<p>daysFrac</p>
</li>
<li>
<p>hours</p>
</li>
<li>
<p>hoursFrac</p>
</li>
<li>
<p>micros</p>
</li>
<li>
<p>microsFrac</p>
</li>
<li>
<p>millis</p>
</li>
<li>
<p>millisFrac</p>
</li>
<li>
<p>minutes</p>
</li>
<li>
<p>minutesFrac</p>
</li>
<li>
<p>nanos</p>
</li>
<li>
<p>seconds</p>
</li>
<li>
<p>secondsFrac</p>
</li>
<li>
<p>stringRep</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">How long the search took.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Total Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The total number of shards the search was executed on.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="QueryConfiguration">Query Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>One of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="#MatchQuery">Match Query</a></p>
</li>
<li>
<p><a href="#MultiMatchQuery">Multi Match Query</a></p>
</li>
<li>
<p><a href="#MatchAllQuery">Match All Query</a></p>
</li>
<li>
<p><a href="#MatchPhraseQuery">Match Phrase Query</a></p>
</li>
<li>
<p><a href="#MatchPhrasePrefixQuery">Match Phrase Prefix Query</a></p>
</li>
<li>
<p><a href="#QueryStringQuery">Query String Query</a></p>
</li>
<li>
<p><a href="#SimpleQueryString">Simple Query String</a></p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Different types of Elasticsearch query configuration</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="SearchSourceConfiguration">Search Source Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">From</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Retrieve search result from a certain offset</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The number of search hits to return</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">10</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time (in minutes) allowed to finish the search operation</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sort Order</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>ASC</p>
</li>
<li>
<p>DESC</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The sort order of search result using default field (_score).</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sort By Field Name</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field name to sort the search result</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Profile</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable the profiling to the execution of search queries</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Explain</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Explain the execution of search queries</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Terminate After</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The maximum number of documents to collect for each shard</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Track Scores</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable the search source tracking</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Track Total Hits</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable the total hits tracking i.e whether the total hit count for the query should be tracked.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Track Total Hits Up To</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The total hit count that should be tracked.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether the document&#8217;s version will be included in the search hits.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Minimum Score</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The minimum score below which docs will be filtered out.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Seq No And Primary Term</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether search hits be returned with the sequence number and primary term of the last modification of the document.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fetch Source</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fetch the source of the search document</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Include Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of the field that are included into the document source</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Exclude Fields</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of the field that are excluded from the document source</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="SearchRequestOptionalConfiguration">Search Request Optional Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow Partial Search Results</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets if this request should allow partial results.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Request Cache</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets if this request should use the request cache or not.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Batched Reduce Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The number of shard results that should be reduced at once on the coordinating node.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">2</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ccs Minimize Roundtrips</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Whether network round-trips should be minimized when executing cross-cluster search requests.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Concurrent Shard Requests</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The number of shard requests that should be executed concurrently on a single node.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Pre Filter Shard Size</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A threshold that enforces a pre-filter roundtrip to pre-filter search shards based on query rewriting if the number of shards the search request expands to exceeds the
 threshold.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="UpdateResponse">Update Response</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Forced Refresh</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Did this request force a refresh? Requests that set WriteRequest.setRefreshPolicy(RefreshPolicy) to WriteRequest.RefreshPolicy.IMMEDIATE will always return true for this.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The id of the document changed.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Index</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The index the document was changed in.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Primary Term</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The primary term for this change.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Result</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The change that occurred to the document, primarily used to communicate the type of operation that occurred</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Seq No</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The sequence number assigned for this change.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Id</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>id</p>
</li>
<li>
<p>index</p>
</li>
<li>
<p>indexName</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">The exact shard the document was changed in.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Shard Info</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>failed</p>
</li>
<li>
<p>failures</p>
</li>
<li>
<p>successful</p>
</li>
<li>
<p>total</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Shard Info</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">Type of the doc</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Version</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle">The current version of the doc.</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Get Result</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object, with fields:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>id</p>
</li>
<li>
<p>index</p>
</li>
<li>
<p>primaryTerm</p>
</li>
<li>
<p>seqNo</p>
</li>
<li>
<p>source</p>
</li>
<li>
<p>type</p>
</li>
<li>
<p>version</p>
</li>
<li>
<p>exists</p>
</li>
<li>
<p>fields</p>
</li>
<li>
<p>documentFields</p>
</li>
<li>
<p>metadataFields</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle">Result details</td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="UpdateDocumentConfiguration">Update Document Configuration</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Retry On Conflict</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">How many times to retry the update operation if the document to update has been changed by another operation between the get and indexing phases of the update operation</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fetch Source</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable or disable source retrieval</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If Seq No</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If set, only perform this update request if the document was last modification was assigned this sequence number.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If Primary Term</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If set, only perform this update request if the document was last modification was assigned this primary term.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Detect Noop</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable or disable the noop detection</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Scripted Upsert</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indicate that the script must run regardless of whether the document exists or not</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Doc As Upsert</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Indicate that the partial document must be used as the upsert document if it does not exist yet.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Wait For Active Shards</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The number of shard copies that must be active before proceeding with the update operation.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Routing is used to determine in which shard the document will reside in</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Timeout In Sec</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time in seconds to wait for primary shard to become available</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh Policy</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>IMMEDIATE</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>WAIT_UNTIL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Refresh policy is used to control when changes made by the requests are made visible to search. Option for refresh policy A) true : Refresh the relevant primary
 and replica shards (not the whole index) immediately after the operation occurs, so that the updated document appears in search results immediately. B) wait_for :
 Wait for the changes made by the request to be made visible by a refresh before replying. This doesn�t force an immediate refresh, rather, it waits for a
 refresh to happen. C) false (default) : Take no refresh related actions. The changes made by this request will be made visible at some point after the request
 returns.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="MatchQuery">Match Query</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Restrict the search request to field</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search text string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzziness</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>AUTO</p>
</li>
<li>
<p>ZERO</p>
</li>
<li>
<p>ONE</p>
</li>
<li>
<p>TWO</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable fuzzy matching on the match query</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Rewrite</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Rewrite</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Transpositions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow the fuzzy transpositions match</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Prefix Length</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Prefix length option on the match query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Expansions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max expansion to control the fuzzy process of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">50</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Operator</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OR</p>
</li>
<li>
<p>AND</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set the match query operator</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Lenient</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore exceptions caused by data-type mismatches</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Zero Terms Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>ALL</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>NULL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set the zero terms query option</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The analyzer to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Auto Generate Synonyms Phrase Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable the auto generate synonyms phrase</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Minimum Should Match</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set minimum should match with possible value using integer and percentage.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="MultiMatchQuery">Multi Match Query</h3>
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
<p>Array of String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Restrict the search request to list of field</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Slop</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The phrase slop if evaluated to a phrase query type.</p></td>
<td class="tableblock halign-left valign-middle"></td>
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
<p>BEST_FIELDS</p>
</li>
<li>
<p>CROSS_FIELDS</p>
</li>
<li>
<p>MOST_FIELDS</p>
</li>
<li>
<p>PHRASE</p>
</li>
<li>
<p>PHRASE_PREFIX</p>
</li>
<li>
<p>BOOL_PREFIX</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Type of the multi match query is executed internally</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Tie Breaker</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The tie breaker parameter used to select field in a group of field based on score
</p><p class="tableblock"> 0.0 - Take the single best score out of multiple field
</p><p class="tableblock"> 1.0 - Add together the scores of the multiple field
</p><p class="tableblock"> 0.0 &lt; n &lt; 1.0 - Take the single best score plus tie_breaker multiplied by each of the scores from other matching fields.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search text string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzziness</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>AUTO</p>
</li>
<li>
<p>ZERO</p>
</li>
<li>
<p>ONE</p>
</li>
<li>
<p>TWO</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable fuzzy matching on the match query</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Rewrite</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Rewrite</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Transpositions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow the fuzzy transpositions match</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Prefix Length</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Prefix length option on the match query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Expansions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max expansion to control the fuzzy process of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">50</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Operator</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OR</p>
</li>
<li>
<p>AND</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set the match query operator</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Lenient</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Ignore exceptions caused by data-type mismatches</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Zero Terms Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>ALL</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>NULL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set the zero terms query option</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The analyzer to use.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Auto Generate Synonyms Phrase Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable the auto generate synonyms phrase</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Minimum Should Match</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set minimum should match with possible value using integer and percentage.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="MatchAllQuery">Match All Query</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="MatchPhraseQuery">Match Phrase Query</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Zero Terms Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>ALL</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>NULL</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query to use in case no query terms are available, e.g. after analysis removed them.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Restrict the search request to field</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search text string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The analyzer name used to analyze the query string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Slop</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A slop factor for phrase queries</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="MatchPhrasePrefixQuery">Match Phrase Prefix Query</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Expansions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Number of suffixes the last term will be expanded</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">50</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Field</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Restrict the search request to field</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Search text string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The analyzer name used to analyze the query string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Slop</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A slop factor for phrase queries</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="QueryStringQuery">Query String Query</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow Leading Wildcard</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow first wildcard (* or ?) in query string</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default Field</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The default field for query terms if no prefix field is specified.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable Position Increments</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set to true to enable position increments in result queries.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Escape</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Allow escape in query string</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Rewrite</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy rewrite.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Max Determinized States</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Protects against too-difficult regular expression queries.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Phrase Slop</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the default slop for phrases. If zero, then exact phrase matches are required.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Quote Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The optional analyzer used to analyze the query string for phrase searches.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Rewrite</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The optional analyzer used to analyze the query string for phrase searches.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Tie Breaker</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The disjunction max tie breaker for multi fields</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Time Zone</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">In case of date field, we can adjust the from/to fields using a timezone</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The actual query to be parsed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fields And Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of the field name and associated field boost</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The analyzer name used to analyze the query string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyze Wildcard</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyze the wildcards terms from the query string</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Auto Generate Synonyms Phrase Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable auto generated synonyms phrase queries</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default Operator</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OR</p>
</li>
<li>
<p>AND</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The default operator used if no explicit query operator is specified</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Max Expansions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Controls the number of terms fuzzy queries will expand to.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">50</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Prefix Length</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set the prefix length for fuzzy queries</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Transpositions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set to false to disable fuzzy transpositions</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Lenient</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If set to true will cause format based failures (like providing text to a numeric field) to be ignored.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Minimum Should Match</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set minimum should match with possible value using integer and percentage.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Quote Field Suffix</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A suffix to append to fields for quoted parts of the query string.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
</tbody>
</table>
</div>
<div class="sect2">
<h3 id="SimpleQueryString">Simple Query String</h3>
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
<td class="tableblock halign-left valign-middle"><p class="tableblock">Simple Query String Flag</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>ALL</p>
</li>
<li>
<p>AND</p>
</li>
<li>
<p>ESCAPE</p>
</li>
<li>
<p>FUZZY</p>
</li>
<li>
<p>NEAR</p>
</li>
<li>
<p>NONE</p>
</li>
<li>
<p>NOT</p>
</li>
<li>
<p>OR</p>
</li>
<li>
<p>PHRASE</p>
</li>
<li>
<p>PRECEDENCE</p>
</li>
<li>
<p>PREFIX</p>
</li>
<li>
<p>SLOP</p>
</li>
<li>
<p>WHITESPACE</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Specify which parsing flag should be enabled</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Query String</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The actual query to be parsed</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">x</p></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fields And Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Object</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">List of the field name and associated field boost</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyzer</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The analyzer name used to analyze the query string</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyze Wildcard</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Analyze the wildcards terms from the query string</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Auto Generate Synonyms Phrase Query</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Enable auto generated synonyms phrase queries</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Boost</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Sets the boost value of the query</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">1.0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Default Operator</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Enumeration, one of:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>OR</p>
</li>
<li>
<p>AND</p>
</li>
</ul>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">The default operator used if no explicit query operator is specified</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Max Expansions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Controls the number of terms fuzzy queries will expand to.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">50</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Prefix Length</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Number</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set the prefix length for fuzzy queries</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">0</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Fuzzy Transpositions</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set to false to disable fuzzy transpositions</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">true</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Lenient</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>Boolean</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">If set to true will cause format based failures (like providing text to a numeric field) to be ignored.</p></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">false</p></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Minimum Should Match</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Set minimum should match with possible value using integer and percentage.</p></td>
<td class="tableblock halign-left valign-middle"></td>
<td class="tableblock halign-left valign-middle"></td>
</tr>
<tr>
<td class="tableblock halign-left valign-middle"><p class="tableblock">Quote Field Suffix</p></td>
<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
<p>String</p>
</div></div></td>
<td class="tableblock halign-left valign-middle"><p class="tableblock">A suffix to append to fields for quoted parts of the query string.</p></td>
<td class="tableblock halign-left valign-middle"></td>
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