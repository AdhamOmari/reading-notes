> Spring and Sockets
How to complete this guide?

create a repo, after that clone int in your machine.
Create a Web Controller.
Manual Initialization
1- Navigate to https://start.spring.io. This service pulls in all the dependencies you need for an application and does most of the setup for you.

2- Choose either Gradle or Maven and the language you want to use. This guide assumes that you chose Java.

3- Click Dependencies and select Spring Web, Thymeleaf, and Spring Boot DevTools.

4- Click Generate.

5- Download the resulting ZIP file, which is an archive of a web application that is configured with your choices.


> To create a “Hello, world” application that sends messages back and forth between a browser and a server:
Spring Initializr
1- Navigate to https://start.spring.io. This service pulls in all the dependencies you need for an application and does most of the setup for you.

2- Choose either Gradle or Maven and the language you want to use.

3- Click Dependencies and select Spring Web, Thymeleaf, and Spring Boot DevTools.

4- Click Generate.

5- Download the resulting ZIP file

Adding Dependencies:
dependencies {
`implementation 'org.webjars:webjars-locator-core'
implementation 'org.webjars:sockjs-client:1.0.2'
implementation 'org.webjars:stomp-websocket:2.3.3'
implementation 'org.webjars:bootstrap:3.3.7'
implementation 'org.webjars:jquery:3.1.1-1'
}`
Create a Resource Representation Class
The service will accept messages that contain a name in a STOMP message whose body is a JSON object.

Upon receiving the message and extracting the name, the service will process it by creating a greeting and publishing that greeting on a separate queue to which the client is subscribed. The greeting will also be a JSON object.

To model the message that carries the name, you can create a plain old Java object with a name property and a corresponding getName() method.

> how we can build a server?
> visit the Spring Initializr (Links to an external site.) to generate a new project with the required dependency (Websocket).
add websocket dependencies .
Create a Resource Representation Class
create your STOMP message service
The service will accept messages that contain a name in a STOMP message whose body is a JSON object.
To model the message you can create a plain old Java object with a name property and a corresponding getName() method.
the service will process it by creating a greeting and publishing that greeting on a separate queue to which the client is subscribed.
The greeting will also be a JSON object
Spring will use the Jackson JSON library to automatically marshal instances of type Greeting into JSON.
Create a Message-handling Controller
STOMP messages can be routed to @Controller classes.
The @MessageMapping annotation ensures that, if a message is sent to the /hello destination, the greeting() method is called.
The payload of the message is bound to a HelloMessage object which is passed into greeting().
the implementation of the method simulates a processing delay by causing the thread to sleep for one second.
after the client sends a message, the server can take as long as it needs to asynchronously process the message.
The client can continue with whatever work it needs to do without waiting for the response.
After the one-second delay, the greeting() method creates a Greeting object and returns it.
The return value is broadcast to all subscribers of /topic/greetings, as specified in the @SendTo annotation.
Configure Spring for STOMP messaging
configure Spring to enable WebSocket and STOMP messaging.
Create a Java class named WebSocketConfig
WebSocketConfig is annotated with @Configuration to indicate that it is a Spring configuration class.
It is also annotated with @EnableWebSocketMessageBroker. As its name suggests, @EnableWebSocketMessageBroker enables WebSocket message handling, backed by a message broker.
Create a Browser Client
you can turn your attention to the JavaScript client that will send messages to and receive messages from the server side.
The connect() function uses SockJS and stomp.js to open a connection
he sendName() function retrieves the name entered by the user and uses the STOMP client to send
Make the Application Executable
Spring Boot creates an application class for you
You can use it to run this application.