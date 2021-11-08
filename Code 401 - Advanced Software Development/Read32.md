# Serverless and Amplify

> Serverless is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers.

[Pricing]

> One of the major advantages of using Serverless is reduced cost. The cost model of Serverless is execution-based: you’re charged for the number of executions.

[Networking]

> The downside is that Serverless functions are accessed only as private APIs. To access these you must set up an API Gateway.

3rd Party Dependencies > Most, if not all of your projects have external dependencies, they rely on libraries that are not built into the language or framework you use.

> Environments

 Given that it’s pay per execution, this is a large improvement over traditional servers, you no longer need to set up dev, staging, and production machines.

 Timeout

 With Serverless computing, there’s a hard 300-second timeout limit. Too complex or long-running functions aren’t good for Serverless, but having a hard timeout makes it impossible to perform certain tasks.

 Scale

 Scaling process for Serverless is automatic and seamless, but there is a lack of control or entire absence of control.


 > FaaS is an implementation of Serverless architectures where engineers can deploy an individual function or a piece of business logic.

> Principles of FaaS:

* Stateless.
* Ephemeral.
* Event-triggered.
* Scalable by default.
* Fully managed by a Cloud vendor.
* The Serverless App.



> AWS Amplify is a set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, powered by AWS. With Amplify, you can configure app backends and connect your app in minutes, deploy static web apps in a few clicks, and easily manage app content outside the AWS console.

Benefits

> Configure backends fast.
> Seamlessly connect frontends.
Deploy in a few clicks.
Easily manage content.

> Amplify
> The GraphQL Transform provides a simple to use abstraction that helps you quickly create backends for your web and mobile applications on AWS.

> The GraphQL Transform simplifies the process of developing, deploying, and maintaining GraphQL APIs. With it, you define your API using the GraphQL Schema Definition Language (SDL) and can then use automation to transform it into a fully descriptive cloudformation template that implements the spec.


> Sources

> Building Serverless Contact Form For Static Websites / Faizan Bashir.

