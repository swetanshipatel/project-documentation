---
title: Braintree Connector API Reference 
keywords: sample
sidebar: braintree_connector_sidebar
permalink: braintree-api-doc.html
folder: braintree_connector
---
Braintree Connector Documentation Reference
===========================================

Braintree Connector

-   [Configurations](#_configurations)
    -   [Config](#config)
-   [Operations](#_operations)
    -   [Customer - Create](#createCustomer)
    -   [PaymentMethod - Create](#createPaymentMethod)
    -   [Customer - Delete](#deleteCustomer)
    -   [PaymentMethod - Delete](#deletePaymentMethod)
    -   [Customer - Find](#findCustomer)
    -   [PaymentMethod - Find](#findPaymentMethod)
    -   [Transaction - Find](#findTransaction)
    -   [Client Token - Get](#getClientToken)
    -   [Transaction - Sale](#sale)
    -   [Customer - Search](#searchCustomer)
    -   [Transaction - Search](#searchTransaction)
    -   [Transaction - Submit For Partial
        Settlement](#submitForPartialSettlement)
    -   [Transaction - Submit For Settlement](#submitForSettlement)
    -   [Customer - Update](#updateCustomer)
    -   [PaymentMethod - Update](#updatePaymentMethod)
    -   [Transaction - Void](#voidTransaction)
-   [Types](#_types)
    -   [Reconnection](#Reconnection)
    -   [Reconnect](#reconnect)
    -   [Reconnect Forever](#reconnect-forever)
    -   [Pooling Profile](#PoolingProfile)
    -   [Expiration Policy](#ExpirationPolicy)
    -   [Payment Card Information](#PaymentCardInformation)
    -   [Payment Method Options](#PaymentMethodOptions)
    -   [Client Token Request Options](#ClientTokenRequestOptions)
    -   [Sale Shipping Details](#SaleShippingDetails)
    -   [Sale Line Item](#SaleLineItem)
    -   [Sale Three D Secure Pass Thru](#SaleThreeDSecurePassThru)
    -   [Transaction Descriptor](#TransactionDescriptor)
    -   [Sale Shared Vault Options](#SaleSharedVaultOptions)
    -   [Sale Options](#SaleOptions)
    -   [Search Customer](#SearchCustomer)
    -   [Customer Information](#CustomerInformation)
    -   [Date Information](#DateInformation)
    -   [Address Information](#AddressInformation)
    -   [Payment Method Information](#PaymentMethodInformation)
    -   [Search Transaction](#SearchTransaction)
    -   [Amount](#Amount)
    -   [Date Range Parameters](#DateRangeParameters)
    -   [Date Range](#DateRange)
    -   [Search Parameters](#SearchParameters)
    -   [Transaction Information](#TransactionInformation)
    -   [Settlement Information](#SettlementInformation)
    -   [Payment Information](#PaymentInformation)
    -   [Billing Address Information](#BillingAddressInformation)
    -   [Shipping Address Information](#ShippingAddressInformation)
    -   [Filter Parameters](#FilterParameters)
    -   [Transaction Type](#TransactionType)
    -   [Transaction Status](#TransactionStatus)
    -   [Transaction Source](#TransactionSource)
    -   [Transaction Card Type](#TransactionCardType)
    -   [Payment Instrument Type](#PaymentInstrumentType)
    -   [Transaction Created Using](#TransactionCreatedUsing)
    -   [Transaction Customer Location](#TransactionCustomerLocation)
    -   [Update Payment Method](#UpdatePaymentMethod)
    -   [Update Payment Method Options](#UpdatePaymentMethodOptions)
    -   [Existing Customer](#ExistingCustomer)
    -   [New Customer](#NewCustomer)
    -   [Existing Billing Address](#ExistingBillingAddress)
    -   [New Billing Address](#NewBillingAddress)
    -   [Existing Shipping Address](#ExistingShippingAddress)
    -   [New Shipping Address](#NewShippingAddress)
    -   [Payment Method Token](#PaymentMethodToken)
    -   [Card Details](#CardDetails)

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

###### Parameters {#_parameters_2}

  Name              Type                                 Description                                                                                                                                                                                                 Default Value   Required
  ----------------- ------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Merchant ID       String                               The merchant account ID                                                                                                                                                                                                     **x** 
  Public Key        String                               Associated public key with merchant account                                                                                                                                                                                 **x** 
  Private Key       String                               Associated private key with merchant account                                                                                                                                                                                **x** 
  Environment       String                               Operation execution environment. Examples: sandbox, development, qa, production                                                                                                                             production       
  Reconnection      [Reconnection](#Reconnection)        When the application is deployed, a connectivity test is performed on all connectors. If set to true, deployment will fail if the test doesn't pass after exhausting the associated reconnection strategy                    
  Pooling Profile   [Pooling Profile](#PoolingProfile)   Characteristics of the connection pool                                                                                                                                                                                       

#### Associated Operations {#_associated_operations}

-   [Customer - Create](#createCustomer)  

-   [PaymentMethod - Create](#createPaymentMethod)  

-   [Customer - Delete](#deleteCustomer)  

-   [PaymentMethod - Delete](#deletePaymentMethod)  

-   [Customer - Find](#findCustomer)  

-   [PaymentMethod - Find](#findPaymentMethod)  

-   [Transaction - Find](#findTransaction)  

-   [Client Token - Get](#getClientToken)  

-   [Transaction - Sale](#sale)  

-   [Customer - Search](#searchCustomer)  

-   [Transaction - Search](#searchTransaction)  

-   [Transaction - Submit For Partial
    Settlement](#submitForPartialSettlement)  

-   [Transaction - Submit For Settlement](#submitForSettlement)  

-   [Customer - Update](#updateCustomer)  

-   [PaymentMethod - Update](#updatePaymentMethod)  

-   [Transaction - Void](#voidTransaction)  

Operations {#_operations}
----------

### Customer - Create {#createCustomer}

`<braintree:create-customer>`

Operation to create customer. You can create a customer by itself, with
a payment method, or with a credit card with a billing address.

#### Parameters {#_parameters_3}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                     Type                                                                                                    Description                                                                                                                                                                                                                                                                                                                                                                                                                          Default Value   Required
  ------------------------ ------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Configuration            String                                                                                                  The name of the configuration to use.                                                                                                                                                                                                                                                                                                                                                                                                                **x** 

  Payment Method           [Payment Card Information](#PaymentCardInformation)                                                     A credit or debit payment method details.                                                                                                                                                                                                                                                                                                                                                                                                             

  Payment Method Options   [Payment Method Options](#PaymentMethodOptions)                                                         Payment method options.                                                                                                                                                                                                                                                                                                                                                                                                                               

  Address                  [Address](https://developers.braintreepayments.com/reference/response/address/java)                     A billing address associated with a specific credit card. The maximum number of addresses per customer is 50.                                                                                                                                                                                                                                                                                                                                         

  ID                       String                                                                                                  A string value that will represent this specific customer in your Vault. 36 character maximum; must be unique within your Vault; valid characters are letters, numbers, -, and \_; the words "all" and "new" currently can't be used. If not specified on creation, the gateway will generate an alphanumeric ID that can be accessed on the result. The generated IDs will never start with a leading 0 and are case insensitive.                    

  First Name               String                                                                                                  The first name. The first name value must be less than or equal to 255 characters.                                                                                                                                                                                                                                                                                                                                                                    

  Last Name                String                                                                                                  The last name. The last name value must be less than or equal to 255 characters.                                                                                                                                                                                                                                                                                                                                                                      

  Email                    String                                                                                                  Email address composed of ASCII characters.                                                                                                                                                                                                                                                                                                                                                                                                           

  Phone                    String                                                                                                  Phone number. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                 

  fax                      String                                                                                                  Fax number. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                   

  Company                  String                                                                                                  Company name. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                 

  Website                  String                                                                                                  Website URL. Must be less than or equal to 255 characters. Website must be well-formed. The URL scheme is optional.                                                                                                                                                                                                                                                                                                                                   

  Token                    String                                                                                                  An alphanumeric value that references a specific payment method stored in your Vault. Must be less than or equal to 36 characters. If using a custom integration, you can specify what you want the token to be. If not specified, the gateway will generate one that can be accessed on the result.                                                                                                                                                  

  Nonce                    String                                                                                                  One-time-use reference to payment information provided by your customer, such as a credit card or PayPal account. When passed on customer create, it creates a payment method associated with the new customer.                                                                                                                                                                                                                                       

  Device Data              String                                                                                                  Customer device information. Pass this value only if you have Advanced Fraud Tools enabled and are adding credit card data to your Vault. Be sure to provide the full string received from the Braintree.                                                                                                                                                                                                                                             

  Custom Fields            Object                                                                                                  A collection of custom field/value pairs. Fields and values must be less than 255 characters. You must [set up each custom field in the Control Panel](https://articles.braintreepayments.com/control-panel/custom-fields?&_ga=1.28588988.1497859415.1565702545#creating-a-custom-field) prior to passing it with a request.                                                                                                                          

  Device Session Id        String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        

  Fraud Merchant Id        String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        

  Risk Data                [RiskData](https://developers.braintreepayments.com/reference/request/customer/create/java#risk_data)   Customer device information, which is sent directly to supported processors for fraud analysis. These fields are automatically populated if using [Advanced Fraud Tools](https://developers.braintreepayments.com/guides/advanced-fraud-tools/overview). Currently only available when processing American Express via Amex Direct.                                                                                                                   

  Target Variable          String                                                                                                  The name of a variable on which the operation's output will be placed                                                                                                                                                                                                                                                                                                                                                                                 

  Target Value             String                                                                                                  An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable                                                                                                                                                                                                                                                                                         \#[payload]      

  Reconnection Strategy    -   [Reconnect](#reconnect)                                                                             A retry strategy in case of connectivity errors                                                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
                           -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations}

-   [Config](#config)  

#### Throws {#_throws}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:CUSTOMER\_NOT\_FOUND  

### PaymentMethod - Create {#createPaymentMethod}

`<braintree:create-payment-method>`

Operation to create payment method for existing customers

#### Parameters {#_parameters_4}

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                     Type                                                                                  Description                                                                                                                                    Default Value   Required
  ------------------------ ------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration            String                                                                                The name of the configuration to use.                                                                                                                          **x** 

  Customer Id              String                                                                                The customer's unique Id                                                                                                                                       **x** 

  Payment Method Nonce     String                                                                                The payment method nonce                                                                                                                                       **x** 

  Payment Method           [Payment Card Information](#PaymentCardInformation)                                   A credit or debit payment method details.                                                                                                                       

  Payment Method Options   [Payment Method Options](#PaymentMethodOptions)                                       Payment method options.                                                                                                                                         

  Billing Address          [Address](https://developers.braintreepayments.com/reference/response/address/java)   A billing address associated with a specific credit card. The maximum number of addresses per customer is 50.                                                   

  Target Variable          String                                                                                The name of a variable on which the operation's output will be placed                                                                                           

  Target Value             String                                                                                An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy    -   [Reconnect](#reconnect)                                                           A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                                                                
                           -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_2}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_2}

-   [Config](#config)  

#### Throws {#_throws_2}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:PAYMENT\_METHOD\_NOT\_FOUND  

### Customer - Delete {#deleteCustomer}

`<braintree:delete-customer>`

Operation to delete customer. You can delete a customer using its ID.
When a customer is deleted, all associated payment methods are also
deleted, and all associated recurring billing subscriptions are
canceled.

#### Parameters {#_parameters_5}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Customer Id             String                                        The customer Id to delete.                                                                                                                                     **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_3}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_3}

-   [Config](#config)  

#### Throws {#_throws_3}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:CUSTOMER\_NOT\_FOUND  

### PaymentMethod - Delete {#deletePaymentMethod}

`<braintree:delete-payment-method>`

#### Parameters {#_parameters_6}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Payment Method Token    String                                        The alphanumeric value that references a specific payment method stored in your Vault.                                                                         **x** 

  Revoke All grants       Boolean                                       When true, all grants of the payment method to other merchants will automatically be revoked. The default value is false.                      false            

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_4}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_4}

-   [Config](#config)  

#### Throws {#_throws_4}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:PAYMENT\_METHOD\_NOT\_FOUND  

### Customer - Find {#findCustomer}

`<braintree:find-customer>`

Find operation look up a single customer using its ID. If the customer
can't be found, it will throw a NotFoundException.

#### Parameters {#_parameters_7}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Customer Id             String                                        The customer Id to find.                                                                                                                                       **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_5}

  ---------- -------------------------
  **Type**   [[Customer]](#Customer)
  ---------- -------------------------

#### For Configurations. {#_for_configurations_5}

-   [Config](#config)  

#### Throws {#_throws_5}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:CUSTOMER\_NOT\_FOUND  

### PaymentMethod - Find {#findPaymentMethod}

`<braintree:find-payment-method>`

#### Parameters {#_parameters_8}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Payment Method Token    String                                        The alphanumeric value that references a specific payment method stored in your Vault.                                                                         **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_6}

  ---------- -----------------------------------
  **Type**   [[PaymentMethod]](#PaymentMethod)
  ---------- -----------------------------------

#### For Configurations. {#_for_configurations_6}

-   [Config](#config)  

#### Throws {#_throws_6}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:PAYMENT\_METHOD\_NOT\_FOUND  

### Transaction - Find {#findTransaction}

`<braintree:find-transaction>`

Find Transaction operation returns the transaction with the specified
Transaction Id

#### Parameters {#_parameters_9}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Transaction Id          String                                        The unique transaction identifier.                                                                                                                             **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_7}

  ---------- ---------------------------------------------------------------------------------------------
  **Type**   [transaction](https://developers.braintreepayments.com/reference/response/transaction/java)
  ---------- ---------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_7}

-   [Config](#config)  

#### Throws {#_throws_7}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

### Client Token - Get {#getClientToken}

`<braintree:get-client-token>`

Operation to generate token which contains all authorization and
configuration information.

#### Parameters {#_parameters_10}

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                           Type                                                         Description                                                                                                                                    Default Value   Required
  ------------------------------ ------------------------------------------------------------ ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration                  String                                                       The name of the configuration to use.                                                                                                                          **x** 

  Client Token Options Request   [Client Token Request Options](#ClientTokenRequestOptions)   Generate token request options.                                                                                                                                 

  Output Mime Type               String                                                       The mime type of the payload that this operation outputs.                                                                                                       

  Target Variable                String                                                       The name of a variable on which the operation's output will be placed                                                                                           

  Target Value                   String                                                       An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy          -   [Reconnect](#reconnect)                                  A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                                             
                                 -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                 
                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                             
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_8}

  ---------- --------
  **Type**   String
  ---------- --------

#### For Configurations. {#_for_configurations_8}

-   [Config](#config)  

#### Throws {#_throws_8}

-   BRAINTREE:CONNECTION\_FAILED  

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:FAILED\_TO\_GENERATE\_TOKEN  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

### Transaction - Sale {#sale}

`<braintree:sale>`

To create a transaction, you must include an amount() and either a
paymentMethodNonce(), a paymentMethodToken(), or a customerId(). Passing
a customerId is equivalent to passing the paymentMethodToken of the
customer's default payment method.

#### Parameters {#_parameters_11}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                              Type                                                         Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          Default Value   Required
  --------------------------------- ------------------------------------------------------------ ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration                     String                                                       The name of the configuration to use.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                **x** 

  Customer                          One of:                                                      SaleCustomer customer Customer details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [Existing Customer](#ExistingCustomer)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [New Customer](#NewCustomer)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Billing Address                   One of:                                                      SaleBillingAddress salebillingAddress Billing address details, either new billing address or existing billing address id                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [Existing Billing Address](#ExistingBillingAddress)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [New Billing Address](#NewBillingAddress)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Shipping Details                  [Sale Shipping Details](#SaleShippingDetails)                SaleShippingDetails saleShippingDetails Shipping amount details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       

  Shipping Address                  One of:                                                      SaleShippingAddress saleshippingAddress Shipping address details, either new shipping address or existing shipping address id                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [Existing Shipping Address](#ExistingShippingAddress)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [New Shipping Address](#NewShippingAddress)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Sale Payment Options              One of:                                                      SalePaymentMode salePaymentOptions SalePaymentMode is either paymentMethodToken or paymentMethodNonce and credit card                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [Payment Method Token](#PaymentMethodToken)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [Card Details](#CardDetails)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Line Item                         [Sale Line Item](#SaleLineItem)                              SaleLineItem lineItem The line items for this transaction. It can include up to 249 line items. If your merchant account has been configured Level 3 processing this field will be passed to processor on your behalf.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                

  3D Secure                         [Sale Three D Secure Pass Thru](#SaleThreeDSecurePassThru)   SaleThreeDSecurePassThru threeDSecure Results of a merchant-performed 3D Secure authentication. You will only need to use these fields if you've performed your own integration with a 3D Secure MPI provider (e.g. Cardinal Centinel).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               

  Descriptor                        [Transaction Descriptor](#TransactionDescriptor)             TransactionDescriptor descriptor                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Shared Payment Options            [Sale Shared Vault Options](#SaleSharedVaultOptions)         SaleSharedVaultOptions sharedVaultOptions Shared Vault data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  Options                           [Sale Options](#SaleOptions)                                 SaleOptions saleOptions Various options for sale transaction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          

  Amount                            String                                                       The billing amount of the request. This value must be greater than 0, and must match the currency format of the merchant account. Can only contain numbers and one decimal point (e.g. x.xx). Can't be greater than the maximum allowed by the processor. Contact us for your specific limit.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        **x** 

  Order Id                          String                                                       Use this field to pass additional information about the transaction. On PayPal transactions, this field maps to the PayPal invoice number. PayPal invoice numbers must be unique in your PayPal business account. Maximum 255 characters or 127 for PayPal transactions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              

  Purchase Order Number             String                                                       A Level 2 field that can be used to pass a purchase order identification value of up to 12 ASCII characters for AIB and 17 ASCII characters for all other processors.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 

  Device Data                       String                                                       Customer device information. Required in the following cases: - When using Advanced Fraud Tools - When creating one-time Vaulted PayPal transactions - When creating Venmo transactions This value will contain a Fraud Merchant ID as the unique, numeric identifier for a Kount account and a Device Session ID as the unique identifier for a customer device. For PayPal and Venmo transactions, this value will also include a PayPal Correlation ID. Provide the full string received from the Braintree client SDK.                                                                                                                                                                                                                                                                                                                                            

  Device Session Id                 String                                                       A unique alphanumeric identifier used by our Advanced Fraud Tools to link a device to transactions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   

  Discount Amount                   String                                                       A Level 3 field that specifies the discount amount that was included in the total transaction amount. It can't be negative, and it does not add to the total transaction amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Tax Exempt                        Boolean                                                      A Level 2 field that indicates whether or not the transaction should be considered eligible for tax exemption. This does not affect the total transaction amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    false            

  Tax Amount                        String                                                       A Level 2 field that specifies the amount of tax that was included in the total transaction amount. The value can't be negative, and in most cases, it must be greater than zero in order to qualify for lower interchange rates. It does not add to the total transaction amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

  Service Fee Amount                String                                                       The portion of a sub-merchant's transaction revenue that is routed to the master merchant account. If set, this value must be greater than or equal to 0, must match the appropriate currency format, and can't exceed the transaction amount. Available to Braintree Marketplace merchants. See charging a service fee and holding funds in escrow on Braintree Marketplace transactions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                            

  Merchant Account Id               String                                                       The merchant account ID used to create a transaction Currency is also determined by merchant account ID. If no merchant account ID is specified, we will use your default merchant account.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

  Custom Fields                     Object                                                       A collection of custom field/value pairs. Fields and values must be formatted as strings or integers. Maximum 255 characters. You must set up each custom field in the Control Panel prior to passing it with a request. Querying this value returns a collection of custom field values stored on the transaction object.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            

  Transaction Source                String                                                       Specifies the source of the transaction. The value passed depends on whether the transaction is initiated by the merchant or the customer. If the transaction is an ecommerce transaction initiated by the customer, no value is passed. Accepted values for merchant-initiated transactions: recurring = Transactions for subsequent recurring payments (e.g. subscriptions with a fixed amount on a predefined schedule). unscheduled = Transactions for unscheduled payments that are not recurring on a predefined schedule or amount (e.g. balance top-up). Formerly merchant. Accepted values for customer-initiated transactions: recurring\_first = Transactions that represent the first in a series of recurring payments or subscription. moto = Transactions that are initiated by the customer via the merchant by mail or telephone.                    

  Previous Network Transaction Id   String                                                       Network transaction identifier issued by the card brand network during a previous transaction. Currently only applicable for Visa payment methods. Visa provides network transaction identifiers to improve authorization approval rates for stored credential transactions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          

  Vault Status                      Enumeration, one of:                                         The option indicates the vaulted status of the externally vaulted payment method. Accepted values: vaulted = Indicates the payment method is already stored on behalf of the customer. will\_vault = Indicates the payment method is intended to be vaulted upon successful processing of the transaction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   WILL\_VAULT                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   VAULTED                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      

  Browser                           String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             

  IP                                String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             

  Target Variable                   String                                                       The name of a variable on which the operation's output will be placed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 

  Target Value                      String                                                       An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         \#[payload]      

  Reconnection Strategy             -   [Reconnect](#reconnect)                                  A retry strategy in case of connectivity errors                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                    -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_9}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_9}

-   [Config](#config)  

#### Throws {#_throws_9}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

### Customer - Search {#searchCustomer}

`<braintree:search-customer>`

Search customer operation returns a collection of Customer response
objects using the search fields

#### Parameters {#_parameters_12}

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                                               Description                                                                                                                                    Default Value   Required
  ----------------------- ------------------------------------------------------------------ ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                                             The name of the configuration to use.                                                                                                                          **x** 

  Customer                [Search Customer](#SearchCustomer)                                 Customer search fields                                                                                                                                          

  Address Fields          Array of [Address Information](#AddressInformation)                Customer address information to search for.                                                                                                                     

  Payment Method Fields   Array of [Payment Method Information](#PaymentMethodInformation)   Payment method information to search for.                                                                                                                       

  Limit                   Number                                                             Limit the number of search results. (0 for no limit)                                                                                           100              

  Target Variable         String                                                             The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                                             An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                                        A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                                            
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                       
                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                            
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_10}

  ---------- ------------------------------------------------------------------------------------------------
  **Type**   Array of [customer](https://developers.braintreepayments.com/reference/response/customer/java)
  ---------- ------------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_10}

-   [Config](#config)  

#### Throws {#_throws_10}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:CUSTOMER\_NOT\_FOUND  

### Transaction - Search {#searchTransaction}

`<braintree:search-transaction>`

Search transaction operation returns a collection of Transaction
response objects using the search fields

#### Parameters {#_parameters_13}

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                            Description                                                                                                                                    Default Value   Required
  ----------------------- ----------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                          The name of the configuration to use.                                                                                                                          **x** 

  Transaction             [Search Transaction](#SearchTransaction)        Search transaction fields                                                                                                                                       

  Date Range Parameter    [Date Range Parameters](#DateRangeParameters)   Date/time range transaction parameters                                                                                                                          

  Search Parameters       [Search Parameters](#SearchParameters)          Search field transaction parameters                                                                                                                             

  Filter Parameters       [Filter Parameters](#FilterParameters)          Multiple values transaction parameters.                                                                                                                         

  Limit                   Number                                          Limit the number of search results. Set 0 for no limit.                                                                                        100              

  Target Variable         String                                          The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                          An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                     A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                         
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                    
                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                         
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_11}

  ---------- ------------------------------------------------------------------------------------------------------
  **Type**   Array of [transaction](https://developers.braintreepayments.com/reference/response/transaction/java)
  ---------- ------------------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_11}

-   [Config](#config)  

#### Throws {#_throws_11}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

### Transaction - Submit For Partial Settlement {#submitForPartialSettlement}

`<braintree:submit-for-partial-settlement>`

Submit for Partial Settlement operation is used to settle multiple
partial amounts against the same authorization. You can create a parent
authorization for the entire order amount and when you?re ready to send
each portion of the order, you can charge the customer for that portion
in a separate child transaction.

#### Parameters {#_parameters_14}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                     Type                                          Description                                                                                                                                                                                                                                                                                          Default Value   Required
  ------------------------ --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration            String                                        The name of the configuration to use.                                                                                                                                                                                                                                                                                **x** 

  Authorized Transaction   String                                        The transaction ID of the parent authorization. You can only submit transactions that have a status of AUTHORIZED for partial settlement.                                                                                                                                                                            **x** 

  Amount                   String                                        An amount to submit for partial settlement against the parent authorization transaction. Must be greater than 0. You can make multiple partial settlement calls as long as the cumulative amount to be partially settled is less than or equal to the amount authorized by the parent transaction.                   **x** 

  Order Id                 String                                        The unique order identifier, used to pass additional information about the transaction.                                                                                                                                                                                                                               

  Target Variable          String                                        The name of a variable on which the operation's output will be placed                                                                                                                                                                                                                                                 

  Target Value             String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable                                                                                                                                                         \#[payload]      

  Reconnection Strategy    -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                              
                           -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                              
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_12}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_12}

-   [Config](#config)  

#### Throws {#_throws_12}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

### Transaction - Submit For Settlement {#submitForSettlement}

`<braintree:submit-for-settlement>`

Submit for Settlement operation explicitly submit the specified
transaction for settlement. It collects the money from an authorized
sale by submitting the transaction for settlement

#### Parameters {#_parameters_15}

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                                                                                                                              Default Value   Required
  ----------------------- --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                                                                                                                                    **x** 

  Transaction Id          String                                        The unique transaction identifier. You can only submit transactions that have a status of authorized for settlement.                                                                                                                                                     **x** 

  Amount                  String                                        An amount to submit for settlement. Must be greater than 0. If you want to settle for an amount that is different from the total authorization amount, you can specify the amount to settle. If you do not specify, the entire amount will be settled.                    

  Order Id                String                                        The unique order identifier, used to pass additional information about the transaction.                                                                                                                                                                                   

  Name                    String                                        The value in the business name field of a customer's statement.                                                                                                                                                                                                           

  Phone                   String                                        The value in the phone number field of a customer's statement.                                                                                                                                                                                                            

  Url                     String                                        The value in the URL/web address field of a customer's statement.                                                                                                                                                                                                         

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                                                                                                                                     

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable                                                                                                             \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                                 
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                                 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_13}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_13}

-   [Config](#config)  

#### Throws {#_throws_13}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

### Customer - Update {#updateCustomer}

`<braintree:update-customer>`

Operation to update customer. To update a customer, use its ID along
with new attributes. The same validations apply as when creating a
customer. Any attribute not passed will remain unchanged.

#### Parameters {#_parameters_16}

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                     Type                                                                                                     Description                                                                                                                                                                                                                                                                                                                                                                                                                          Default Value   Required
  ------------------------ -------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Configuration            String                                                                                                   The name of the configuration to use.                                                                                                                                                                                                                                                                                                                                                                                                                **x** 

  Customer Id              String                                                                                                   The customer Id to update.                                                                                                                                                                                                                                                                                                                                                                                                                           **x** 

  Payment Method           [Payment Card Information](#PaymentCardInformation)                                                      A credit or debit payment method details.                                                                                                                                                                                                                                                                                                                                                                                                             

  Payment Method Options   [Payment Method Options](#PaymentMethodOptions)                                                          Payment method options.                                                                                                                                                                                                                                                                                                                                                                                                                               

  Address                  [Address](https://developers.braintreepayments.com/reference/response/address/java)                      A billing address associated with a specific credit card. The maximum number of addresses per customer is 50.                                                                                                                                                                                                                                                                                                                                         

  ID                       String                                                                                                   A string value that will represent this specific customer in your Vault. 36 character maximum; must be unique within your Vault; valid characters are letters, numbers, -, and \_; the words "all" and "new" currently can't be used. If not specified on creation, the gateway will generate an alphanumeric ID that can be accessed on the result. The generated IDs will never start with a leading 0 and are case insensitive.                    

  First Name               String                                                                                                   The first name. The first name value must be less than or equal to 255 characters.                                                                                                                                                                                                                                                                                                                                                                    

  Last Name                String                                                                                                   The last name. The last name value must be less than or equal to 255 characters.                                                                                                                                                                                                                                                                                                                                                                      

  Email                    String                                                                                                   Email address composed of ASCII characters.                                                                                                                                                                                                                                                                                                                                                                                                           

  Phone                    String                                                                                                   Phone number. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                 

  fax                      String                                                                                                   Fax number. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                   

  Company                  String                                                                                                   Company name. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                 

  Website                  String                                                                                                   Website URL. Must be less than or equal to 255 characters. Website must be well-formed. The URL scheme is optional.                                                                                                                                                                                                                                                                                                                                   

  Token                    String                                                                                                   An alphanumeric value that references a specific payment method stored in your Vault. Must be less than or equal to 36 characters. If using a custom integration, you can specify what you want the token to be. If not specified, the gateway will generate one that can be accessed on the result.                                                                                                                                                  

  Nonce                    String                                                                                                   One-time-use reference to payment information provided by your customer, such as a credit card or PayPal account. When passed on customer create, it creates a payment method associated with the new customer.                                                                                                                                                                                                                                       

  Device Data              String                                                                                                   Customer device information. Pass this value only if you have Advanced Fraud Tools enabled and are adding credit card data to your Vault. Be sure to provide the full string received from the Braintree.                                                                                                                                                                                                                                             

  Custom Fields            Object                                                                                                   A collection of custom field/value pairs. Fields and values must be less than 255 characters. You must [set up each custom field in the Control Panel](https://articles.braintreepayments.com/control-panel/custom-fields?&_ga=1.28588988.1497859415.1565702545#creating-a-custom-field) prior to passing it with a request.                                                                                                                          

  Device Session Id        String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         

  Fraud Merchant Id        String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         

  Risk Data                [Risk Data](https://developers.braintreepayments.com/reference/request/customer/create/java#risk_data)   Customer device information, which is sent directly to supported processors for fraud analysis. These fields are automatically populated if using [Advanced Fraud Tools](https://developers.braintreepayments.com/guides/advanced-fraud-tools/overview). Currently only available when processing American Express via Amex Direct.                                                                                                                   

  Target Variable          String                                                                                                   The name of a variable on which the operation's output will be placed                                                                                                                                                                                                                                                                                                                                                                                 

  Target Value             String                                                                                                   An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable                                                                                                                                                                                                                                                                                         \#[payload]      

  Reconnection Strategy    -   [Reconnect](#reconnect)                                                                              A retry strategy in case of connectivity errors                                                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                           -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_14}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_14}

-   [Config](#config)  

#### Throws {#_throws_14}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:CUSTOMER\_NOT\_FOUND  

### PaymentMethod - Update {#updatePaymentMethod}

`<braintree:update-payment-method>`

#### Parameters {#_parameters_17}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                            Type                                                                                  Description                                                                                                                                                                  Default Value   Required
  ------------------------------- ------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration                   String                                                                                The name of the configuration to use.                                                                                                                                                        **x** 

  Billing Address                 [Address](https://developers.braintreepayments.com/reference/response/address/java)   A billing address associated with a specific customer ID. It can be further associated with a specific payment method. The maximum number of addresses per customer is 50.                    

  Update Payment Method Details   [Update Payment Method](#UpdatePaymentMethod)                                         Payment method details                                                                                                                                                                       **x** 

  Updatepayment Method            [Payment Card Information](#PaymentCardInformation)                                   A credit or debit payment method details.                                                                                                                                                     

  Update Payment Method Options   [Update Payment Method Options](#UpdatePaymentMethodOptions)                          Payment method options.                                                                                                                                                                       

  Target Variable                 String                                                                                The name of a variable on which the operation's output will be placed                                                                                                                         

  Target Value                    String                                                                                An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable                                 \#[payload]      

  Reconnection Strategy           -   [Reconnect](#reconnect)                                                           A retry strategy in case of connectivity errors                                                                                                                                               
                                                                                                                                                                                                                                                                                                                     
                                  -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                     
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_15}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_15}

-   [Config](#config)  

#### Throws {#_throws_15}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

-   BRAINTREE:PAYMENT\_METHOD\_NOT\_FOUND  

### Transaction - Void {#voidTransaction}

`<braintree:void-transaction>`

Void Transaction operation undo a transaction before it settles. It
cancels the transfer of funds before the transaction settles. You can
only void transactions that have a status() of: AUTHORIZED,
SUBMITTED\_FOR\_SETTLEMENT, SETTLEMENT\_PENDING (only for certain PayPal
transactions)

#### Parameters {#_parameters_18}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Name                    Type                                          Description                                                                                                                                    Default Value   Required
  ----------------------- --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Configuration           String                                        The name of the configuration to use.                                                                                                                          **x** 

  Transaction Id          String                                        The unique transaction identifier.                                                                                                                             **x** 

  Target Variable         String                                        The name of a variable on which the operation's output will be placed                                                                                           

  Target Value            String                                        An expression that will be evaluated against the operation's output and the outcome of that expression will be stored in the target variable   \#[payload]      

  Reconnection Strategy   -   [Reconnect](#reconnect)                   A retry strategy in case of connectivity errors                                                                                                                 
                                                                                                                                                                                                                                       
                          -   [Reconnect Forever](#reconnect-forever)                                                                                                                                                                  
                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Output {#_output_16}

  ---------- ------------------------------------------------------------------------------------------
  **Type**   [Result](https://developers.braintreepayments.com/reference/general/result-objects/java)
  ---------- ------------------------------------------------------------------------------------------

#### For Configurations. {#_for_configurations_16}

-   [Config](#config)  

#### Throws {#_throws_16}

-   BRAINTREE:EXECUTION  

-   BRAINTREE:CONNECTIVITY  

-   BRAINTREE:AUTHORIZATION  

-   BRAINTREE:RETRY\_EXHAUSTED  

-   BRAINTREE:AUTHENTICATION  

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

### Payment Card Information {#PaymentCardInformation}

  Field                Type     Description                                                                                                                                                                                                                                                                                                                                                                                               Default Value   Required
  -------------------- -------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Billing Address Id   String   Provide billing address Id to use existing billing address with payment method.                                                                                                                                                                                                                                                                                                                                           
  Device Data          String   Customer device information. Pass this value only if you have Advanced Fraud Tools enabled and are adding credit card data to your Vault.                                                                                                                                                                                                                                                                                 
  Cardholder Name      String   The name associated with the credit card. Must be less than or equal to 175 characters.                                                                                                                                                                                                                                                                                                                                   
  Number               String   Typically requires The \<a href= "https://www.pcisecuritystandards.org/pci\_security/completing\_self\_assessment"\>PCI SAQ D compliance\</a\> Braintree recommend using paymentMethodNonce to avoid any PCI concerns with raw credit card data being present on your server. The 12-19 digit value on a credit card consisting of a bank identification number (BIN) and primary account number (PAN).                   
  Cvv                  String   A 3 or 4 digit card verification value assigned to a credit card. The CVV will never be stored in the gateway, but it can be provided with one-time requests to verify the card.                                                                                                                                                                                                                                          
  Expiration Month     String   The expiration month of a credit card, formatted MM. May be used with expirationYear, and instead of expirationDate.                                                                                                                                                                                                                                                                                                      
  Expiration Year      String   The two or four digit year associated with a credit card, formatted YYYY or YY. May be used with expirationMonth, and instead of expirationDate.                                                                                                                                                                                                                                                                          

### Payment Method Options {#PaymentMethodOptions}

  Field                              Type      Description                                                                                                                                                                                                                                                                                            Default Value   Required
  ---------------------------------- --------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Fail On Duplicate Payment Method   Boolean   If this option is passed and the same payment method has already been added to the Vault for any customer, the request will fail. This option will be ignored for PayPal, Pay with Venmo, Apple Pay, Google Pay, and Samsung Pay payment methods.                                                      false           
  Token                              String    An alphanumeric value that references a specific payment method stored in your Vault. Must be less than or equal to 36 characters. If using a custom integration, you can specify what you want the token to be. If not specified, the gateway will generate one that can be accessed on the result.                   
  Make Default                       Boolean   This option makes the specified payment method the default for the customer.                                                                                                                                                                                                                           false           
  Verification Amount                String    Specify a non-negative amount that you want to use to verify a card. If you do not pass this option, the gateway will automatically use a verification amount of \$0 or \$1, depending on the processor and/or card type.                                                                                              
  Verification Merchant Account Id   String    Specify the merchant account ID that you want to use to verify a card. Can’t be a Braintree Marketplace sub-merchant account.                                                                                                                                                                                          
  Verify Card                        Boolean   If the payment method is a credit card, this option prompts the gateway to verify the card’s number and expiration date. It also verifies the AVS and CVV information if you’ve enabled AVS and CVV rules.                                                                                             false           

### Client Token Request Options {#ClientTokenRequestOptions}

  Field                              Type      Description                                                                                                                                                                                                                                                                                                    Default Value   Required
  ---------------------------------- --------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Customer Id                        String    A string value representing an existing customer in your Vault. Passing this option allows customers to manage their vaulted payment methods via the Drop-in UI                                                                                                                                                                
  Merchant Account Id                String    Specify the merchant account ID that you want to use to generate the client token. If no merchant account ID is specified, Braintree will use your default merchant account.                                                                                                                                                   
  Version                            Number                                                                                                                                                                                                                                                                                                                                   
  Fail On Duplicate Payment Method   Boolean   If this option is passed and the same payment method has already been added to the Vault for any customer, the request will fail. This can only be passed if a customerId is passed as well. This option will be ignored for PayPal, Pay with Venmo, Apple Pay, Google Pay, and Samsung Pay payment methods.   false           
  Make Default                       Boolean   This option makes the specified payment method the default for the customer. This can only be passed if a customer\_id is passed as well.                                                                                                                                                                      false           
  Verify Card                        Boolean   If the payment method is a credit card, this option prompts the gateway to verify the card’s number and expiration date. It also verifies the AVS and CVV information if you’ve enabled AVS and CVV rules. This option can only be passed if a customerId is passed as well.                                   false           

### Sale Shipping Details {#SaleShippingDetails}

  Field                    Type     Description                                                                                                                                              Default Value   Required
  ------------------------ -------- -------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Shipping Amount          String   A Level 3 field that specifies the shipping cost on the entire transaction. It can’t be negative, and it does not add to the total transaction amount.                   
  Ships From Postal Code   String   A Level 3 field that specifies the postal code of the shipping location.                                                                                                 

### Sale Line Item {#SaleLineItem}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field             Type                   Description                                                                                                                                                                                                                                                                                                           Default Value   Required
  ----------------- ---------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Commodity Code    String                 Code used to classify items purchased and track the total amount spent across various categories of products and services. Different corporate purchasing organizations may use different standards, but the United Nations Standard Products and Services Code (UNSPSC) is frequently used. Maximum 12 characters.                   

  Description       String                 Item description. Maximum 127 characters.                                                                                                                                                                                                                                                                                             

  Discount Amount   Number                 Discount amount for the line item. Can include up to 2 decimal places. This value can’t be negative.                                                                                                                                                                                                                                  

  Kind              Enumeration, one of:   Indicates whether the line item is a debit (sale) or credit (refund) to the customer. Accepted values: - "debit" - "credit"                                                                                                                                                                                                           x
                                                                                                                                                                                                                                                                                                                                                                                 
                    -   DEBIT                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                 
                    -   CREDIT                                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                                                 
                    -   UNRECOGNIZED                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                                                                 

  Line Name         String                 Item name. Maximum 35 characters, or 127 characters for PayPal transactions.                                                                                                                                                                                                                                                          x

  Product Code      String                 Product or UPC code for the item. Maximum 12 characters, or 127 characters for PayPal transactions.                                                                                                                                                                                                                                   

  Quantity          Number                 Number of units of the item purchased. Can include up to 4 decimal places. This value can’t be negative or zero.                                                                                                                                                                                                                      x

  Tax Amount        Number                 Tax amount for the line item. Can include up to 2 decimal places. This value can’t be negative.                                                                                                                                                                                                                                       

  Total Amount      Number                 Quantity x unit amount. Can include up to 2 decimal places.                                                                                                                                                                                                                                                                           x

  Unit Amount       Number                 Per-unit price of the item. Maximum 4 decimal places, or 2 decimal places for PayPal transactions. This value can’t be negative or zero.                                                                                                                                                                                              x

  Unit Of Measure   String                 The unit of measure or the unit of measure code. Maximum 12 characters.                                                                                                                                                                                                                                                               

  Unit Tax Amount   Number                 Per-unit tax price of the item. Can include up to 2 decimal places. This value can’t be negative or zero.                                                                                                                                                                                                                             

  Url               String                 The URL to product information.                                                                                                                                                                                                                                                                                                       
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Sale Three D Secure Pass Thru {#SaleThreeDSecurePassThru}

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                    Type     Description                                                                                                                                                                                                                                                                                  Default Value   Required
  ------------------------ -------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Cavv                     String   Cardholder authentication verification value or CAVV. The main encrypted message issuers and card networks use to verify authentication has occurred. Mastercard uses an AVV message and American Express uses an AEVV message, each of which should also be passed in the cavv parameter.                   

  Ds Transaction Id        String   Transaction identifier resulting from 3D Secure 2 authentication. This field must be supplied for Mastercard Identity Check.                                                                                                                                                                                 

  Eci Flag                 String   The value of the electronic commerce indicator (ECI) flag, which indicates the outcome of the 3DS authentication. Accepted values for Mastercard: 00 = Failed or not attempted 01 = Attempted 02 = Success                                                                                                   x
                                                                                                                                                                                                                                                                                                                                                 
                                    Accepted values for all other card brands: 07 = Failed or not attempted 06 = Attempted 05 = Success                                                                                                                                                                                                          

  Three D Secure Version   String   The version of 3D Secure authentication used for the transaction. Required on Visa and Mastercard authentications. Must be composed of digits separated by periods (e.g. 1.0.2).                                                                                                                             

  Xid                      String   Transaction identifier resulting from 3D Secure authentication. Uniquely identifies the transaction and sometimes required in the authorization message. Must be base64-encoded. This field will no longer be used in 3D Secure 2 authentications.                                                           
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Transaction Descriptor {#TransactionDescriptor}

  Field   Type     Description                                                         Default Value   Required
  ------- -------- ------------------------------------------------------------------- --------------- ----------
  Name    String   The value in the business name field of a customer’s statement.                     
  Phone   String   The value in the phone number field of a customer’s statement.                      
  Url     String   The value in the URL/web address field of a customer’s statement.                   

### Sale Shared Vault Options {#SaleSharedVaultOptions}

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                              Type                                 Description                                                                                                                                                                                                                                                                                                                                                                                                          Default Value   Required
  ---------------------------------- ------------------------------------ -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Shared Customer Id                 String                               For Shared Vault only                                                                                                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                          The ID of a customer belonging to the OAuth application owner. If no sharedPaymentMethodToken() is specified, the customer’s default payment method will be used.                                                                                                                                                                                                                                                                    

  Shared Billing Address Id          String                               For Shared Vault only The ID of an address belonging to the OAuth application owner. If used in conjunction with a sharedCustomerId(), must belong to the specified customer.                                                                                                                                                                                                                                                        

  Shared Payment Method Mode         Enumeration, one of:                 sharedPaymentMethodNonce ------------------------- For Shared Vault only A payment method nonce belonging to the OAuth application owner. These payment method nonces can be credit cards or channel-initiated PayPal Billing Agreements that have been executed. Mutually exclusive with sharedPaymentMethodToken().                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                     -   SHARED\_PAYMENT\_METHOD\_NONCE   sharedPaymentMethodToken ------------------------- For Shared Vault only The token of a payment method belonging to the OAuth application owner. Mutually exclusive with sharedPaymentMethodNonce(). If no sharedCustomerId() is explicitly specified, the customer that owns the payment method is implicitly specified. If used in conjunction with a sharedCustomerId(), must belong to the specified customer.                   
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                     -   SHARED\_PAYMENT\_METHOD\_TOKEN                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               

  Shared Payment Method Mode Value   String                               Value of sharedPaymentMethodNonce OR sharedPaymentMethodToken                                                                                                                                                                                                                                                                                                                                                                        

  Shared Shipping Address Id         String                               For Shared Vault only                                                                                                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                          The ID of an address belonging to the OAuth application owner. If used in conjunction with a sharedCustomerId(), must belong to the specified customer.                                                                                                                                                                                                                                                                              
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Sale Options {#SaleOptions}

  Field                          Type      Description                                                                                                                                                                                                                                                                                                                                                                                                                                                     Default Value   Required
  ------------------------------ --------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Hold In Escrow                 Boolean   For Braintree Marketplace merchants only. This value specifies whether a transaction is held in escrow. See Escrow for more detail.                                                                                                                                                                                                                                                                                                                             false           
  Paypal Custom Field            String    Variable passed directly to PayPal via the API for your own tracking purposes. Customers do not see this value, but you can see it in reports from your PayPal console. It also appears in the Braintree Control Panel on the Transaction Detail page of the associated PayPal transaction, and in the CSV file of downloaded transaction searches. Unlike Braintree custom fields, this field does not need to be configured in the Braintree Control Panel.                   
  Paypal Description             String    Description of the transaction that is displayed to customers in PayPal email receipts. Max 127 characters.                                                                                                                                                                                                                                                                                                                                                                     
  Skip Advanced Fraud Checking   Boolean   Prevents the transaction from being sent to Kount for evaluation as part of Advanced Fraud Tools checks. Use with caution ? once you’ve skipped checks for a transaction, it is not possible to run them retroactively.                                                                                                                                                                                                                                         false           
  Skip Avs                       Boolean   Skip AVS checks for the transaction. Will result in a processor response code of B for avsPostalCodeResponseCode and avsStreetAddressResponseCode, and nil for avsErrorResponseCode. Use with caution ? once you’ve skipped checks for a transaction, it is not possible to run them retroactively.                                                                                                                                                             false           
  Skip Cvv                       Boolean   Skip CVV checks for the transaction. Will result in a processor response code of B for cvvResponseCode. Use with caution ? once you’ve skipped checks for a transaction, it is not possible to run them retroactively.                                                                                                                                                                                                                                          false           
  Store In Vault On Success      Boolean   The option that determines whether the payment method associated with the successful transaction should be stored in the Vault.                                                                                                                                                                                                                                                                                                                                 false           
  Store In Vault                 Boolean   The option that determines whether the payment method should be stored in the Vault, regardless of the transaction’s success.                                                                                                                                                                                                                                                                                                                                   false           
  Submit For Settlement          Boolean   The option that determines whether an authorized transaction is submitted for settlement.                                                                                                                                                                                                                                                                                                                                                                       false           
  Venmo Profile Id               String    Specify which Venmo business profile to use for a transaction.                                                                                                                                                                                                                                                                                                                                                                                                                  

### Search Customer {#SearchCustomer}

  Field             Type                                                    Description                                  Default Value   Required
  ----------------- ------------------------------------------------------- -------------------------------------------- --------------- ----------
  Customer Fields   Array of [Customer Information](#CustomerInformation)   Customer fields information to search for.                   
  Created At        [Date Information](#DateInformation)                    The date/time the customer was created.                      
  Ids               Array of String                                         A list of customer IDs to search for.                        

### Customer Information {#CustomerInformation}

  -----------------------------------------------------------------------------------------
  Field           Type                   Description             Default Value   Required
  --------------- ---------------------- ----------------------- --------------- ----------
  Field           Enumeration, one of:   Search customer field                   x
                                                                                 
                  -   FIRST\_NAME                                                
                                                                                 
                  -   LAST\_NAME                                                 
                                                                                 
                  -   CUSTOMER\_ID                                               
                                                                                 
                  -   EMAIL                                                      
                                                                                 
                  -   PHONE                                                      
                                                                                 
                  -   FAX                                                        
                                                                                 
                  -   COMPANY                                                    
                                                                                 
                  -   WEBSITE                                                    
                                                                                 
                                                                                 

  Operator        Enumeration, one of:   Search operator                         x
                                                                                 
                  -   IS                                                         
                                                                                 
                  -   IS\_NOT                                                    
                                                                                 
                  -   STARTS\_WITH                                               
                                                                                 
                  -   ENDS\_WITH                                                 
                                                                                 
                  -   CONTAINS                                                   
                                                                                 
                                                                                 

  Search String   String                 Search value                            x
  -----------------------------------------------------------------------------------------

### Date Information {#DateInformation}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field      Type                               Description                                                                                                                               Default Value   Required
  ---------- ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Operator   Enumeration, one of:               Operator for Date Range parameter for search transaction                                                                                                  x
                                                                                                                                                                                                          
             -   BETWEEN                                                                                                                                                                                  
                                                                                                                                                                                                          
             -   GREATER\_THAN\_OR\_EQUAL\_TO                                                                                                                                                             
                                                                                                                                                                                                          
             -   LESS\_THAN\_OR\_EQUAL\_TO                                                                                                                                                                
                                                                                                                                                                                                          
                                                                                                                                                                                                          

  Date       String                             Date in search transaction. For BETWEEN operator, it is 'From Date'. Provide date in dd-MM-yyyy HH:mm format. Example: 25-12-2019 13:59                   x

  Max Date   String                             It is only required for BETWEEN operator. Provide date in dd-MM-yyyy HH:mm format. Example: 25-12-2019 13:59                                              
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Address Information {#AddressInformation}

  -----------------------------------------------------------------------------------------
  Field           Type                    Description            Default Value   Required
  --------------- ----------------------- ---------------------- --------------- ----------
  Field           Enumeration, one of:    Search address field                   x
                                                                                 
                  -   FIRST\_NAME                                                
                                                                                 
                  -   LAST\_NAME                                                 
                                                                                 
                  -   STREET\_ADDRESS                                            
                                                                                 
                  -   EXTENDED\_ADDRESS                                          
                                                                                 
                  -   LOCALITY                                                   
                                                                                 
                  -   REGION                                                     
                                                                                 
                  -   POSTAL\_CODE                                               
                                                                                 
                  -   COUNTRY\_NAME                                              
                                                                                 
                                                                                 

  Operator        Enumeration, one of:    Search operator                        x
                                                                                 
                  -   IS                                                         
                                                                                 
                  -   IS\_NOT                                                    
                                                                                 
                  -   STARTS\_WITH                                               
                                                                                 
                  -   ENDS\_WITH                                                 
                                                                                 
                  -   CONTAINS                                                   
                                                                                 
                                                                                 

  Search String   String                  Search value                           x
  -----------------------------------------------------------------------------------------

### Payment Method Information {#PaymentMethodInformation}

  -----------------------------------------------------------------------------------------------------
  Field           Type                         Description                   Default Value   Required
  --------------- ---------------------------- ----------------------------- --------------- ----------
  Field           Enumeration, one of:         Search payment method field                   x
                                                                                             
                  -   CARDHOLDER\_NAME                                                       
                                                                                             
                  -   PAYMENT\_METHOD\_TOKEN                                                 
                                                                                             
                  -   PAYPAL\_ACCOUNT\_EMAIL                                                 
                                                                                             
                  -   CREDIT\_CARD\_NUMBER                                                   
                                                                                             
                  -   EXPIRATION\_DATE                                                       
                                                                                             
                                                                                             

  Operator        Enumeration, one of:         Search operator                               x
                                                                                             
                  -   IS                                                                     
                                                                                             
                  -   IS\_NOT                                                                
                                                                                             
                  -   STARTS\_WITH                                                           
                                                                                             
                  -   ENDS\_WITH                                                             
                                                                                             
                  -   CONTAINS                                                               
                                                                                             
                                                                                             

  Search String   String                       Search value                                  x
  -----------------------------------------------------------------------------------------------------

### Search Transaction {#SearchTransaction}

  Field                     Type                Description                                                                    Default Value   Required
  ------------------------- ------------------- ------------------------------------------------------------------------------ --------------- ----------
  Amount                    [Amount](#Amount)   The amount of the transaction. The amount must be formatted like xx or x.xx.                   
  Ids                       Array of String     The list of transaction IDs to search for.                                                     
  Merchant Account Ids      Array of String     The merchant account IDs associated with transactions.                                         
  Transaction Is A Refund   Boolean             Specifies whether transaction is a refund                                      false           

### Amount {#Amount}

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field        Type                               Description                                                                                                                                       Default Value   Required
  ------------ ---------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Operator     Enumeration, one of:               Operator for Range parameter for search transaction.                                                                                                              x
                                                                                                                                                                                                                    
               -   IS                                                                                                                                                                                               
                                                                                                                                                                                                                    
               -   BETWEEN                                                                                                                                                                                          
                                                                                                                                                                                                                    
               -   GREATER\_THAN\_OR\_EQUAL\_TO                                                                                                                                                                     
                                                                                                                                                                                                                    
               -   LESS\_THAN\_OR\_EQUAL\_TO                                                                                                                                                                        
                                                                                                                                                                                                                    
                                                                                                                                                                                                                    

  Min Amount   String                             Transaction amount in search transaction. For BETWEEN operator, it is the minimum amount. Provide amount in x.xx format. Example: 5000.00                         x

  Max Amount   String                             It is only required for BETWEEN operator and it is the maximum amount with between operator. Provide maxAmount in x.xx format. Example: 5000.00                   
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Date Range Parameters {#DateRangeParameters}

  Field                         Type                       Description                                                                                              Default Value   Required
  ----------------------------- -------------------------- -------------------------------------------------------------------------------------------------------- --------------- ----------
  Authorization Expired At      [Date Range](#DateRange)   The date/time the transaction’s authorization expired.                                                                   
  Authorized At                 [Date Range](#DateRange)   The date/time the transaction was authorized.                                                                            
  Transaction Created At        [Date Range](#DateRange)   The date/time at which the transaction was created.                                                                      
  Disbursement Date             [Date Range](#DateRange)   The date the transaction was disbursed to your bank account. This field does not include a time value.                   
  Dispute Date                  [Date Range](#DateRange)   The date the transaction was disputed. This field does not include a time value.                                         
  Failed At                     [Date Range](#DateRange)   The date/time the transaction failed.                                                                                    
  Gateway Rejected At           [Date Range](#DateRange)   The date/time the transaction was rejected by the gateway.                                                               
  Processor Declined At         [Date Range](#DateRange)   The date/time the transaction was declined by the processor                                                              
  Settled At                    [Date Range](#DateRange)   The date/time the transaction finished settling.                                                                         
  Submitted For Settlement At   [Date Range](#DateRange)   The date/time the transaction was submitted for settlement.                                                              
  Voided At                     [Date Range](#DateRange)   The date/time the transaction was voided.                                                                                

### Date Range {#DateRange}

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field      Type                               Description                                                                                                                               Default Value   Required
  ---------- ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Operator   Enumeration, one of:               Operator for Date Range parameter for search transaction.                                                                                                 x
                                                                                                                                                                                                          
             -   BETWEEN                                                                                                                                                                                  
                                                                                                                                                                                                          
             -   GREATER\_THAN\_OR\_EQUAL\_TO                                                                                                                                                             
                                                                                                                                                                                                          
             -   LESS\_THAN\_OR\_EQUAL\_TO                                                                                                                                                                
                                                                                                                                                                                                          
                                                                                                                                                                                                          

  Date       String                             Date in search transaction. For BETWEEN operator, it is 'From Date'. Provide date in dd-MM-yyyy HH:mm format. Example: 25-12-2019 13:59                   x

  To Date    String                             It is only required for BETWEEN operator and it is 'To Date'. Provide date in dd-MM-yyyy HH:mm format. Example: 25-12-2019 13:59                          
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Search Parameters {#SearchParameters}

  Field                           Type                                                                   Description                                      Default Value   Required
  ------------------------------- ---------------------------------------------------------------------- ------------------------------------------------ --------------- ----------
  Transaction Informations        Array of [Transaction Information](#TransactionInformation)            Transaction information parameters.                              
  Settlement Informations         Array of [Settlement Information](#SettlementInformation)              Parameters for Transaction settlement.                           
  Payment Informations            Array of [Payment Information](#PaymentInformation)                    Parameters for Transaction’s Payment Method.                     
  Customer Informations           Array of [Customer Information](#CustomerInformation)                  Customer information parameters.                                 
  Billing Address Informations    Array of [Billing Address Information](#BillingAddressInformation)     Parameters for Transaction’s billing address.                    
  Shipping Address Informations   Array of [Shipping Address Information](#ShippingAddressInformation)   Parameters for Transaction’s shipping address.                   

### Transaction Information {#TransactionInformation}

  -----------------------------------------------------------------------------------------------------------------
  Field           Type                                 Description                       Default Value   Required
  --------------- ------------------------------------ --------------------------------- --------------- ----------
  Field           Enumeration, one of:                 Search fields for Transaction                     x
                                                                                                         
                  -   TRANSACTION\_ID                                                                    
                                                                                                         
                  -   CURRENCY                                                                           
                                                                                                         
                  -   ORDER\_ID                                                                          
                                                                                                         
                  -   PROCESSOR\_AUTHORIZATION\_CODE                                                     
                                                                                                         
                                                                                                         

  Operator        Enumeration, one of:                 Search operator for Transaction                   x
                                                                                                         
                  -   IS                                                                                 
                                                                                                         
                  -   IS\_NOT                                                                            
                                                                                                         
                  -   STARTS\_WITH                                                                       
                                                                                                         
                  -   ENDS\_WITH                                                                         
                                                                                                         
                  -   CONTAINS                                                                           
                                                                                                         
                                                                                                         

  Search String   String                               Search value for transaction                      x
  -----------------------------------------------------------------------------------------------------------------

### Settlement Information {#SettlementInformation}

  --------------------------------------------------------------------------------------------------------------------
  Field           Type                        Description                                   Default Value   Required
  --------------- --------------------------- --------------------------------------------- --------------- ----------
  Field           Enumeration, one of:        Search field for Settlement Information                       x
                                                                                                            
                  -   SETTLEMENT\_BATCH\_ID                                                                 
                                                                                                            
                                                                                                            

  Operator        Enumeration, one of:        Search operatior for Settlement Information                   x
                                                                                                            
                  -   IS                                                                                    
                                                                                                            
                  -   IS\_NOT                                                                               
                                                                                                            
                  -   STARTS\_WITH                                                                          
                                                                                                            
                  -   ENDS\_WITH                                                                            
                                                                                                            
                  -   CONTAINS                                                                              
                                                                                                            
                                                                                                            

  Search String   String                      Search value for Settlement Information                       x
  --------------------------------------------------------------------------------------------------------------------

### Payment Information {#PaymentInformation}

  -------------------------------------------------------------------------------------------------------------------------
  Field           Type                                     Description                           Default Value   Required
  --------------- ---------------------------------------- ------------------------------------- --------------- ----------
  Field           Enumeration, one of:                     Search fields for Payment Methods                     x
                                                                                                                 
                  -   CARDHOLDER\_NAME                                                                           
                                                                                                                 
                  -   CREDIT\_CARD\_UNIQUE\_IDENTIFIER                                                           
                                                                                                                 
                  -   PAYMENT\_METHOD\_TOKEN                                                                     
                                                                                                                 
                  -   PAYPAL\_ACCOUNT\_PAYER\_EMAIL                                                              
                                                                                                                 
                  -   PAYPAL\_ACCOUNT\_PAYMENT\_ID                                                               
                                                                                                                 
                  -   PAYPAL\_ACCOUNT\_AUTHORIZATION\_ID                                                         
                                                                                                                 
                  -   EXPIRATION\_DATE                                                                           
                                                                                                                 
                  -   CREDIT\_CARD\_NUMBER                                                                       
                                                                                                                 
                                                                                                                 

  Operator        Enumeration, one of:                     Search operator for Payment Methods                   x
                                                                                                                 
                  -   IS                                                                                         
                                                                                                                 
                  -   IS\_NOT                                                                                    
                                                                                                                 
                  -   STARTS\_WITH                                                                               
                                                                                                                 
                  -   ENDS\_WITH                                                                                 
                                                                                                                 
                  -   CONTAINS                                                                                   
                                                                                                                 
                                                                                                                 

  Search String   String                                                                                         x
  -------------------------------------------------------------------------------------------------------------------------

### Billing Address Information {#BillingAddressInformation}

  -----------------------------------------------------------------------------------------------------------------
  Field           Type                             Description                           Default Value   Required
  --------------- -------------------------------- ------------------------------------- --------------- ----------
  Field           Enumeration, one of:             Search fields for Billing Address                     x
                                                                                                         
                  -   BILLING\_FIRST\_NAME                                                               
                                                                                                         
                  -   BILLING\_LAST\_NAME                                                                
                                                                                                         
                  -   BILLING\_COMPANY                                                                   
                                                                                                         
                  -   BILLING\_STREET\_ADDRESS                                                           
                                                                                                         
                  -   BILLING\_EXTENDED\_ADDRESS                                                         
                                                                                                         
                  -   BILLING\_LOCATITY                                                                  
                                                                                                         
                  -   BILLING\_REGION                                                                    
                                                                                                         
                  -   BILLING\_POSTAL\_CODE                                                              
                                                                                                         
                  -   BILLING\_COUNTRY\_NAME                                                             
                                                                                                         
                                                                                                         

  Operator        Enumeration, one of:             Search operator for billing address                   x
                                                                                                         
                  -   IS                                                                                 
                                                                                                         
                  -   IS\_NOT                                                                            
                                                                                                         
                  -   STARTS\_WITH                                                                       
                                                                                                         
                  -   ENDS\_WITH                                                                         
                                                                                                         
                  -   CONTAINS                                                                           
                                                                                                         
                                                                                                         

  Search String   String                           Search value for billing address                      x
  -----------------------------------------------------------------------------------------------------------------

### Shipping Address Information {#ShippingAddressInformation}

  -------------------------------------------------------------------------------------------------------------------
  Field           Type                              Description                            Default Value   Required
  --------------- --------------------------------- -------------------------------------- --------------- ----------
  Field           Enumeration, one of:              Search fields for Shipping Address                     x
                                                                                                           
                  -   SHIPPING\_FIRST\_NAME                                                                
                                                                                                           
                  -   SHIPPING\_LAST\_NAME                                                                 
                                                                                                           
                  -   SHIPPING\_COMPANY                                                                    
                                                                                                           
                  -   SHIPPING\_STREET\_ADDRESS                                                            
                                                                                                           
                  -   SHIPPING\_EXTENDED\_ADDRESS                                                          
                                                                                                           
                  -   SHIPPING\_LOCATITY                                                                   
                                                                                                           
                  -   SHIPPING\_REGION                                                                     
                                                                                                           
                  -   SHIPPING\_POSTAL\_CODE                                                               
                                                                                                           
                  -   SHIPPING\_COUNTRY\_NAME                                                              
                                                                                                           
                                                                                                           

  Operator        Enumeration, one of:              Search operator for Shipping Address                   x
                                                                                                           
                  -   IS                                                                                   
                                                                                                           
                  -   IS\_NOT                                                                              
                                                                                                           
                  -   STARTS\_WITH                                                                         
                                                                                                           
                  -   ENDS\_WITH                                                                           
                                                                                                           
                  -   CONTAINS                                                                             
                                                                                                           
                                                                                                           

  Search String   String                            Search value for shipping address                      x
  -------------------------------------------------------------------------------------------------------------------

### Filter Parameters {#FilterParameters}

  Field                        Type                                                                     Description                                                          Default Value   Required
  ---------------------------- ------------------------------------------------------------------------ -------------------------------------------------------------------- --------------- ----------
  Types                        Array of [Transaction Type](#TransactionType)                            The list of transaction types to search for.                                         
  Statuses                     Array of [Transaction Status](#TransactionStatus)                        The list of statuses to search for.                                                  
  Transaction Sources          Array of [Transaction Source](#TransactionSource)                        The list of sources of transaction i.e how transaction was created                   
  Transaction Card Types       Array of [Transaction Card Type](#TransactionCardType)                   The list of different types of credit card.                                          
  Payment Instrument Types     Array of [Payment Instrument Type](#PaymentInstrumentType)               The list of payment methods used to process the transaction.                         
  Transactions Created Using   Array of [Transaction Created Using](#TransactionCreatedUsing)           The list of data used to create the transaction.                                     
  Customer Locations           Array of [Transaction Customer Location](#TransactionCustomerLocation)   The list of the customer location in the transaction.                                

### Transaction Type {#TransactionType}

  --------------------------------------------------------------------------------------------
  Field              Type                   Description             Default Value   Required
  ------------------ ---------------------- ----------------------- --------------- ----------
  Transaction Type   Enumeration, one of:   Types of transaction.                   
                                                                                    
                     -   SALE                                                       
                                                                                    
                     -   CREDIT                                                     
                                                                                    
                                                                                    
  --------------------------------------------------------------------------------------------

### Transaction Status {#TransactionStatus}

  ------------------------------------------------------------------------------------------------------
  Field    Type                             Description                       Default Value   Required
  -------- -------------------------------- --------------------------------- --------------- ----------
  Status   Enumeration, one of:             Specifies transaction’s status.                   
                                                                                              
           -   AUTHORIZING                                                                    
                                                                                              
           -   AUTHORIZED                                                                     
                                                                                              
           -   AUTHORIZATION\_EXPIRED                                                         
                                                                                              
           -   SUBMITTED\_FOR\_SETTLEMENT                                                     
                                                                                              
           -   SETTLING                                                                       
                                                                                              
           -   SETTLEMENT\_PENDING                                                            
                                                                                              
           -   SETTLEMENT\_DECLINED                                                           
                                                                                              
           -   SETTLED                                                                        
                                                                                              
           -   VOIDED                                                                         
                                                                                              
           -   PROCESSOR\_DECLINED                                                            
                                                                                              
           -   GATEWAY\_REJECTED                                                              
                                                                                              
           -   FAILED                                                                         
                                                                                              
                                                                                              
  ------------------------------------------------------------------------------------------------------

### Transaction Source {#TransactionSource}

  --------------------------------------------------------------------------------------------------------
  Field                Type                   Description                       Default Value   Required
  -------------------- ---------------------- --------------------------------- --------------- ----------
  Transaction Source   Enumeration, one of:   Specifies transaction’s source.                   
                                                                                                
                       -   API                                                                  
                                                                                                
                       -   CONTROL\_PANEL                                                       
                                                                                                
                       -   RECURRING                                                            
                                                                                                
                                                                                                
  --------------------------------------------------------------------------------------------------------

### Transaction Card Type {#TransactionCardType}

  ------------------------------------------------------------------------------------------------
  Field       Type                    Description                       Default Value   Required
  ----------- ----------------------- --------------------------------- --------------- ----------
  Card Type   Enumeration, one of:    Different types of credit card.                   
                                                                                        
              -   AMERICAN\_EXPRESS                                                     
                                                                                        
              -   DISCOVER                                                              
                                                                                        
              -   MAESTRO                                                               
                                                                                        
              -   JCB                                                                   
                                                                                        
              -   MASTER\_CARD                                                          
                                                                                        
              -   UNION\_PAY                                                            
                                                                                        
              -   VISA                                                                  
                                                                                        
                                                                                        
  ------------------------------------------------------------------------------------------------

### Payment Instrument Type {#PaymentInstrumentType}

  ----------------------------------------------------------------------------------------------------------------------------------
  Field                     Type                       Description                                        Default Value   Required
  ------------------------- -------------------------- -------------------------------------------------- --------------- ----------
  Payment Instrument Type   Enumeration, one of:       Payment methods used to process the transaction.                   
                                                                                                                          
                            -   ANDROID\_PAY\_CARD                                                                        
                                                                                                                          
                            -   APPLE\_PAY\_CARD                                                                          
                                                                                                                          
                            -   CREDIT\_CARD                                                                              
                                                                                                                          
                            -   MASTERPASS\_CARD                                                                          
                                                                                                                          
                            -   PAYPAL\_ACCOUNT                                                                           
                                                                                                                          
                            -   SAMSUNG\_PAY\_CARD                                                                        
                                                                                                                          
                            -   US\_BANK\_ACCOUNT                                                                         
                                                                                                                          
                            -   VENMO\_ACCOUNT                                                                            
                                                                                                                          
                            -   VISA\_CHECKOUT\_CARD                                                                      
                                                                                                                          
                                                                                                                          
  ----------------------------------------------------------------------------------------------------------------------------------

### Transaction Created Using {#TransactionCreatedUsing}

  ---------------------------------------------------------------------------------------------------------------------
  Field                       Type                    Description                            Default Value   Required
  --------------------------- ----------------------- -------------------------------------- --------------- ----------
  Transaction Created Using   Enumeration, one of:    Data used to create the transaction.                   
                                                                                                             
                              -   TOKEN                                                                      
                                                                                                             
                              -   FULL\_INFORMATION                                                          
                                                                                                             
                                                                                                             
  ---------------------------------------------------------------------------------------------------------------------

### Transaction Customer Location {#TransactionCustomerLocation}

  -----------------------------------------------------------------------------------------------------------------------
  Field               Type                   Description                                       Default Value   Required
  ------------------- ---------------------- ------------------------------------------------- --------------- ----------
  Customer Location   Enumeration, one of:   Specifies customer location in the transaction.                   
                                                                                                               
                      -   INTERNATIONAL                                                                        
                                                                                                               
                      -   US                                                                                   
                                                                                                               
                                                                                                               
  -----------------------------------------------------------------------------------------------------------------------

### Update Payment Method {#UpdatePaymentMethod}

  Field                  Type      Description                                                                                                                                                                                                                  Default Value   Required
  ---------------------- --------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Token                  String    The alphanumeric value that references a specific payment method stored in your Vault.                                                                                                                                                       x
  Update Existing        Boolean   Update the billing address associated with the payment method token specified. Other payment methods associated with the same billing address will have their addresses updated, as well.                                    false           
  Payment Method Nonce   String    One-time-use reference to new card details provided by your customer. Can only be used on payment method update if the payment method type is a card; other payment method types do not allow their details to be updated.                   
  New Token              String    If provided, updates the token for the payment method.                                                                                                                                                                                       

### Update Payment Method Options {#UpdatePaymentMethodOptions}

  Field                              Type      Description                                                                                                                                                                                                                 Default Value   Required
  ---------------------------------- --------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Make Default                       Boolean   This option makes the specified payment method the default for the customer.                                                                                                                                                false           
  Verification Amount                String    Specify a non-negative amount that you want to use to verify a card. If you do not pass this option, the gateway will automatically use a verification amount of \$0 or \$1, depending on the processor and/or card type.                   
  Verification Merchant Account Id   String    Specify the merchant account ID that you want to use to verify a card. Can’t be a Braintree Marketplace sub-merchant account.                                                                                                               
  Verify Card                        Boolean   If the payment method is a credit card, this option prompts the gateway to verify the card’s number and expiration date. It also verifies the AVS and CVV information if you’ve enabled AVS and CVV rules.                  false           

### Existing Customer {#ExistingCustomer}

  Field         Type     Description                                                                               Default Value   Required
  ------------- -------- ----------------------------------------------------------------------------------------- --------------- ----------
  Customer Id   String   A string value representing an existing customer in your Vault that you want to charge.                   

### New Customer {#NewCustomer}

  Field                 Type                                                                                                     Description                                                                                                                                                                                                                                                                                                                                                                                                                          Default Value   Required
  --------------------- -------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------- ----------
  Id                    String                                                                                                   A string value that will represent this specific customer in your Vault. 36 character maximum; must be unique within your Vault; valid characters are letters, numbers, -, and \_; the words "all" and "new" currently can’t be used. If not specified on creation, the gateway will generate an alphanumeric ID that can be accessed on the result. The generated IDs will never start with a leading 0 and are case insensitive.                   
  Customer First Name   String                                                                                                   The first name. The first name value must be less than or equal to 255 characters.                                                                                                                                                                                                                                                                                                                                                                   
  Customer Last Name    String                                                                                                   The last name. The last name value must be less than or equal to 255 characters.                                                                                                                                                                                                                                                                                                                                                                     
  Email                 String                                                                                                   Email address composed of ASCII characters.                                                                                                                                                                                                                                                                                                                                                                                                          
  Phone                 String                                                                                                   Phone number. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                
  Fax                   String                                                                                                   Fax number. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                  
  Company               String                                                                                                   Company name. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                
  Website               String                                                                                                   Website URL. Must be less than or equal to 255 characters. Website must be well-formed. The URL scheme is optional.                                                                                                                                                                                                                                                                                                                                  
  Token                 String                                                                                                   An alphanumeric value that references a specific payment method stored in your Vault. Must be less than or equal to 36 characters. If using a custom integration, you can specify what you want the token to be. If not specified, the gateway will generate one that can be accessed on the result.                                                                                                                                                 
  Nonce                 String                                                                                                   One-time-use reference to payment information provided by your customer, such as a credit card or PayPal account. When passed on customer create, it creates a payment method associated with the new customer.                                                                                                                                                                                                                                      
  Device Data           String                                                                                                   Customer device information. Pass this value only if you have Advanced Fraud Tools enabled and are adding credit card data to your Vault. Be sure to provide the full string received from the Braintree.                                                                                                                                                                                                                                            
  Custom Fields         Object                                                                                                   A collection of custom field/value pairs. Fields and values must be less than 255 characters. You must \<a href="https://articles.braintreepayments.com/control-panel/custom-fields?&\_ga=1.28588988.1497859415.1565702545\#creating-a-custom-field"\>set up each custom field in the Control Panel\</a\> prior to passing it with a request.                                                                                                        
  Risk Data             [Risk Data](https://developers.braintreepayments.com/reference/request/customer/create/java#risk_data)   Customer device information, which is sent directly to supported processors for fraud analysis. These fields are automatically populated if using \<a href="https://developers.braintreepayments.com/guides/advanced-fraud-tools/overview"\>Advanced Fraud Tools\</a\>. Currently only available when processing American Express via Amex Direct.                                                                                                   

### Existing Billing Address {#ExistingBillingAddress}

  Field                Type     Description                                                                                                                       Default Value   Required
  -------------------- -------- --------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Billing Address Id   String   The two-letter value for an address associated with a specific customer ID. The maximum number of addresses per customer is 50.                   

### New Billing Address {#NewBillingAddress}

  Field                                   Type      Description                                                                                                                                                                                                                                                                                    Default Value   Required
  --------------------------------------- --------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Add Billing Address To Payment Method   Boolean   The option that determines whether the billing address information provided in the request should be added to the payment method specified. This option works only for new payment methods.                                                                                                    false           
  First Name                              String    The first name. Maximum 255 characters.                                                                                                                                                                                                                                                                        
  Last Name                               String    The last name. Maximum 255 characters.                                                                                                                                                                                                                                                                         
  Company                                 String    Company name. Maximum 255 characters.                                                                                                                                                                                                                                                                          
  Country Code Alpha2                     String    The \<a href="http://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2"\>ISO 3166-1 alpha-2\</a\> country code specified in an address. The gateway only accepts \<a href="https://developers.braintreepayments.com/reference/general/countries\#list-of-countries"\>specific alpha-2 values\</a\>.                   
  Country Code Alpha3                     String    The \<a href="http://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-3"\>ISO 3166-1 alpha-3\</a\> country code specified in an address. The gateway only accepts \<a href="https://developers.braintreepayments.com/reference/general/countries\#list-of-countries"\>specific alpha-3 values\</a\>.                   
  Country Code Numeric                    String    The \<a href="http://en.wikipedia.org/wiki/ISO\_3166-1\_numeric"\>ISO 3166-1 numeric\</a\> country code specified in an address. The gateway only accepts \<a href="https://developers.braintreepayments.com/reference/general/countries\#list-of-countries"\>specific numeric values\</a\>.                   
  Country Name                            String    The country name specified in an address.                                                                                                                                                                                                                                                                      
  Street Address                          String    The street address. Maximum 255 characters.                                                                                                                                                                                                                                                                    
  Region                                  String    The state or province. Maximum 255 characters.                                                                                                                                                                                                                                                                 
  Extended Address                        String    The extended address information?such as apartment or suite number. 255 character maximum.                                                                                                                                                                                                                     
  Locality                                String    The locality/city. Maximum 255 characters.                                                                                                                                                                                                                                                                     
  Postal Code                             String    The postal code. Postal code must be a string of 4-9 alphanumeric characters, optionally separated by a dash or a space. Spaces and hyphens are ignored.                                                                                                                                                       

### Existing Shipping Address {#ExistingShippingAddress}

  Field                 Type     Description                                                                                                      Default Value   Required
  --------------------- -------- ---------------------------------------------------------------------------------------------------------------- --------------- ----------
  Shipping Address Id   String   A shipping address associated with a specific customer ID. The maximum number of addresses per customer is 50.                   

### New Shipping Address {#NewShippingAddress}

  Field                             Type      Description                                                                                                                                                                                                                                                                                                                                                                                                                                                               Default Value   Required
  --------------------------------- --------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Store Shipping Address In Vault   Boolean   The option that determines whether the shipping address information provided with the transaction should be associated with the customer ID specified. When passed, the payment method will always be stored in the Vault. If there is already a shipping address associated with the customer, this parameter will not replace the existing information; an additional address will be stored instead. You can associate up to 50 addresses with a single customer ID.   false           
  First Name                        String    The first name. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                   
  Last Name                         String    The last name. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                    
  Company                           String    Company name. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                     
  Country Code Alpha2               String    The \<a href="http://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2"\>ISO 3166-1 alpha-2\</a\> country code specified in an address. The gateway only accepts \<a href="https://developers.braintreepayments.com/reference/general/countries\#list-of-countries"\>specific alpha-2 values\</a\>.                                                                                                                                                                                              
  Country Code Alpha3               String    The \<a href="http://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-3"\>ISO 3166-1 alpha-3\</a\> country code specified in an address. The gateway only accepts \<a href="https://developers.braintreepayments.com/reference/general/countries\#list-of-countries"\>specific alpha-3 values\</a\>.                                                                                                                                                                                              
  Country Code Numeric              String    The \<a href="http://en.wikipedia.org/wiki/ISO\_3166-1\_numeric"\>ISO 3166-1 numeric\</a\> country code specified in an address. The gateway only accepts \<a href="https://developers.braintreepayments.com/reference/general/countries\#list-of-countries"\>specific numeric values\</a\>.                                                                                                                                                                                              
  Country Name                      String    The country name specified in an address.                                                                                                                                                                                                                                                                                                                                                                                                                                                 
  Street Address                    String    The street address. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                               
  Region                            String    The state or province. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                            
  Extended Address                  String    The extended address information?such as apartment or suite number. 255 character maximum.                                                                                                                                                                                                                                                                                                                                                                                                
  Locality                          String    The locality/city. Maximum 255 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                
  Postal Code                       String    The postal code. Postal code must be a string of 4-9 alphanumeric characters, optionally separated by a dash or a space. Spaces and hyphens are ignored.                                                                                                                                                                                                                                                                                                                                  

### Payment Method Token {#PaymentMethodToken}

  Field                       Type     Description                                                                                                                                                                                                                                                                                                                                                                                                   Default Value   Required
  --------------------------- -------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Sale Payment Method Token   String   An alphanumeric value that references a specific payment method stored in your Vault. Must be less than or equal to 36 characters. If using a custom integration, you can specify what you want the token to be. If not specified, the gateway will generate one that can be accessed on the result. If using our Drop-in UI with a customer ID to vault payment methods, you can’t specify your own token.                   x

### Card Details {#CardDetails}

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Field                       Type      Description                                                                                                                                                                                                                                                                                                                                                                                               Default Value   Required
  --------------------------- --------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------- ----------
  Sale Payment Method Nonce   String    One-time-use reference to payment information provided by your customer, such as a credit card or PayPal account. Can be passed instead of a paymentMethodToken parameter.                                                                                                                                                                                                                                                

  Three D Secure Required     Boolean   Options for 3D Secure verification. Can only be used when the payment method nonce parameter is present.                                                                                                                                                                                                                                                                                                  true            
                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
                                        Specify whether to require 3D Secure verification to succeed before creating a transaction. Defaults to true for all transactions sent through 3D Secure verification unless you explicitly pass false. For more information, see 3D Secure advanced server-side options.                                                                                                                                                 

  Payment Method Token        String    An alphanumeric value that references a specific payment method stored in your Vault. Must be less than or equal to 36 characters. If using a custom integration, you can specify what you want the token to be. If not specified, the gateway will generate one that can be accessed on the result.                                                                                                                      

  Cardholder Name             String    The name associated with the credit card. Must be less than or equal to 175 characters.                                                                                                                                                                                                                                                                                                                                   

  Number                      String    Typically requires The \<a href= "https://www.pcisecuritystandards.org/pci\_security/completing\_self\_assessment"\>PCI SAQ D compliance\</a\> Braintree recommend using paymentMethodNonce to avoid any PCI concerns with raw credit card data being present on your server. The 12-19 digit value on a credit card consisting of a bank identification number (BIN) and primary account number (PAN).                   

  Cvv                         String    A 3 or 4 digit card verification value assigned to a credit card. The CVV will never be stored in the gateway, but it can be provided with one-time requests to verify the card.                                                                                                                                                                                                                                          

  Expiration Month            String    The expiration month of a credit card, formatted MM. May be used with expirationYear, and instead of expirationDate.                                                                                                                                                                                                                                                                                                      

  Expiration Year             String    The two or four digit year associated with a credit card, formatted YYYY or YY. May be used with expirationMonth, and instead of expirationDate.                                                                                                                                                                                                                                                                          
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


