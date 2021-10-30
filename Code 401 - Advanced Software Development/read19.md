Real time messaging with websockets
The WebSocket protocol is one of the ways to make The application handle real-time messages.

The WebSocket protocol allows you to implement bidirectional communication between applications. It is important to know that HTTP is used only for the initial handshake. After it happens, the HTTP connection is upgraded to a newly opened TCP/IP connection that is used by a WebSocket.

The WebSocket specification allows using of sub-protocols that operate on a higher, application level. One of them, supported by the Spring Framework, is STOMP.

To build the WebSocket server-side, we will utilize the Spring Boot framework which significantly speeds up the development of standalone and web applications in Java. Spring Boot includes the spring-WebSocket module

Implementing the WebSocket server-side with Spring Boot:
First, we should add these Dependencies:
implementation 'org.webjars:webjars-locator-core'
implementation 'org.webjars:sockjs-client:1.0.2'
implementation 'org.webjars:stomp-websocket:2.3.3'
implementation 'org.webjars:bootstrap:3.3.7'
implementation 'org.webjars:jquery:3.1.1-1'

Why you should use WebSockets
WebSockets are designed to supersede the existing bidirectional communication technologies. The existing methods described above are neither reliable nor efficient when it comes to full-duplex real-time communications.

WebSockets are similar to SSE but also triumph in taking messages back from the client to the server. Connection restrictions are no longer an issue since data is served over a single TCP socket connection.

How to use WebSockets As mentioned in the introduction, the WebSocket protocol has only two agendas. Let’s see how WebSockets fulfills those agendas. To do that, I’m going to spin off a Node.js server and connect it to a client built with React.js.


STOMP protocol
STOMP (simple text orientated messaging protocol) is a sub-protocol much like HTTP. Each time either party sends data, they must send it in the form of a frame. A frame takes a structure like an HTTP request.

It has a verb associated with the intention of the frame (ex. CONNECT, DISCONNECT) like the HTTP methods. It also contains a header to give extra information to the other party and a body to give the main content. As you can see, the design of STOMP is almost identical to the way we send HTTP requests and will be intuitive to use.

Implementing WebSockets in Spring
Now that you have a good understanding of WebSockets, let’s implement them in Spring. What we are going to build is a simple application that takes messages from users and sends them back to everyone. Each user is going to send messages to an endpoint /app/chat and subscribe to receive messages from /topic/messages.

Every time a user sends a message to /app/chat our server will send the message back to /topic/messages. For simplicity, I will be making a simplistic client using plain HTML and JavaScript. It will be running on its own server separate from our Spring Boot application.

First, we need to create a new Spring Boot project from the Spring initializer (Links to an external site.). The only dependency we will need for now is the spring-boot-starter-websocket dependency. Next, you need to create a configuration class to register our STOMP endpoints and to allow us to use an extra tool called sockjs.

What sockjs does is it allows for backup plans in case the client cannot connect via WebSocket. If this happens it will try to connect using another protocol to try to mimic a WebSocket connection. This is particularly useful if we want to allow the use of older browsers that do not support WebSockets.