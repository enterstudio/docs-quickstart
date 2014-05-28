.. _authenticate:

Authentication
--------------
To use this service, you must authenticate yourself as a subscriber to the service.
Authenticate by presenting valid Rackspace customer credentials in a ''POST'' to a Rackspace authentication endpoint. 

After you authenticate, you'll have two things:
* a token, proving that your identity has been authenticated
* a service catalog, listing the API endpoints available to you
To begin interacting with a service, send your token to that service's API endpoint.

You can read more about authentication, including how to obtain your API key credential, 
in the Quickstart information for the Rackspace Cloud Identity service 
at http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/QuickStart-000.html.
