# Logic, service layer, dependency injection

----

## Where are we at?

* We want to build URL shorter service (class 1)
* We know how to build simple Spring Boot application (class 2)
* We know about dependency injection and have a service ready which returns shortened urls 
----

## Agenda for today
* We will learn about API Design
* We will learn about REST, HTTP/Status
* We will learn about Swagger

----

## Core functionality

* As a link creator I would like to create a short link for my long URL
* As a link user I would like to be redirected to the original URL by following a short link

Read more about [user stories](https://en.wikipedia.org/wiki/User_story).

----

##API

Application programming interface

https://developer.hootsuite.com/docs/owly-api-reference

## HTTP Response codes
* Status Code 200 – This is the standard “OK” status code for a successful HTTP request. The response that is returned is dependent on the request. For example, for a GET request, the response will be included in the message body. For a PUT/POST request, the response will include the resource that contains the result of the action.
* Status Code 201 – This is the status code that confirms that the request was successful and, as a result, a new resource was created. Typically, this is the status code that is sent after a POST/PUT request.
* Status Code 204 – This status code confirms that the server has fulfilled the request but does not need to return information. Examples of this status code include delete requests or if a request was sent via a form and the response should not cause the form to be refreshed or for a new page to load.
* Status Code 304 – The is status code used for browser caching. If the response has not been modified, the client/user can continue to use the same response/cached version. For example, a browser can request if a resource has been modified since a specific time. If it hasn’t, the status code 304 is sent. If it has been modified, a status code 200 is sent, along with the resource.
* Status Code 400 – The server cannot understand and process a request due to a client error. Missing data, domain validation, and invalid formatting are some examples that cause the status code 400 to be sent.
* Status Code 401 – This status code request occurs when authentication is required but has failed or not been provided.
* Status Code 403 – Very similar to status code 401, a status code 403 happens when a valid request was sent, but the server refuses to accept it. This happens if a client/user requires the necessary permission or they may need an account to access the resource. Unlike a status code 401, authentication will not apply here.
* Status Code 404 – The most common status code the average user will see. A status code 404 occurs when the request is valid, but the resource cannot be found on the server. Even though these are grouped in the Client Errors “bucket,” they are often due to improper URL redirection.
* Status Code 409 – A status code 409 is sent when a request conflicts with the current state of the resource. This is usually an issue with simultaneous updates, or versions, that conflict with one another.
* Status Code 410 – Resource requested is no longer available and will not be available again. Learn about network error 410.
* Status Code 500 – Another one of the more commonly seen status codes by users, the 500 series codes are similar to the 400 series codes in that they are true error codes. The status code 500 happens when the server cannot fulfill a request due to an unexpected issue. Web developers typically have to comb through the server logs to determine where the exact issue is coming from.


##REST

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation), HTML, XLT, Python, PHP, or plain text. JSON is the most generally popular file format to use because, despite its name, it’s language-agnostic, as well as readable by both humans and machines.



In order for an API to be considered RESTful, it has to conform to these criteria:

* A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
* Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
* Cacheable data that streamlines client-server interactions.
  * A uniform interface between components so that information is transferred in a standard form. This requires that:
  * resources requested are identifiable and separate from the representations sent to the client.  
  * resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.  
  * self-descriptive messages returned to the client have enough information to describe how the client should process it.   
  * hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
* A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.

Though the REST API has these criteria to conform to, it is still considered easier to use than a prescribed protocol like SOAP (Simple Object Access Protocol), which has specific requirements like XML messaging, and built-in security and transaction compliance that make it slower and heavier.


## Type of HTTP requests:
* GET – obtain resource from the server
* POST – create a new resource on the server
* PUT – update resource on the server
* DELETE – delete resource from the server

----

### Swagger

Simplify API development for users, teams, and enterprises with the Swagger open source and professional toolset. Find out how Swagger can help you design and document your APIs at scale.

```
		<dependency>
			<groupId>org.springdoc</groupId>
			<artifactId>springdoc-openapi-ui</artifactId>
			<version>1.6.6</version>
		</dependency>
```

## Home assignment
* Integrate code with swagger