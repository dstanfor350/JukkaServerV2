            JukkaServerV2 Solution and Project

The JukkaServerV2 solution is the first attempt at a http listener.
The Machine to Cloud classes have been move to a Class Library JukkaServerLib so they can be unit tested.

The NUnit unit test framework has been added to this version of the project.  
The Login class has been modified to have an additional contructor allowing custom
Login manager to be passes in.  For testing a 'Fake' login manager is used.
For non-test a real login manager would be used.
Otherwise, the solution is the same as the JukkaServer project.

There currently is only 2 unit test. One for Login pass and one for Login fail.
The Test class JukkaServerTestClass.cs uses dependency injection via a constructor.

Article I used to get started with httplistener
https://stackoverflow.com/questions/7004616/how-to-use-httplistener-to-receive-http-post-which-contain-xml

.NET: Create a basic HttpListener web service
http://www.gabescode.com/dotnet/2018/11/01/basic-HttpListener-web-service.html

Usage:
!! IMPORTANT !!
Visual Studio must be "Run as Administrator".  If run from the command line,
the command line window must "Run as Administrator".

The project is intended to be an attempt to simulate the Jukka Machine to Cloud APIs by
creating class models and methods of the Machine to Cloud APIs.

The JukkaServer project acts as a http listener and processes http request.
It listens on http://localhost:4333 for http request.
The port can be changed in the JukkaServer program.cs prefix variable located in 
the RunServer method.

Postman is used as the client.  
Postman can be downloaded from https://www.postman.com/downloads/

Postman URLs:
The Postman URLs "Jukka Machone.postman_collection.json" can be found in the Solution's 
folder ""Solution Items." This collection can be imported into Postman by using
the "File" -> "Import" menu item.

These http request are described in the Jukka Machine to Cloud API document.
Each should return a response as described in the Response Example for each API.

Login:
    http://localhost:4333/prod/api/account/login
    No actual authentication validation is actually performed.
    The payload is provided in the Postman request.
    A response body is returned as the API describes.
    The HTTP Response Code should be 200 : Success.

Order Status:
    http://localhost:4333/api/order/status
    The payload is provided in the Postman request.
    The response body is N/A
    The HTTP Response Code should be 200 : Success.

Order Item Status:
    http://localhost:4333/api/orderitem/status
    The payload is provided in the Postman request.
    The response body is N/A
    The HTTP Response Code should be 200 : Success.

Payment:
    http://localhost:4333/api/payment
    The payload is provided in the Postman request.
    The response body is N/A
    The HTTP Response Code should be 200 : Success.

Machine Status:
    http://localhost:4333/api/machine/status
    The payload is provided in the Postman request.
    The response body is N/A
    The HTTP Response Code should be 200 : Success

The Postman LoginOAuth and JukkaServerLoginOAuth are NOT supported in this version 
of the JukkaServer solution.

