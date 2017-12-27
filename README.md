# RESTJava
rest web services with java

goodread:
https://www.journaldev.com/9170/restful-web-services-tutorial-java
https://www.tutorialspoint.com/restful/restful_resources.htm

practise programs on :https://www.tutorialspoint.com/restful/restful_methods.htm

Restful Web Services is a stateless client-server architecture where web services are resources and can be identified by their URIs.

---what is a resource---
REST architecture treats every content as a resource. These resources can be Text Files, Html Pages, Images, Videos or Dynamic Business Data. REST Server simply provides access to resources and REST client accesses and modifies the resources.
A resource in REST is a similar Object in Object Oriented Programming or is like an Entity in a Database. Once a resource is identified then its representation is to be decided using a standard format so that the server can send the resource in the above said format and client can understand the same format.


---Annnotations---
Some of the important JAX-RS annotations are:

@Path: used to specify the relative path of class and methods. We can get the URI of a webservice by scanning the Path annotation value.
@GET, @PUT, @POST, @DELETE and @HEAD: used to specify the HTTP request type for a method.
@Produces, @Consumes: used to specify the request and response types.
@PathParam: used to bind the method parameter to path value by parsing it.

--URI--
A URI is of following format −

<protocol>://<service-name>/<ResourceType>/<ResourceID>

---HTTP---
An HTTP Request has five major parts −

Verb − Indicates the HTTP methods such as GET, POST, DELETE, PUT, etc.

URI − Uniform Resource Identifier (URI) to identify the resource on the server.

HTTP Version − Indicates the HTTP version. For example, HTTP v1.1.

Request Header − Contains metadata for the HTTP Request message as key-value pairs. For example, client (or browser) type, format supported by the client, format of the message body, cache settings, etc.

Request Body − Message content or Resource representation.

An HTTP Response has four major parts −

Status/Response Code − Indicates the Server status for the requested resource. For example, 404 means resource not found and 200 means response is ok.

HTTP Version − Indicates the HTTP version. For example HTTP v1.1.

Response Header − Contains metadata for the HTTP Response message as keyvalue pairs. For example, content length, content type, response date, server type, etc.

Response Body − Response message content or Resource representation.

----
SOAP vs rest:
SOAP is a protocol whereas REST is an architectural style.
SOAP server and client applications are tightly coupled and bind with the WSDL contract whereas there is no contract in REST web services and client.
REST web services request and response types can be XML, JSON, text etc. whereas SOAP works with XML only.
JAX-RS is the Java API for REST web services whereas JAX-WS is the Java API for SOAP web services.

---
Implementation and JARS:-

Jersey: Jersey is the reference implementation provided by Sun. For using Jersey as our JAX-RS implementation, all we need to configure its servlet in web.xml and add required dependencies. Note that JAX-RS API is part of JDK not Jersey, so we have to add its dependency jars in our application.
RESTEasy: RESTEasy is the JBoss project that provides JAX-RS implementation.


---stateless---

As per the REST architecture, a RESTful Web Service should not keep a client state on the server. This restriction is called Statelessness. It is the responsibility of the client to pass its context to the server and then the server can store this context to process the client's further request. For example, session maintained by server is identified by session identifier passed by the client.

RESTful Web Services should adhere to this restriction. We have seen this in the RESTful Web Services - Methods chapter, that the web service methods are not storing any information from the client they are invoked from.

---
Advantages of Statelessness
  Web services can treat each method request independently.
  Web services need not maintain the client's previous interactions. It simplifies the application design.
  As HTTP is itself a statelessness protocol, RESTful Web Services work seamlessly with the HTTP protocols.

Disadvantages of Statelessness
  Web services need to get extra information in each request and then interpret to get the client's state in case the client interactions are to be taken care of.
  
  
  ---caching---
  Caching refers to storing the server response in the client itself, so that a client need not make a server request for the same resource again and again. A server response should have information about how caching is to be done, so that a client caches the response for a time-period or never caches the server response.
  
  ---security---
1.Validation − Validate all inputs on the server. Protect your server against SQL or NoSQL injection attacks.
2.Session Based Authentication − Use session based authentication to authenticate a user whenever a request is made to a Web Service method.
3.No Sensitive Data in the URL − Never use username, password or session token in a URL, these values should be passed to Web Service via the POST method.
4.Restriction on Method Execution − Allow restricted use of methods like GET, POST and DELETE methods. The GET method should not be able to delete data.
5.Validate Malformed XML/JSON − Check for well-formed input passed to a web service method.
Throw generic Error Messages − A web service method should use HTTP error messages like 403 to show access forbidden, etc.


--Annotations---
in use since JAVA 5. JAX_RS implementation
1.@Path

Relative path of the resource class/method.

2

@GET

HTTP Get request, used to fetch resource.

3

@PUT

HTTP PUT request, used to create resource.

4

@POST

HTTP POST request, used to create/update resource.

5

@DELETE

HTTP DELETE request, used to delete resource.

6

@HEAD

HTTP HEAD request, used to get status of method availability.

7

@Produces

States the HTTP Response generated by web service. For example, APPLICATION/XML, TEXT/HTML, APPLICATION/JSON etc.

8

@Consumes

States the HTTP Request type. For example, application/x-www-formurlencoded to accept form data in HTTP body during POST request.

9

@PathParam

Binds the parameter passed to the method to a value in path.

10

@QueryParam

Binds the parameter passed to method to a query parameter in the path.

11

@MatrixParam

Binds the parameter passed to the method to a HTTP matrix parameter in path.

12

@HeaderParam

Binds the parameter passed to the method to a HTTP header.

13

@CookieParam

Binds the parameter passed to the method to a Cookie.

14

@FormParam

Binds the parameter passed to the method to a form value.

15

@DefaultValue

Assigns a default value to a parameter passed to the method.

16

@Context

Context of the resource. For example, HTTPRequest as a context.
