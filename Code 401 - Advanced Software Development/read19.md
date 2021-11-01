# Spring and Sockets
> Using WebSocket to build an interactive web application
what is a web socket?

> WebSocket is a thin, lightweight layer above TCP. This makes it suitable for using “subprotocols” to embed messages.
STOMP is a subprotocol operating on top of the lower-level WebSocket.
steps:
* Spring Initializr
* Adding Dependencies
* Create a Resource Representation Class
* Create a Message-handling Controller
* Configure Spring for STOMP messaging
* Create a Browser Client
* Make the Application Executable
> Create a Resource Representation Class: The service will accept messages that contain a name in a STOMP message whose body is a JSON object.

Create a Message-handling Controller create a controller to receive and send the messages. STOMP messages can be routed to @Controller classes like the following:

`package com.example.messagingstompwebsocket;
import org.springframework.messaging.handler.annotation.MessageMapping; import org.springframework.messaging.handler.annotation.SendTo; import org.springframework.stereotype.Controller; import org.springframework.web.util.HtmlUtils;
@Controller public class GreetingController {
@MessageMapping("/hello") @SendTo("/topic/greetings") public Greeting greeting(HelloMessage message) throws Exception { Thread.sleep(1000); // simulated delay return new Greeting("Hello, " + HtmlUtils.htmlEscape(message.getName()) + "!"); }

}`

> Why you should use WebSockets:

> WebSockets are designed to supersede the existing bidirectional communication technologies. The existing methods described above are neither reliable nor efficient when it comes to full-duplex real-time communications.

> WebSockets are similar to SSE but also triumph in taking messages back from the client to the server. Connection restrictions are no longer an issue since data is served over a single TCP socket connection.

> How to use WebSockets As mentioned in the introduction, the WebSocket protocol has only two agendas. Let’s see how WebSockets fulfills those agendas. To do that, I’m going to spin off a Node.js server and connect it to a client built with React.js.