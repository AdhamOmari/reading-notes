# What is a status code 202?
> The 202 response is intentionally non-committal. Its purpose is to allow a server to accept a request for some other process (perhaps a batch-oriented process that is only run once per day) without requiring that the user agent’s connection to the server persist until the process is completed.


> Status Codes
Status codes between 100 and 600 are part of HTTP responses.
100’s = Informational status codes. Header part of request has been recieved, and server will try to comply with response. 200’s = Success codes :) Saying that a request was accepted. For an asyn processing of request, 202, it met valid requirements. 300’s = Redirection codes. The code one is trying to access is not available at the current time of the error. 400’s = Client error codes. Timeouts, wrong URI, missing auth… A client is doing something wrong- sending the wrong info. 500’s = Server error codes. Server may be overwhelmed, or code may not be written/connected properly.
202 = An async request met the valudation requirements, but it wasn’t necessarily fully processed. 208 = There is an error with the accessing the Microsoft SQL Server.

> Build a REST API Link
Why do we need to pull our MongoDB database string out of our server and put it into our .env?
This is because when working on the code locally, you want to store the database as a local environment variable. This adds security and flexibility.


> 3. What is a status code 308?
308 Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore.

4. What code would you use if an update didn’t return data to a client?
204 No Content - A proper code for updates that don’t return data to the client, for example when just saving a currently edited document.

5. What code would you use if a resource used to exist but no longer does?
410 Gone - This is like 404 but we know that the resource existed in the past, but it got deleted or somehow moved, and we don’t know where.

6. What is the ‘Forbidden’ status code?
403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

7. What is the difference between PUT and PATCH?
PUT will update the whole document but PATCH will update that specific document detail.



> 3. What is a status code 308?
308 Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore.

4. What code would you use if an update didn’t return data to a client?
204 No Content - A proper code for updates that don’t return data to the client, for example when just saving a currently edited document.

5. What code would you use if a resource used to exist but no longer does?
410 Gone - This is like 404 but we know that the resource existed in the past, but it got deleted or somehow moved, and we don’t know where.

6. What is the ‘Forbidden’ status code?
403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

7. What is the difference between PUT and PATCH?
PUT will update the whole document but PATCH will update that specific document detail.



> 200 - 299Permalink
These are the success codes. They tell the client that its request was accepted. In case of asynchronous processing of a request (202), this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.

300 - 399Permalink
These are redirection codes. They tell the client that the resource they are requesting isn’t available at the expected location anymore. This can have multiple reasons, be temporary or permanent, but the client has to issue a request to the new location.

400 - 499Permalink
These are the client error codes. They are all about invalid requests a client sent to a server. There are several causes to this, timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request.

500 - 599Permalink
These are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. These errors can be temporary or permanent. Usually it’s best for the client to retry the same request.