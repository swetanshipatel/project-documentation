---
title: Braintree Connector API Reference 
keywords: sample
sidebar: braintree_connector_sidebar
permalink: braintree-api-doc.html
folder: braintree_connector
---
  <div id="content">
    <div class="sect1">
      <h2 id="_configurations">Configurations</h2>
      <div class="sectionbody">
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Name</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name for this configuration. Connectors reference the configuration
                      with this name.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Connection</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#config_connection">Connection</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The connection types that can be provided to this configuration.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Expiration Policy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#ExpirationPolicy">Expiration Policy</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configures the minimum amount of time that a dynamic configuration
                      instance can remain idle before the runtime considers it eligible
                      for expiration. This does not mean that the platform will expire
                      the instance at the exact moment that it becomes eligible.
                      The runtime will actually purge the instances when it sees
                      it fit.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="sect3">
            <h4 id="_connection_types">Connection Types</h4>
            <div class="sect4">
              <h5 id="config_connection">Connection</h5>
                <p>This class (as it's name implies) provides connection instances and the funcionality
                  to disconnect and validate those connections. All connection related parameters (values required in order to
                    create a connection) must be declared in the connection providers.</p>
                 <p> This particular example is a PoolingConnectionProvider which
                      declares that connections resolved by this provider will be
                      pooled and reused.</p>
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
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Merchant ID</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <div>
                          <div class="paragraph">
                            <p>String</p>
                          </div>
                        </div>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">The merchant account ID</p>
                      </td>
                      <td class="tableblock halign-left valign-middle"></td>
                      <td class="tableblock halign-center valign-middle">
                        <p class="tableblock"><strong>x</strong>&#160;</p>
                      </td>
                    </tr>
                    <tr>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Public Key</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <div>
                          <div class="paragraph">
                            <p>String</p>
                          </div>
                        </div>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Associated public key with merchant account</p>
                      </td>
                      <td class="tableblock halign-left valign-middle"></td>
                      <td class="tableblock halign-center valign-middle">
                        <p class="tableblock"><strong>x</strong>&#160;</p>
                      </td>
                    </tr>
                    <tr>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Private Key</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <div>
                          <div class="paragraph">
                            <p>String</p>
                          </div>
                        </div>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Associated private key with merchant account</p>
                      </td>
                      <td class="tableblock halign-left valign-middle"></td>
                      <td class="tableblock halign-center valign-middle">
                        <p class="tableblock"><strong>x</strong>&#160;</p>
                      </td>
                    </tr>
                    <tr>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Environment</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <div>
                          <div class="paragraph">
                            <p>String</p>
                          </div>
                        </div>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Operation execution environment. Examples: sandbox, development,
                          qa, production</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">production</p>
                      </td>
                      <td class="tableblock halign-center valign-middle">
                        <p class="tableblock">&#160;</p>
                      </td>
                    </tr>
                    <tr>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Reconnection</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <div>
                          <div class="paragraph">
                            <p><a href="#Reconnection">Reconnection</a></p>
                          </div>
                        </div>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">When the application is deployed, a connectivity test is
                          performed on all connectors. If set to true, deployment
                          will fail if the test doesn't pass after exhausting the
                          associated reconnection strategy</p>
                      </td>
                      <td class="tableblock halign-left valign-middle"></td>
                      <td class="tableblock halign-center valign-middle">
                        <p class="tableblock">&#160;</p>
                      </td>
                    </tr>
                    <tr>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Pooling Profile</p>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <div>
                          <div class="paragraph">
                            <p><a href="#PoolingProfile">Pooling Profile</a></p>
                          </div>
                        </div>
                      </td>
                      <td class="tableblock halign-left valign-middle">
                        <p class="tableblock">Characteristics of the connection pool</p>
                      </td>
                      <td class="tableblock halign-left valign-middle"></td>
                      <td class="tableblock halign-center valign-middle">
                        <p class="tableblock">&#160;</p>
                      </td>
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
                  <p><a href="#createCustomer">Customer - Create</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#createPaymentMethod">PaymentMethod - Create</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#deleteCustomer">Customer - Delete</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#deletePaymentMethod">PaymentMethod - Delete</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#findCustomer">Customer - Find</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#findPaymentMethod">PaymentMethod - Find</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#findTransaction">Transaction - Find</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#getClientToken">Client Token - Get</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#sale">Transaction - Sale</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#searchCustomer">Customer - Search</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#searchTransaction">Transaction - Search</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#submitForPartialSettlement">Transaction - Submit For Partial Settlement</a>                    &#160;</p>
                </li>
                <li>
                  <p><a href="#submitForSettlement">Transaction - Submit For Settlement</a>                    &#160;</p>
                </li>
                <li>
                  <p><a href="#updateCustomer">Customer - Update</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#updatePaymentMethod">PaymentMethod - Update</a> &#160;</p>
                </li>
                <li>
                  <p><a href="#voidTransaction">Transaction - Void</a> &#160;</p>
                </li>
				<li>
                  <p><a href="#refundTransaction">Transaction - Refund</a> &#160;</p>
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
          <h3 id="createCustomer">Customer - Create</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:create-customer&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Operation to create customer. You can create a customer by itself, with a payment
              method, or with a credit card with a billing address.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentCardInformation">Payment Card Information</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A credit or debit payment method details.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Options</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentMethodOptions">Payment Method Options</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment method options.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Address</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/response/address/java">Address</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A billing address associated with a specific credit card. The
                      maximum number of addresses per customer is 50.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">ID</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A string value that will represent this specific customer in
                      your Vault. 36 character maximum; must be unique within your
                      Vault; valid characters are letters, numbers, -, and _; the
                      words "all" and "new" currently can't be used. If not specified
                      on creation, the gateway will generate an alphanumeric ID that
                      can be accessed on the result. The generated IDs will never
                      start with a leading 0 and are case insensitive.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">First Name</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The first name. The first name value must be less than or equal
                      to 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Last Name</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The last name. The last name value must be less than or equal
                      to 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Email</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Email address composed of ASCII characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Phone</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Phone number. Maximum 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">fax</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Fax number. Maximum 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Company</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Company name. Maximum 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Website</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Website URL. Must be less than or equal to 255 characters. Website
                      must be well-formed. The URL scheme is optional.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Token</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An alphanumeric value that references a specific payment method
                      stored in your Vault. Must be less than or equal to 36 characters.
                      If using a custom integration, you can specify what you want
                      the token to be. If not specified, the gateway will generate
                      one that can be accessed on the result.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Nonce</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">One-time-use reference to payment information provided by your
                      customer, such as a credit card or PayPal account. When passed
                      on customer create, it creates a payment method associated
                      with the new customer.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Device Data</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer device information. Pass this value only if you have
                      Advanced Fraud Tools enabled and are adding credit card data
                      to your Vault. Be sure to provide the full string received
                      from the Braintree.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Custom Fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Object</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A collection of custom field/value pairs. Fields and values must
                      be less than 255 characters. You must <a href="https://articles.braintreepayments.com/control-panel/custom-fields?&_ga=1.28588988.1497859415.1565702545#creating-a-custom-field">set up each custom field in the Control Panel</a>                      prior to passing it with a request.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Device Session Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Fraud Merchant Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Risk Data</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/request/customer/create/java#risk_data">RiskData</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer device information, which is sent directly to supported
                      processors for fraud analysis. These fields are automatically
                      populated if using <a href="https://developers.braintreepayments.com/guides/advanced-fraud-tools/overview">Advanced Fraud Tools</a>.
                      Currently only available when processing American Express via
                      Amex Direct.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CUSTOMER_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="createPaymentMethod">PaymentMethod - Create</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:create-payment-method&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Operation to create payment method for existing customers
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The customer's unique Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Nonce</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The payment method nonce</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentCardInformation">Payment Card Information</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A credit or debit payment method details.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Options</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentMethodOptions">Payment Method Options</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment method options.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Billing Address</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/response/address/java">Address</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A billing address associated with a specific credit card. The
                      maximum number of addresses per customer is 50.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:PAYMENT_METHOD_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="deleteCustomer">Customer - Delete</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:delete-customer&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Operation to delete customer. You can delete a customer using its ID. When a customer
              is deleted, all associated payment methods are also deleted, and all
              associated recurring billing subscriptions are canceled.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The customer Id to delete.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CUSTOMER_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="deletePaymentMethod">PaymentMethod - Delete</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:delete-payment-method&gt;</code></p>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Token</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The alphanumeric value that references a specific payment method
                      stored in your Vault.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Revoke All grants</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Boolean</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">When true, all grants of the payment method to other merchants
                      will automatically be revoked. The default value is false.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">false</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:PAYMENT_METHOD_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="findCustomer">Customer - Find</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:find-customer&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Find operation look up a single customer using its ID. If the customer can't be found,
              it will throw a NotFoundException.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The customer Id to find.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#Customer">[Customer]</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CUSTOMER_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="findPaymentMethod">PaymentMethod - Find</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:find-payment-method&gt;</code></p>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Token</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The alphanumeric value that references a specific payment method
                      stored in your Vault.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentMethod">[PaymentMethod]</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:PAYMENT_METHOD_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="findTransaction">Transaction - Find</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:find-transaction&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Find Transaction operation returns the transaction with the specified Transaction
              Id
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Transaction Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The unique transaction identifier.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/response/transaction/java">transaction</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="getClientToken">Client Token - Get</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:get-client-token&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Operation to generate token which contains all authorization and configuration information.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Client Token Options Request</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#ClientTokenRequestOptions">Client Token Request Options</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Generate token request options.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Output Mime Type</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The mime type of the payload that this operation outputs.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:CONNECTION_FAILED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:FAILED_TO_GENERATE_TOKEN &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="sale">Transaction - Sale</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:sale&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              To create a transaction, you must include an amount() and either a paymentMethodNonce(),
              a paymentMethodToken(), or a customerId(). Passing a customerId is
              equivalent to passing the paymentMethodToken of the customer's default
              payment method.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>One of:</p>
                      </div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#ExistingCustomer">Existing Customer</a></p>
                          </li>
                          <li>
                            <p><a href="#NewCustomer">New Customer</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleCustomer customer Customer details</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Billing Address</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>One of:</p>
                      </div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#ExistingBillingAddress">Existing Billing Address</a></p>
                          </li>
                          <li>
                            <p><a href="#NewBillingAddress">New Billing Address</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleBillingAddress salebillingAddress Billing address details,
                      either new billing address or existing billing address id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Shipping Details</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SaleShippingDetails">Sale Shipping Details</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleShippingDetails saleShippingDetails Shipping amount details</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Shipping Address</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>One of:</p>
                      </div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#ExistingShippingAddress">Existing Shipping Address</a></p>
                          </li>
                          <li>
                            <p><a href="#NewShippingAddress">New Shipping Address</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleShippingAddress saleshippingAddress Shipping address details,
                      either new shipping address or existing shipping address id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Sale Payment Options</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>One of:</p>
                      </div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#PaymentMethodToken">Payment Method Token</a></p>
                          </li>
                          <li>
                            <p><a href="#CardDetails">Card Details</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SalePaymentMode salePaymentOptions SalePaymentMode is either
                      paymentMethodToken or paymentMethodNonce and credit card</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Line Item</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SaleLineItem">Sale Line Item</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleLineItem lineItem The line items for this transaction. It
                      can include up to 249 line items. If your merchant account
                      has been configured Level 3 processing this field will be passed
                      to processor on your behalf.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">3D Secure</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SaleThreeDSecurePassThru">Sale Three D Secure Pass Thru</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleThreeDSecurePassThru threeDSecure Results of a merchant-performed
                      3D Secure authentication. You will only need to use these fields
                      if you've performed your own integration with a 3D Secure MPI
                      provider (e.g. Cardinal Centinel).</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Descriptor</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#TransactionDescriptor">Transaction Descriptor</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">TransactionDescriptor descriptor</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Options</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SaleOptions">Sale Options</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">SaleOptions saleOptions Various options for sale transaction</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Amount</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The billing amount of the request. This value must be greater
                      than 0, and must match the currency format of the merchant
                      account. Can only contain numbers and one decimal point (e.g.
                      x.xx). Can't be greater than the maximum allowed by the processor.
                      Contact us for your specific limit.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Order Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Use this field to pass additional information about the transaction.
                      On PayPal transactions, this field maps to the PayPal invoice
                      number. PayPal invoice numbers must be unique in your PayPal
                      business account. Maximum 255 characters or 127 for PayPal
                      transactions.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Purchase Order Number</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A Level 2 field that can be used to pass a purchase order identification
                      value of up to 12 ASCII characters for AIB and 17 ASCII characters
                      for all other processors.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Device Data</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer device information. Required in the following cases:
                      - When using Advanced Fraud Tools - When creating one-time
                      Vaulted PayPal transactions - When creating Venmo transactions
                      This value will contain a Fraud Merchant ID as the unique,
                      numeric identifier for a Kount account and a Device Session
                      ID as the unique identifier for a customer device. For PayPal
                      and Venmo transactions, this value will also include a PayPal
                      Correlation ID. Provide the full string received from the Braintree
                      client SDK.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Device Session Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A unique alphanumeric identifier used by our Advanced Fraud Tools
                      to link a device to transactions.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Discount Amount</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A Level 3 field that specifies the discount amount that was included
                      in the total transaction amount. It can't be negative, and
                      it does not add to the total transaction amount.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Tax Exempt</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Boolean</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A Level 2 field that indicates whether or not the transaction
                      should be considered eligible for tax exemption. This does
                      not affect the total transaction amount.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">false</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Tax Amount</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A Level 2 field that specifies the amount of tax that was included
                      in the total transaction amount. The value can't be negative,
                      and in most cases, it must be greater than zero in order to
                      qualify for lower interchange rates. It does not add to the
                      total transaction amount.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Service Fee Amount</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The portion of a sub-merchant's transaction revenue that is routed
                      to the master merchant account. If set, this value must be
                      greater than or equal to 0, must match the appropriate currency
                      format, and can't exceed the transaction amount. Available
                      to Braintree Marketplace merchants. See charging a service
                      fee and holding funds in escrow on Braintree Marketplace transactions.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Merchant Account Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The merchant account ID used to create a transaction Currency
                      is also determined by merchant account ID. If no merchant account
                      ID is specified, we will use your default merchant account.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Custom Fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Object</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A collection of custom field/value pairs. Fields and values must
                      be formatted as strings or integers. Maximum 255 characters.
                      You must set up each custom field in the Control Panel prior
                      to passing it with a request. Querying this value returns a
                      collection of custom field values stored on the transaction
                      object.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Transaction Source</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Specifies the source of the transaction. The value passed depends
                      on whether the transaction is initiated by the merchant or
                      the customer. If the transaction is an ecommerce transaction
                      initiated by the customer, no value is passed. Accepted values
                      for merchant-initiated transactions: recurring = Transactions
                      for subsequent recurring payments (e.g. subscriptions with
                      a fixed amount on a predefined schedule). unscheduled = Transactions
                      for unscheduled payments that are not recurring on a predefined
                      schedule or amount (e.g. balance top-up). Formerly merchant.
                      Accepted values for customer-initiated transactions: recurring_first
                      = Transactions that represent the first in a series of recurring
                      payments or subscription. moto = Transactions that are initiated
                      by the customer via the merchant by mail or telephone.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Previous Network Transaction Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Network transaction identifier issued by the card brand network
                      during a previous transaction. Currently only applicable for
                      Visa payment methods. Visa provides network transaction identifiers
                      to improve authorization approval rates for stored credential
                      transactions.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Vault Status</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Enumeration, one of:</p>
                      </div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p>WILL_VAULT</p>
                          </li>
                          <li>
                            <p>VAULTED</p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The option indicates the vaulted status of the externally vaulted
                      payment method. Accepted values: vaulted = Indicates the payment
                      method is already stored on behalf of the customer. will_vault
                      = Indicates the payment method is intended to be vaulted upon
                      successful processing of the transaction.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Browser</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">IP</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="searchCustomer">Customer - Search</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:search-customer&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Search customer operation returns a collection of Customer response objects using
              the search fields
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SearchCustomer">Search Customer</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer search fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Address Fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Array of <a href="#AddressInformation">Address Information</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer address information to search for.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Array of <a href="#PaymentMethodInformation">Payment Method Information</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment method information to search for.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Limit</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Number</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Limit the number of search results. (0 for no limit)</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">100</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Array of <a href="https://developers.braintreepayments.com/reference/response/customer/java">customer</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CUSTOMER_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="searchTransaction">Transaction - Search</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:search-transaction&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Search transaction operation returns a collection of Transaction response objects
              using the search fields
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Transaction</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SearchTransaction">Search Transaction</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Search transaction fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Date Range Parameter</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#DateRangeParameters">Date Range Parameters</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Date/time range transaction parameters</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Search Parameters</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#SearchParameters">Search Parameters</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Search field transaction parameters</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Filter Parameters</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#FilterParameters">Filter Parameters</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Multiple values transaction parameters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Limit</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Number</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Limit the number of search results. Set 0 for no limit.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">100</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Array of <a href="https://developers.braintreepayments.com/reference/response/transaction/java">transaction</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="submitForPartialSettlement">Transaction - Submit For Partial Settlement</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:submit-for-partial-settlement&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Submit for Partial Settlement operation is used to settle multiple partial amounts
              against the same authorization. You can create a parent authorization
              for the entire order amount and when you?re ready to send each portion
              of the order, you can charge the customer for that portion in a separate
              child transaction.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Authorized Transaction</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The transaction ID of the parent authorization. You can only
                      submit transactions that have a status of AUTHORIZED for partial
                      settlement.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Amount</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An amount to submit for partial settlement against the parent
                      authorization transaction. Must be greater than 0. You can
                      make multiple partial settlement calls as long as the cumulative
                      amount to be partially settled is less than or equal to the
                      amount authorized by the parent transaction.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Order Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The unique order identifier, used to pass additional information
                      about the transaction.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="submitForSettlement">Transaction - Submit For Settlement</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:submit-for-settlement&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Submit for Settlement operation explicitly submit the specified transaction for settlement.
              It collects the money from an authorized sale by submitting the transaction
              for settlement
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Transaction Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The unique transaction identifier. You can only submit transactions
                      that have a status of authorized for settlement.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Amount</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An amount to submit for settlement. Must be greater than 0. If
                      you want to settle for an amount that is different from the
                      total authorization amount, you can specify the amount to settle.
                      If you do not specify, the entire amount will be settled.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Order Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The unique order identifier, used to pass additional information
                      about the transaction.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Name</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The value in the business name field of a customer's statement.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Phone</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The value in the phone number field of a customer's statement.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Url</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The value in the URL/web address field of a customer's statement.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="updateCustomer">Customer - Update</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:update-customer&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Operation to update customer. To update a customer, use its ID along with new attributes.
              The same validations apply as when creating a customer. Any attribute
              not passed will remain unchanged.
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The customer Id to update.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentCardInformation">Payment Card Information</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A credit or debit payment method details.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment Method Options</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentMethodOptions">Payment Method Options</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment method options.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Address</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/response/address/java">Address</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A billing address associated with a specific credit card. The
                      maximum number of addresses per customer is 50.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">ID</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A string value that will represent this specific customer in
                      your Vault. 36 character maximum; must be unique within your
                      Vault; valid characters are letters, numbers, -, and _; the
                      words "all" and "new" currently can't be used. If not specified
                      on creation, the gateway will generate an alphanumeric ID that
                      can be accessed on the result. The generated IDs will never
                      start with a leading 0 and are case insensitive.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">First Name</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The first name. The first name value must be less than or equal
                      to 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Last Name</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The last name. The last name value must be less than or equal
                      to 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Email</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Email address composed of ASCII characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Phone</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Phone number. Maximum 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">fax</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Fax number. Maximum 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Company</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Company name. Maximum 255 characters.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Website</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Website URL. Must be less than or equal to 255 characters. Website
                      must be well-formed. The URL scheme is optional.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Token</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An alphanumeric value that references a specific payment method
                      stored in your Vault. Must be less than or equal to 36 characters.
                      If using a custom integration, you can specify what you want
                      the token to be. If not specified, the gateway will generate
                      one that can be accessed on the result.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Nonce</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">One-time-use reference to payment information provided by your
                      customer, such as a credit card or PayPal account. When passed
                      on customer create, it creates a payment method associated
                      with the new customer.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Device Data</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer device information. Pass this value only if you have
                      Advanced Fraud Tools enabled and are adding credit card data
                      to your Vault. Be sure to provide the full string received
                      from the Braintree.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Custom Fields</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>Object</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A collection of custom field/value pairs. Fields and values must
                      be less than 255 characters. You must <a href="https://articles.braintreepayments.com/control-panel/custom-fields?&_ga=1.28588988.1497859415.1565702545#creating-a-custom-field">set up each custom field in the Control Panel</a>                      prior to passing it with a request.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Device Session Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Fraud Merchant Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Risk Data</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/request/customer/create/java#risk_data">Risk Data</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Customer device information, which is sent directly to supported
                      processors for fraud analysis. These fields are automatically
                      populated if using <a href="https://developers.braintreepayments.com/guides/advanced-fraud-tools/overview">Advanced Fraud Tools</a>.
                      Currently only available when processing American Express via
                      Amex Direct.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CUSTOMER_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="updatePaymentMethod">PaymentMethod - Update</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:update-payment-method&gt;</code></p>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Billing Address</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/response/address/java">Address</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A billing address associated with a specific customer ID. It
                      can be further associated with a specific payment method. The
                      maximum number of addresses per customer is 50.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Update Payment Method Details</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#UpdatePaymentMethod">Update Payment Method</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment method details</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Updatepayment Method</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#PaymentCardInformation">Payment Card Information</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A credit or debit payment method details.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Update Payment Method Options</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="#UpdatePaymentMethodOptions">Update Payment Method Options</a></p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Payment method options.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:PAYMENT_METHOD_NOT_FOUND &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="sect2">
          <h3 id="voidTransaction">Transaction - Void</h3>
          <div class="paragraph">
            <p><code>&lt;braintree:void-transaction&gt;</code></p>
          </div>
          <div class="paragraph">
            <p>
              Void Transaction operation undo a transaction before it settles. It cancels the transfer
              of funds before the transaction settles. You can only void transactions
              that have a status() of: AUTHORIZED, SUBMITTED_FOR_SETTLEMENT, SETTLEMENT_PENDING
              (only for certain PayPal transactions)
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
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Configuration</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">String</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of the configuration to use.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Transaction Id</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The unique transaction identifier.</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock"><strong>x</strong>&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">The name of a variable on which the operation's output will be
                      placed</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Target Value</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p>String</p>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">An expression that will be evaluated against the operation's
                      output and the outcome of that expression will be stored in
                      the target variable</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">#[payload]</p>
                  </td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">Reconnection Strategy</p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="ulist">
                        <ul>
                          <li>
                            <p><a href="#reconnect">Reconnect</a></p>
                          </li>
                          <li>
                            <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock">A retry strategy in case of connectivity errors</p>
                  </td>
                  <td class="tableblock halign-left valign-middle"></td>
                  <td class="tableblock halign-center valign-middle">
                    <p class="tableblock">&#160;</p>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="sect3">
            <h4 id="_output_16">Output</h4>
            <table class="tableblock frame-all grid-all spread">
              <colgroup>
                <col style="width: 50%;">
                <col style="width: 50%;">
              </colgroup>
              <tbody>
                <tr>
                  <td class="tableblock halign-left valign-middle">
                    <p class="tableblock"><strong>Type</strong></p>
                  </td>
                  <td class="tableblock halign-left valign-middle">
                    <div>
                      <div class="paragraph">
                        <p><a href="https://developers.braintreepayments.com/reference/general/result-objects/java">Result</a></p>
                      </div>
                    </div>
                  </td>
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
                  <p>BRAINTREE:EXECUTION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:CONNECTIVITY &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHORIZATION &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
                </li>
                <li>
                  <p>BRAINTREE:AUTHENTICATION &#160;</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
		<div class="sect2">
			<h3 id="refundTransaction">Transaction - Refund</h3>
			<div class="paragraph">
				<p><code>&lt;braintree:refund-transaction&gt;</code></p>
			</div>
			<div class="paragraph">
				<p>
					Refund transaction operation refunds the specified transaction that have a status of settled or settling. If the transaction has not yet begun settlement, use 'Void Transaction' operation instead.
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
							<td class="tableblock halign-left valign-middle"><p class="tableblock">Transaction Id</p></td>
							<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
							<p>String</p>
							</div></div></td>
							<td class="tableblock halign-left valign-middle"><p class="tableblock">The unique transaction identifier. You can only refund the transactions that have a status of settled or settling.</p></td>
							<td class="tableblock halign-left valign-middle"></td>
							<td class="tableblock halign-center valign-middle"><p class="tableblock"><strong>x</strong>&#160;</p></td>
						</tr>
						<tr>
							<td class="tableblock halign-left valign-middle"><p class="tableblock">Amount</p></td>
							<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
							<p>String</p>
							</div></div></td>
							<td class="tableblock halign-left valign-middle"><p class="tableblock">The amount to refund. This value must be greater than 0, and can't exceed the total amount of the transaction. If you do not specify an amount to refund, the entire transaction amount will be refunded</p></td>
							<td class="tableblock halign-left valign-middle"></td>
							<td class="tableblock halign-center valign-middle"><p class="tableblock">&#160;</p></td>
						</tr>
						<tr>
							<td class="tableblock halign-left valign-middle"><p class="tableblock">Order Id</p></td>
							<td class="tableblock halign-left valign-middle"><div><div class="paragraph">
							<p>String</p>
							</div></div></td>
							<td class="tableblock halign-left valign-middle"><p class="tableblock">The unique order identifier, use this parameter if you would like to pass different orderId than that of the original transaction.</p></td>
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
						<p><a href="#Result">Result</a></p>
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
							<p>BRAINTREE:EXECUTION &#160;</p>
						</li>
						<li>
							<p>BRAINTREE:CONNECTIVITY &#160;</p>
						</li>
						<li>
							<p>BRAINTREE:AUTHORIZATION &#160;</p>
						</li>
						<li>
							<p>BRAINTREE:RETRY_EXHAUSTED &#160;</p>
						</li>
						<li>
							<p>BRAINTREE:AUTHENTICATION &#160;</p>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Fails Deployment</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">When the application is deployed, a connectivity test is performed
                    on all connectors. If set to true, deployment will fail if the
                    test doesn&#8217;t pass after exhausting the associated reconnection
                    strategy</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Reconnection Strategy</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p><a href="#reconnect">Reconnect</a></p>
                        </li>
                        <li>
                          <p><a href="#reconnect-forever">Reconnect Forever</a></p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The reconnection strategy to use</p>
                </td>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Frequency</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">How often (in ms) to reconnect</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Count</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">How many reconnection attempts to make</p>
                </td>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Frequency</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">How often (in ms) to reconnect</p>
                </td>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Max Active</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Controls the maximum number of Mule components that can be borrowed
                    from a session at one time. When set to a negative value, there
                    is no limit to the number of components that may be active at
                    one time. When maxActive is exceeded, the pool is said to be
                    exhausted.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Max Idle</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Controls the maximum number of Mule components that can sit idle
                    in the pool at any time. When set to a negative value, there
                    is no limit to the number of Mule components that may be idle
                    at one time.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Max Wait</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies the number of milliseconds to wait for a pooled component
                    to become available when the pool is exhausted and the exhaustedAction
                    is set to WHEN_EXHAUSTED_WAIT.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Min Eviction Millis</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Determines the minimum amount of time an object may sit idle in
                    the pool before it is eligible for eviction. When non-positive,
                    no objects will be evicted from the pool due to idle time alone.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Eviction Check Interval Millis</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies the number of milliseconds between runs of the object
                    evictor. When non-positive, no object evictor is executed.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Exhausted Action</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
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
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies the behavior of the Mule component pool when the pool
                    is exhausted. Possible values are: "WHEN_EXHAUSTED_FAIL", which
                    will throw a NoSuchElementException, "WHEN_EXHAUSTED_WAIT", which
                    will block by invoking Object.wait(long) until a new or idle
                    object is available, or WHEN_EXHAUSTED_GROW, which will create
                    a new Mule instance and return it, essentially making maxActive
                    meaningless. If a positive maxWait value is supplied, it will
                    block for at most that many milliseconds, after which a NoSuchElementException
                    will be thrown. If maxThreadWait is a negative value, it will
                    block indefinitely.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Initialisation Policy</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
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
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Determines how components in a pool should be initialized. The
                    possible values are: INITIALISE_NONE (will not load any components
                    into the pool on startup), INITIALISE_ONE (will load one initial
                    component into the pool on startup), or INITIALISE_ALL (will
                    load all components in the pool on startup)</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Disabled</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Whether pooling should be disabled</p>
                </td>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Max Idle Time</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A scalar time value for the maximum amount of time a dynamic configuration
                    instance should be allowed to be idle before it&#8217;s considered
                    eligible for expiration</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Time Unit</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
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
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A time unit that qualifies the maxIdleTime attribute</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="PaymentCardInformation">Payment Card Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Billing Address Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Provide billing address Id to use existing billing address with
                    payment method.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Device Data</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer device information. Pass this value only if you have Advanced
                    Fraud Tools enabled and are adding credit card data to your Vault.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Cardholder Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The name associated with the credit card. Must be less than or
                    equal to 175 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Number</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Typically requires The &lt;a href= "https://www.pcisecuritystandards.org/pci_security/completing_self_assessment"&gt;PCI
                    SAQ D compliance&lt;/a&gt; Braintree recommend using paymentMethodNonce
                    to avoid any PCI concerns with raw credit card data being present
                    on your server. The 12-19 digit value on a credit card consisting
                    of a bank identification number (BIN) and primary account number
                    (PAN).</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Cvv</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A 3 or 4 digit card verification value assigned to a credit card.
                    The CVV will never be stored in the gateway, but it can be provided
                    with one-time requests to verify the card.
                  </p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Expiration Month</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The expiration month of a credit card, formatted MM. May be used
                    with expirationYear, and instead of expirationDate.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Expiration Year</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The two or four digit year associated with a credit card, formatted
                    YYYY or YY. May be used with expirationMonth, and instead of
                    expirationDate.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="PaymentMethodOptions">Payment Method Options</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Fail On Duplicate Payment Method</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">If this option is passed and the same payment method has already
                    been added to the Vault for any customer, the request will fail.
                    This option will be ignored for PayPal, Pay with Venmo, Apple
                    Pay, Google Pay, and Samsung Pay payment methods.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Token</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">An alphanumeric value that references a specific payment method
                    stored in your Vault. Must be less than or equal to 36 characters.
                    If using a custom integration, you can specify what you want
                    the token to be. If not specified, the gateway will generate
                    one that can be accessed on the result.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Make Default</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">This option makes the specified payment method the default for
                    the customer.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verification Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specify a non-negative amount that you want to use to verify a
                    card. If you do not pass this option, the gateway will automatically
                    use a verification amount of $0 or $1, depending on the processor
                    and/or card type.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verification Merchant Account Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specify the merchant account ID that you want to use to verify
                    a card. Can&#8217;t be a Braintree Marketplace sub-merchant account.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verify Card</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">If the payment method is a credit card, this option prompts the
                    gateway to verify the card&#8217;s number and expiration date.
                    It also verifies the AVS and CVV information if you&#8217;ve
                    enabled AVS and CVV rules.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="ClientTokenRequestOptions">Client Token Request Options</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A string value representing an existing customer in your Vault.
                    Passing this option allows customers to manage their vaulted
                    payment methods via the Drop-in UI</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Merchant Account Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specify the merchant account ID that you want to use to generate
                    the client token. If no merchant account ID is specified, Braintree
                    will use your default merchant account.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Version</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Fail On Duplicate Payment Method</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">If this option is passed and the same payment method has already
                    been added to the Vault for any customer, the request will fail.
                    This can only be passed if a customerId is passed as well. This
                    option will be ignored for PayPal, Pay with Venmo, Apple Pay,
                    Google Pay, and Samsung Pay payment methods.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Make Default</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">This option makes the specified payment method the default for
                    the customer. This can only be passed if a customer_id is passed
                    as well.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verify Card</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">If the payment method is a credit card, this option prompts the
                    gateway to verify the card&#8217;s number and expiration date.
                    It also verifies the AVS and CVV information if you&#8217;ve
                    enabled AVS and CVV rules. This option can only be passed if
                    a customerId is passed as well.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SaleShippingDetails">Sale Shipping Details</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Shipping Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A Level 3 field that specifies the shipping cost on the entire
                    transaction. It can&#8217;t be negative, and it does not add
                    to the total transaction amount.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Ships From Postal Code</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A Level 3 field that specifies the postal code of the shipping
                    location.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SaleLineItem">Sale Line Item</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Commodity Code</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Code used to classify items purchased and track the total amount
                    spent across various categories of products and services. Different
                    corporate purchasing organizations may use different standards,
                    but the United Nations Standard Products and Services Code (UNSPSC)
                    is frequently used. Maximum 12 characters.
                  </p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Description</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Item description. Maximum 127 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Discount Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Discount amount for the line item. Can include up to 2 decimal
                    places. This value can&#8217;t be negative.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Kind</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>DEBIT</p>
                        </li>
                        <li>
                          <p>CREDIT</p>
                        </li>
                        <li>
                          <p>UNRECOGNIZED</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Indicates whether the line item is a debit (sale) or credit (refund)
                    to the customer. Accepted values: - "debit" - "credit"</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Line Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Item name. Maximum 35 characters, or 127 characters for PayPal
                    transactions.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Product Code</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Product or UPC code for the item. Maximum 12 characters, or 127
                    characters for PayPal transactions.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Quantity</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Number of units of the item purchased. Can include up to 4 decimal
                    places. This value can&#8217;t be negative or zero.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Tax Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Tax amount for the line item. Can include up to 2 decimal places.
                    This value can&#8217;t be negative.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Total Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Quantity x unit amount. Can include up to 2 decimal places.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Unit Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Per-unit price of the item. Maximum 4 decimal places, or 2 decimal
                    places for PayPal transactions. This value can&#8217;t be negative
                    or zero.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Unit Of Measure</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The unit of measure or the unit of measure code. Maximum 12 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Unit Tax Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Number</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Per-unit tax price of the item. Can include up to 2 decimal places.
                    This value can&#8217;t be negative or zero.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Url</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The URL to product information.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SaleThreeDSecurePassThru">Sale Three D Secure Pass Thru</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Cavv</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Cardholder authentication verification value or CAVV. The main
                    encrypted message issuers and card networks use to verify authentication
                    has occurred. Mastercard uses an AVV message and American Express
                    uses an AEVV message, each of which should also be passed in
                    the cavv parameter.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Ds Transaction Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction identifier resulting from 3D Secure 2 authentication.
                    This field must be supplied for Mastercard Identity Check.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Eci Flag</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The value of the electronic commerce indicator (ECI) flag, which
                    indicates the outcome of the 3DS authentication. Accepted values
                    for Mastercard: 00 = Failed or not attempted 01 = Attempted 02
                    = Success
                  </p>
                  <p class="tableblock"> Accepted values for all other card brands: 07 = Failed or not attempted
                    06 = Attempted 05 = Success</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Three D Secure Version</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The version of 3D Secure authentication used for the transaction.
                    Required on Visa and Mastercard authentications. Must be composed
                    of digits separated by periods (e.g. 1.0.2).</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Xid</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction identifier resulting from 3D Secure authentication.
                    Uniquely identifies the transaction and sometimes required in
                    the authorization message. Must be base64-encoded. This field
                    will no longer be used in 3D Secure 2 authentications.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionDescriptor">Transaction Descriptor</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The value in the business name field of a customer&#8217;s statement.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Phone</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The value in the phone number field of a customer&#8217;s statement.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Url</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The value in the URL/web address field of a customer&#8217;s statement.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SaleOptions">Sale Options</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Hold In Escrow</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">For Braintree Marketplace merchants only. This value specifies
                    whether a transaction is held in escrow. See Escrow for more
                    detail.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Paypal Custom Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Variable passed directly to PayPal via the API for your own tracking
                    purposes. Customers do not see this value, but you can see it
                    in reports from your PayPal console. It also appears in the Braintree
                    Control Panel on the Transaction Detail page of the associated
                    PayPal transaction, and in the CSV file of downloaded transaction
                    searches. Unlike Braintree custom fields, this field does not
                    need to be configured in the Braintree Control Panel.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Paypal Description</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Description of the transaction that is displayed to customers in
                    PayPal email receipts. Max 127 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Skip Advanced Fraud Checking</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Prevents the transaction from being sent to Kount for evaluation
                    as part of Advanced Fraud Tools checks. Use with caution ? once
                    you&#8217;ve skipped checks for a transaction, it is not possible
                    to run them retroactively.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Skip Avs</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Skip AVS checks for the transaction. Will result in a processor
                    response code of B for avsPostalCodeResponseCode and avsStreetAddressResponseCode,
                    and nil for avsErrorResponseCode. Use with caution ? once you&#8217;ve
                    skipped checks for a transaction, it is not possible to run them
                    retroactively.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Skip Cvv</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Skip CVV checks for the transaction. Will result in a processor
                    response code of B for cvvResponseCode. Use with caution ? once
                    you&#8217;ve skipped checks for a transaction, it is not possible
                    to run them retroactively.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Store In Vault On Success</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The option that determines whether the payment method associated
                    with the successful transaction should be stored in the Vault.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Store In Vault</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The option that determines whether the payment method should be
                    stored in the Vault, regardless of the transaction&#8217;s success.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Submit For Settlement</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The option that determines whether an authorized transaction is
                    submitted for settlement.
                  </p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Venmo Profile Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specify which Venmo business profile to use for a transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SearchCustomer">Search Customer</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Fields</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#CustomerInformation">Customer Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer fields information to search for.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Created At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateInformation">Date Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the customer was created.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Ids</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A list of customer IDs to search for.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="CustomerInformation">Customer Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>FIRST_NAME</p>
                        </li>
                        <li>
                          <p>LAST_NAME</p>
                        </li>
                        <li>
                          <p>CUSTOMER_ID</p>
                        </li>
                        <li>
                          <p>EMAIL</p>
                        </li>
                        <li>
                          <p>PHONE</p>
                        </li>
                        <li>
                          <p>FAX</p>
                        </li>
                        <li>
                          <p>COMPANY</p>
                        </li>
                        <li>
                          <p>WEBSITE</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search customer field</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="DateInformation">Date Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>BETWEEN</p>
                        </li>
                        <li>
                          <p>GREATER_THAN_OR_EQUAL_TO</p>
                        </li>
                        <li>
                          <p>LESS_THAN_OR_EQUAL_TO</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator for Date Range parameter for search transaction</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Date</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Date in search transaction. For BETWEEN operator, it is 'From Date'.
                    Provide date in dd-MM-yyyy HH:mm format. Example: 25-12-2019
                    13:59</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Max Date</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">It is only required for BETWEEN operator. Provide date in dd-MM-yyyy
                    HH:mm format. Example: 25-12-2019 13:59</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="AddressInformation">Address Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>FIRST_NAME</p>
                        </li>
                        <li>
                          <p>LAST_NAME</p>
                        </li>
                        <li>
                          <p>STREET_ADDRESS</p>
                        </li>
                        <li>
                          <p>EXTENDED_ADDRESS</p>
                        </li>
                        <li>
                          <p>LOCALITY</p>
                        </li>
                        <li>
                          <p>REGION</p>
                        </li>
                        <li>
                          <p>POSTAL_CODE</p>
                        </li>
                        <li>
                          <p>COUNTRY_NAME</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search address field</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="PaymentMethodInformation">Payment Method Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>CARDHOLDER_NAME</p>
                        </li>
                        <li>
                          <p>PAYMENT_METHOD_TOKEN</p>
                        </li>
                        <li>
                          <p>PAYPAL_ACCOUNT_EMAIL</p>
                        </li>
                        <li>
                          <p>CREDIT_CARD_NUMBER</p>
                        </li>
                        <li>
                          <p>EXPIRATION_DATE</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search payment method field</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SearchTransaction">Search Transaction</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#Amount">Amount</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The amount of the transaction. The amount must be formatted like
                    xx or x.xx.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Ids</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of transaction IDs to search for.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Merchant Account Ids</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The merchant account IDs associated with transactions.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Is A Refund</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies whether transaction is a refund</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="Amount">Amount</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>BETWEEN</p>
                        </li>
                        <li>
                          <p>GREATER_THAN_OR_EQUAL_TO</p>
                        </li>
                        <li>
                          <p>LESS_THAN_OR_EQUAL_TO</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator for Range parameter for search transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Min Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction amount in search transaction. For BETWEEN operator,
                    it is the minimum amount. Provide amount in x.xx format. Example:
                    5000.00</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Max Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">It is only required for BETWEEN operator and it is the maximum
                    amount with between operator. Provide maxAmount in x.xx format.
                    Example: 5000.00</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="DateRangeParameters">Date Range Parameters</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Authorization Expired At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction&#8217;s authorization expired.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Authorized At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction was authorized.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Created At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time at which the transaction was created.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Disbursement Date</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date the transaction was disbursed to your bank account. This
                    field does not include a time value.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Dispute Date</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date the transaction was disputed. This field does not include
                    a time value.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Failed At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction failed.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Gateway Rejected At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction was rejected by the gateway.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Processor Declined At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction was declined by the processor</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Settled At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction finished settling.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Submitted For Settlement At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction was submitted for settlement.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Voided At</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="#DateRange">Date Range</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The date/time the transaction was voided.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="DateRange">Date Range</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>BETWEEN</p>
                        </li>
                        <li>
                          <p>GREATER_THAN_OR_EQUAL_TO</p>
                        </li>
                        <li>
                          <p>LESS_THAN_OR_EQUAL_TO</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator for Date Range parameter for search transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Date</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Date in search transaction. For BETWEEN operator, it is 'From Date'.
                    Provide date in dd-MM-yyyy HH:mm format. Example: 25-12-2019
                    13:59</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">To Date</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">It is only required for BETWEEN operator and it is 'To Date'. Provide
                    date in dd-MM-yyyy HH:mm format. Example: 25-12-2019 13:59</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SearchParameters">Search Parameters</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Informations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionInformation">Transaction Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction information parameters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Settlement Informations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#SettlementInformation">Settlement Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Parameters for Transaction settlement.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Payment Informations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#PaymentInformation">Payment Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Parameters for Transaction&#8217;s Payment Method.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Informations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#CustomerInformation">Customer Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer information parameters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Billing Address Informations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#BillingAddressInformation">Billing Address Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Parameters for Transaction&#8217;s billing address.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Shipping Address Informations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#ShippingAddressInformation">Shipping Address Information</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Parameters for Transaction&#8217;s shipping address.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionInformation">Transaction Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>TRANSACTION_ID</p>
                        </li>
                        <li>
                          <p>CURRENCY</p>
                        </li>
                        <li>
                          <p>ORDER_ID</p>
                        </li>
                        <li>
                          <p>PROCESSOR_AUTHORIZATION_CODE</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search fields for Transaction</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator for Transaction</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value for transaction</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="SettlementInformation">Settlement Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>SETTLEMENT_BATCH_ID</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search field for Settlement Information</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operatior for Settlement Information</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value for Settlement Information</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="PaymentInformation">Payment Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>CARDHOLDER_NAME</p>
                        </li>
                        <li>
                          <p>CREDIT_CARD_UNIQUE_IDENTIFIER</p>
                        </li>
                        <li>
                          <p>PAYMENT_METHOD_TOKEN</p>
                        </li>
                        <li>
                          <p>PAYPAL_ACCOUNT_PAYER_EMAIL</p>
                        </li>
                        <li>
                          <p>PAYPAL_ACCOUNT_PAYMENT_ID</p>
                        </li>
                        <li>
                          <p>PAYPAL_ACCOUNT_AUTHORIZATION_ID</p>
                        </li>
                        <li>
                          <p>EXPIRATION_DATE</p>
                        </li>
                        <li>
                          <p>CREDIT_CARD_NUMBER</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search fields for Payment Methods</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator for Payment Methods</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="BillingAddressInformation">Billing Address Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>BILLING_FIRST_NAME</p>
                        </li>
                        <li>
                          <p>BILLING_LAST_NAME</p>
                        </li>
                        <li>
                          <p>BILLING_COMPANY</p>
                        </li>
                        <li>
                          <p>BILLING_STREET_ADDRESS</p>
                        </li>
                        <li>
                          <p>BILLING_EXTENDED_ADDRESS</p>
                        </li>
                        <li>
                          <p>BILLING_LOCATITY</p>
                        </li>
                        <li>
                          <p>BILLING_REGION</p>
                        </li>
                        <li>
                          <p>BILLING_POSTAL_CODE</p>
                        </li>
                        <li>
                          <p>BILLING_COUNTRY_NAME</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search fields for Billing Address</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator for billing address</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value for billing address</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="ShippingAddressInformation">Shipping Address Information</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Field</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>SHIPPING_FIRST_NAME</p>
                        </li>
                        <li>
                          <p>SHIPPING_LAST_NAME</p>
                        </li>
                        <li>
                          <p>SHIPPING_COMPANY</p>
                        </li>
                        <li>
                          <p>SHIPPING_STREET_ADDRESS</p>
                        </li>
                        <li>
                          <p>SHIPPING_EXTENDED_ADDRESS</p>
                        </li>
                        <li>
                          <p>SHIPPING_LOCATITY</p>
                        </li>
                        <li>
                          <p>SHIPPING_REGION</p>
                        </li>
                        <li>
                          <p>SHIPPING_POSTAL_CODE</p>
                        </li>
                        <li>
                          <p>SHIPPING_COUNTRY_NAME</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search fields for Shipping Address</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Operator</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>IS</p>
                        </li>
                        <li>
                          <p>IS_NOT</p>
                        </li>
                        <li>
                          <p>STARTS_WITH</p>
                        </li>
                        <li>
                          <p>ENDS_WITH</p>
                        </li>
                        <li>
                          <p>CONTAINS</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search operator for Shipping Address</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search String</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Search value for shipping address</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="FilterParameters">Filter Parameters</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Types</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionType">Transaction Type</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of transaction types to search for.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Statuses</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionStatus">Transaction Status</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of statuses to search for.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Sources</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionSource">Transaction Source</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of sources of transaction i.e how transaction was created</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Card Types</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionCardType">Transaction Card Type</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of different types of credit card.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Payment Instrument Types</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#PaymentInstrumentType">Payment Instrument Type</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of payment methods used to process the transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transactions Created Using</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionCreatedUsing">Transaction Created Using</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of data used to create the transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Locations</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Array of <a href="#TransactionCustomerLocation">Transaction Customer Location</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The list of the customer location in the transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionType">Transaction Type</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Type</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>SALE</p>
                        </li>
                        <li>
                          <p>CREDIT</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Types of transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionStatus">Transaction Status</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Status</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>AUTHORIZING</p>
                        </li>
                        <li>
                          <p>AUTHORIZED</p>
                        </li>
                        <li>
                          <p>AUTHORIZATION_EXPIRED</p>
                        </li>
                        <li>
                          <p>SUBMITTED_FOR_SETTLEMENT</p>
                        </li>
                        <li>
                          <p>SETTLING</p>
                        </li>
                        <li>
                          <p>SETTLEMENT_PENDING</p>
                        </li>
                        <li>
                          <p>SETTLEMENT_DECLINED</p>
                        </li>
                        <li>
                          <p>SETTLED</p>
                        </li>
                        <li>
                          <p>VOIDED</p>
                        </li>
                        <li>
                          <p>PROCESSOR_DECLINED</p>
                        </li>
                        <li>
                          <p>GATEWAY_REJECTED</p>
                        </li>
                        <li>
                          <p>FAILED</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies transaction&#8217;s status.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionSource">Transaction Source</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Source</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>API</p>
                        </li>
                        <li>
                          <p>CONTROL_PANEL</p>
                        </li>
                        <li>
                          <p>RECURRING</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies transaction&#8217;s source.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionCardType">Transaction Card Type</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Card Type</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>AMERICAN_EXPRESS</p>
                        </li>
                        <li>
                          <p>DISCOVER</p>
                        </li>
                        <li>
                          <p>MAESTRO</p>
                        </li>
                        <li>
                          <p>JCB</p>
                        </li>
                        <li>
                          <p>MASTER_CARD</p>
                        </li>
                        <li>
                          <p>UNION_PAY</p>
                        </li>
                        <li>
                          <p>VISA</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Different types of credit card.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="PaymentInstrumentType">Payment Instrument Type</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Payment Instrument Type</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>ANDROID_PAY_CARD</p>
                        </li>
                        <li>
                          <p>APPLE_PAY_CARD</p>
                        </li>
                        <li>
                          <p>CREDIT_CARD</p>
                        </li>
                        <li>
                          <p>MASTERPASS_CARD</p>
                        </li>
                        <li>
                          <p>PAYPAL_ACCOUNT</p>
                        </li>
                        <li>
                          <p>SAMSUNG_PAY_CARD</p>
                        </li>
                        <li>
                          <p>US_BANK_ACCOUNT</p>
                        </li>
                        <li>
                          <p>VENMO_ACCOUNT</p>
                        </li>
                        <li>
                          <p>VISA_CHECKOUT_CARD</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Payment methods used to process the transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionCreatedUsing">Transaction Created Using</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Transaction Created Using</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>TOKEN</p>
                        </li>
                        <li>
                          <p>FULL_INFORMATION</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Data used to create the transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="TransactionCustomerLocation">Transaction Customer Location</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Location</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Enumeration, one of:</p>
                    </div>
                    <div class="ulist">
                      <ul>
                        <li>
                          <p>INTERNATIONAL</p>
                        </li>
                        <li>
                          <p>US</p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specifies customer location in the transaction.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="UpdatePaymentMethod">Update Payment Method</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Token</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The alphanumeric value that references a specific payment method
                    stored in your Vault.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Update Existing</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Update the billing address associated with the payment method token
                    specified. Other payment methods associated with the same billing
                    address will have their addresses updated, as well.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Payment Method Nonce</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">One-time-use reference to new card details provided by your customer.
                    Can only be used on payment method update if the payment method
                    type is a card; other payment method types do not allow their
                    details to be updated.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">New Token</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">If provided, updates the token for the payment method.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="UpdatePaymentMethodOptions">Update Payment Method Options</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Make Default</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">This option makes the specified payment method the default for
                    the customer.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verification Amount</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specify a non-negative amount that you want to use to verify a
                    card. If you do not pass this option, the gateway will automatically
                    use a verification amount of $0 or $1, depending on the processor
                    and/or card type.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verification Merchant Account Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Specify the merchant account ID that you want to use to verify
                    a card. Can&#8217;t be a Braintree Marketplace sub-merchant account.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Verify Card</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">If the payment method is a credit card, this option prompts the
                    gateway to verify the card&#8217;s number and expiration date.
                    It also verifies the AVS and CVV information if you&#8217;ve
                    enabled AVS and CVV rules.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="ExistingCustomer">Existing Customer</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A string value representing an existing customer in your Vault
                    that you want to charge.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="NewCustomer">New Customer</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A string value that will represent this specific customer in your
                    Vault. 36 character maximum; must be unique within your Vault;
                    valid characters are letters, numbers, -, and _; the words "all"
                    and "new" currently can&#8217;t be used. If not specified on
                    creation, the gateway will generate an alphanumeric ID that can
                    be accessed on the result. The generated IDs will never start
                    with a leading 0 and are case insensitive.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer First Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The first name. The first name value must be less than or equal
                    to 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer Last Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The last name. The last name value must be less than or equal to
                    255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Email</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Email address composed of ASCII characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Phone</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Phone number. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Fax</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Fax number. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Company</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Company name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Website</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Website URL. Must be less than or equal to 255 characters. Website
                    must be well-formed. The URL scheme is optional.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Token</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">An alphanumeric value that references a specific payment method
                    stored in your Vault. Must be less than or equal to 36 characters.
                    If using a custom integration, you can specify what you want
                    the token to be. If not specified, the gateway will generate
                    one that can be accessed on the result.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Nonce</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">One-time-use reference to payment information provided by your
                    customer, such as a credit card or PayPal account. When passed
                    on customer create, it creates a payment method associated with
                    the new customer.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Device Data</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer device information. Pass this value only if you have Advanced
                    Fraud Tools enabled and are adding credit card data to your Vault.
                    Be sure to provide the full string received from the Braintree.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Custom Fields</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Object</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A collection of custom field/value pairs. Fields and values must
                    be less than 255 characters. You must &lt;a href="https://articles.braintreepayments.com/control-panel/custom-fields?&amp;_ga=1.28588988.1497859415.1565702545#creating-a-custom-field"&gt;set
                    up each custom field in the Control Panel&lt;/a&gt; prior to
                    passing it with a request.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Risk Data</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p><a href="https://developers.braintreepayments.com/reference/request/customer/create/java#risk_data">Risk Data</a></p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Customer device information, which is sent directly to supported
                    processors for fraud analysis. These fields are automatically
                    populated if using &lt;a href="https://developers.braintreepayments.com/guides/advanced-fraud-tools/overview"&gt;Advanced
                    Fraud Tools&lt;/a&gt;. Currently only available when processing
                    American Express via Amex Direct.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="ExistingBillingAddress">Existing Billing Address</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Billing Address Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The two-letter value for an address associated with a specific
                    customer ID. The maximum number of addresses per customer is
                    50.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="NewBillingAddress">New Billing Address</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Add Billing Address To Payment Method</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The option that determines whether the billing address information
                    provided in the request should be added to the payment method
                    specified. This option works only for new payment methods.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">First Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The first name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Last Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The last name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Company</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Company name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Code Alpha2</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The &lt;a href="http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2"&gt;ISO
                    3166-1 alpha-2&lt;/a&gt; country code specified in an address.
                    The gateway only accepts &lt;a href="https://developers.braintreepayments.com/reference/general/countries#list-of-countries"&gt;specific
                    alpha-2 values&lt;/a&gt;.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Code Alpha3</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The &lt;a href="http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3"&gt;ISO
                    3166-1 alpha-3&lt;/a&gt; country code specified in an address.
                    The gateway only accepts &lt;a href="https://developers.braintreepayments.com/reference/general/countries#list-of-countries"&gt;specific
                    alpha-3 values&lt;/a&gt;.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Code Numeric</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The &lt;a href="http://en.wikipedia.org/wiki/ISO_3166-1_numeric"&gt;ISO
                    3166-1 numeric&lt;/a&gt; country code specified in an address.
                    The gateway only accepts &lt;a href="https://developers.braintreepayments.com/reference/general/countries#list-of-countries"&gt;specific
                    numeric values&lt;/a&gt;.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The country name specified in an address.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Street Address</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The street address. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Region</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The state or province. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Extended Address</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The extended address information?such as apartment or suite number.
                    255 character maximum.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Locality</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The locality/city. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Postal Code</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The postal code. Postal code must be a string of 4-9 alphanumeric
                    characters, optionally separated by a dash or a space. Spaces
                    and hyphens are ignored.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="ExistingShippingAddress">Existing Shipping Address</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Shipping Address Id</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A shipping address associated with a specific customer ID. The
                    maximum number of addresses per customer is 50.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="NewShippingAddress">New Shipping Address</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Store Shipping Address In Vault</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The option that determines whether the shipping address information
                    provided with the transaction should be associated with the customer
                    ID specified. When passed, the payment method will always be
                    stored in the Vault. If there is already a shipping address associated
                    with the customer, this parameter will not replace the existing
                    information; an additional address will be stored instead. You
                    can associate up to 50 addresses with a single customer ID.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">false</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">First Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The first name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Last Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The last name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Company</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Company name. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Code Alpha2</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The &lt;a href="http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2"&gt;ISO
                    3166-1 alpha-2&lt;/a&gt; country code specified in an address.
                    The gateway only accepts &lt;a href="https://developers.braintreepayments.com/reference/general/countries#list-of-countries"&gt;specific
                    alpha-2 values&lt;/a&gt;.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Code Alpha3</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The &lt;a href="http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3"&gt;ISO
                    3166-1 alpha-3&lt;/a&gt; country code specified in an address.
                    The gateway only accepts &lt;a href="https://developers.braintreepayments.com/reference/general/countries#list-of-countries"&gt;specific
                    alpha-3 values&lt;/a&gt;.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Code Numeric</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The &lt;a href="http://en.wikipedia.org/wiki/ISO_3166-1_numeric"&gt;ISO
                    3166-1 numeric&lt;/a&gt; country code specified in an address.
                    The gateway only accepts &lt;a href="https://developers.braintreepayments.com/reference/general/countries#list-of-countries"&gt;specific
                    numeric values&lt;/a&gt;.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Country Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The country name specified in an address.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Street Address</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The street address. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Region</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The state or province. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Extended Address</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The extended address information?such as apartment or suite number.
                    255 character maximum.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Locality</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The locality/city. Maximum 255 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Postal Code</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The postal code. Postal code must be a string of 4-9 alphanumeric
                    characters, optionally separated by a dash or a space. Spaces
                    and hyphens are ignored.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="PaymentMethodToken">Payment Method Token</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Sale Payment Method Token</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">An alphanumeric value that references a specific payment method
                    stored in your Vault. Must be less than or equal to 36 characters.
                    If using a custom integration, you can specify what you want
                    the token to be. If not specified, the gateway will generate
                    one that can be accessed on the result. If using our Drop-in
                    UI with a customer ID to vault payment methods, you can&#8217;t
                    specify your own token.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">x</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="sect2">
          <h3 id="CardDetails">Card Details</h3>
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
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Sale Payment Method Nonce</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">One-time-use reference to payment information provided by your
                    customer, such as a credit card or PayPal account. Can be passed
                    instead of a paymentMethodToken parameter.
                  </p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Three D Secure Required</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>Boolean</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Options for 3D Secure verification. Can only be used when the payment
                    method nonce parameter is present.
                  </p>
                  <p class="tableblock"> Specify whether to require 3D Secure verification to succeed before
                    creating a transaction. Defaults to true for all transactions
                    sent through 3D Secure verification unless you explicitly pass
                    false. For more information, see 3D Secure advanced server-side
                    options.</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">true</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Payment Method Token</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">An alphanumeric value that references a specific payment method
                    stored in your Vault. Must be less than or equal to 36 characters.
                    If using a custom integration, you can specify what you want
                    the token to be. If not specified, the gateway will generate
                    one that can be accessed on the result.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Cardholder Name</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The name associated with the credit card. Must be less than or
                    equal to 175 characters.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Number</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Typically requires The &lt;a href= "https://www.pcisecuritystandards.org/pci_security/completing_self_assessment"&gt;PCI
                    SAQ D compliance&lt;/a&gt; Braintree recommend using paymentMethodNonce
                    to avoid any PCI concerns with raw credit card data being present
                    on your server. The 12-19 digit value on a credit card consisting
                    of a bank identification number (BIN) and primary account number
                    (PAN).</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Cvv</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">A 3 or 4 digit card verification value assigned to a credit card.
                    The CVV will never be stored in the gateway, but it can be provided
                    with one-time requests to verify the card.
                  </p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Expiration Month</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The expiration month of a credit card, formatted MM. May be used
                    with expirationYear, and instead of expirationDate.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
              <tr>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">Expiration Year</p>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <div>
                    <div class="paragraph">
                      <p>String</p>
                    </div>
                  </div>
                </td>
                <td class="tableblock halign-left valign-middle">
                  <p class="tableblock">The two or four digit year associated with a credit card, formatted
                    YYYY or YY. May be used with expirationMonth, and instead of
                    expirationDate.</p>
                </td>
                <td class="tableblock halign-left valign-middle"></td>
                <td class="tableblock halign-left valign-middle"></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>