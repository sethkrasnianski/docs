# Concepts

- [REST](#rest)
- [OAuth](#oauth)
- [Authorisation](#auth)
- [Credentials](#credentials)
- [Flows](#flows)
- [Headers](#headers)

<a name="rest"></a>
## REST

REST stands for Representational State Transfer. It relies on a stateless, client-server, cacheable communications protocol built using the HTTP protocol.

RESTful applications use HTTP requests to post data (create and/or update), read data (e.g., make queries), and delete data. Thus, REST uses HTTP for all four CRUD (Create/Read/Update/Delete) operations.

<a name="oauth"></a>
## OAuth

OAuth is an open standard for authorization. OAuth provides client applications a 'secure delegated access' to server resources on behalf of a resource owner. It specifies a process for resource owners to authorize third-party access to their server resources without sharing their credentials.

<a name="auth"></a>
## Authorisation

Before making any requests to the API you must obtain an access_token. The access token lets us know you are and you are allowd to request a resource. To recieve an access token you utilise one of the available grant types. A grant type is a method of authentication intended for different purposes, which are as follows:

- Authorization Code for apps running on a web server
- Implicit for browser-based or mobile apps
- Password for logging in with a username and password
- Client credentials for application access

<a name="credentials"></a>
## Credentials

You will receive a client ID and a client secret. The client ID is considered public information, and is used to build login URLs, or included in Javascript source code on a page. The client secret must be kept confidential. If a deployed app cannot keep the secret confidential, such as Javascript or native apps, then the secret is not used.

<a name="flows"></a>
## Flows

When we started planning Moltin we recognised one drawback of many APIs was that only key value pairs were supported. This wouldn't really cut it when we needed to store complex eCommerce data and we wanted flexibility to be at the heart of our solution. We also wanted a system that provided validation for different types of data, such as emails, money and integers.


We wanted individual stores on our platform to extend any data set 



<a name="headers"></a>
## Headers

TODO
