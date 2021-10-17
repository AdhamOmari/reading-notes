> Spring Boot and OAuth2

* simple: a very basic static app with just a home page and unconditional login via Spring Boot’s OAuth 2.0 configuration properties (if you visit the home page, you will be automatically redirected to GitHub).

* click: adds an explicit link that the user has to click to login.

* logout: adds a logout link as well for authenticated users.

*two-providers: adds a second login provider so the user can choose on the home page which one to use.

* custom-error: adds an error message for unauthenticated users, and a custom authentication based on GitHub’s API.

> Each app can be imported into an IDE. You can run the main method in SocialApplication to start an app. They all come up with a home page on `http://localhost:8080` (and all require that you have at least a GitHub and Google account if you want to log in and see the content).


> You can also run all the apps on the command line using mvn spring-boot:run or by building the jar file and running it with mvn package and java -jar target/*.jar (per the Spring Boot docs and other available documentation). There is no need to install Maven if you use the wrapper at the top level, e.g.

`$ cd simple
$ ../mvnw package
$ java -jar target/*.jar`

> 
> Add a Home Page
`<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <title>Demo</title>
    <meta name="description" content=""/>
    <meta name="viewport" content="width=device-width"/>
    <base href="/"/>
    <link rel="stylesheet" type="text/css" href="/webjars/bootstrap/css/bootstrap.min.css"/>
    <script type="text/javascript" src="/webjars/jquery/jquery.min.js"></script>
    <script type="text/javascript" src="/webjars/bootstrap/js/bootstrap.min.js"></script>
</head>
<body>
	<h1>Demo</h1>
	<div class="container"></div>
</body>
</html>`