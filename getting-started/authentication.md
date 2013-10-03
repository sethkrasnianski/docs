<!--
@title Authentication
@author Moltin Ltd
@description Before you start making calls you need to Authenticate
@family Getting Started
-->
Before using the API you must first authenticate with it, this will allow it to retrieve the correct data for your account as well as keep your data safe and secure. For anyone already familiar with OAuth from other places this should be a very easy process, for those not so you'll find all the help you need below.

#### OAuth
OAuth is an open standard for authorization. OAuth provides a method for clients to access server resources on behalf of a resource owner (such as a different client or an end-user). It also provides a process for end-users to authorize third-party access to their server resources without sharing their credentials (typically, a username and password pair), using user-agent redirections.

#### Grant Types
With OAuth there are a number of different authentication methods (or grant types) available that require different types of credentials and are designed for different purposes. Some require your ID and Secret, others require more public versions of these keys, with access to different resources being allowed or disallowed based on requested access.

The different methods that are available are as follows:

* *Client Credentials* - The easiest method available, designed for backend systems where your credentials are kept secret and does not require you sharing them with others.
* *Authorization Code* - Designed for third parties, this will be familiar to most people that have ever logged in with Facebook or Twitter to a website. It allows third-parties access to certain parts of your data that you allow.

#### Authorising with Client Credentials
