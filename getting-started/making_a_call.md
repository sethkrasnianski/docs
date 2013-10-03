<!--
@title Making a Call
@author Moltin Ltd
@description A helping hand to get started making API calls
@family Getting Started
-->
Once you have your [Access Token](/getting-started/authentication) you can then start to make calls to the API. Throughout our documentation you will see different URLs (or End-Points) that when called in different ways will return information and in some cases perform a specific action.


#### HTTP Methods
We've tried to make the API as simple as possible and utilise HTTP methods to keep the range of end-points/URLs to a minumum. We've also made sure that a single call enough to perform an action, rather than requiring multiple calls to create a form that can be used to update a product for example. The methods you'll see throughout are our API are:

* *GET* - The most common method, used to retrieve data
* *POST* - Used to create or insert objects
* *PUT* - Used to update objects
* *DELETE* - Used to delete or remove objects

These methods (when not using GET) will be set in the header of your request, this is done like so:

	-X PUT


#### Making a Request
There are numerous ways to make requests to the API, throughout this guide we'll focus on CURL as it is one of the most comonly used libraries available. If you are happier using something else to perform these actions that is not a problem and the API will work with any library capable of setting headers and making regular HTTP calls.

Along with every request you make your access token recieved from [Authentication](/getting-started/authentication) will be required as a header, and will be set as a header like so:

	"Authorization: Bearer NUB6998XaPHuga7UwEn3spE8axebREswUT4EH3fR"


##### Basic GET Request

	curl -H "Authorization: Bearer NUB6998XaPHuga7UwEn3spE8axebREswUT4EH3fR" {{ url }}product/1


##### Basic POST Request

	curl -X POST -H "Authorization: Bearer NUB6998XaPHuga7UwEn3spE8axebREswUT4EH3fR" {{ url }}product


##### Basic PUT Request

	curl -X PUT -H "Authorization: Bearer NUB6998XaPHuga7UwEn3spE8axebREswUT4EH3fR" {{ url }}product/1
