---
layout: post
title: When to choose Microservices Architecture Over Monolithic?
categories:
  - Software Development
tags:
  - Developers
header:
  teaser: /images/microservice.png
---

From the last couple of years, I’ve heard repeatedly about microservices architecture vs. monolithic, why we should adopt microservices, how to make your application microservice based, and so on and so forth.

I've also have some thoughts about it as per my knowledge like what are they, which one to choose & why?

![Docker containers](/images/microservice.png)

## Monolithic Architecture

When developing a server-side application you can start it with a modular hexagonal or layered architecture which consists of different types of components like:

- **Presentation** — responsible for handling HTTP requests and responding with either HTML or JSON/XML (for web services APIs).
- **Business logic** — the application’s business logic.
- **Database access** - data access objects responsible for accessing the data from database.
- **Application integration** - integration with other services (e.g. via Messaging or REST API).

It works well in the early stages of the project or the application. Most of the big & successful applications which exists today were started as a monolith.

### Pros

- Simple to develop & test. For example, you can implement end-to-end testing by simply launching the application and testing the UI with Selenium.
- Simple to deploy. You just have to copy the packaged application to a server.
- Simple to scale horizontally by running multiple copies behind a load balancers.

### Cons

- This simple approach has a limitation in size and complexity.
- The application is too large and complex to fully understand and made changes fast and correctly.
- The size of the application can slow down the start-up time.
- You must redeploy the entire application on each update.
- Impact of a change is usually not very well understood which leads to demand extensive manual testing.
- Continuous deployment becomes difficult.
- Monolithic applications can also be difficult to scale when different modules have conflicting resource requirement.
- Another problem with monolithic applications is reliability. Bug in any small module(e.g. memory leak) can potentially bring down the entire process down. Moreover, since all instances of the application are identical, the bug may impact the availability of entire application.
- Monolithic applications have a barrier to adopting new technologies or updates. Since changes in frameworks or languages can impact the whole application which is extremely cost effective in terms of cost & time.

## Microservices Architecture

The idea is to split your application into a set of smaller, interconnected services instead of building a single monolithic application. Each microservice is a small application that has its own hexagonal architecture consisting of business logic with various adapters. Some microservices would expose a REST, RPC or message-based API and most services consume APIs provided by other services. Other microservices might implement a web UI.

The Microservice architecture pattern significantly impacts the relationship between the application and the database. Instead of sharing a single database schema with other services, each service has its own database schema. On the one hand, this approach is at odds with the idea of an enterprise-wide data model. Also, it often results in duplication of some data.

### Pros

- It tackles the problem of complexity by decomposing the application into a set of manageable services which are much faster to develop, and much easier to understand and maintain.
- It enables each service to be developed independently by a team that is focused on that service.
- It reduces the barrier of adopting new technologies since the developers are free to choose whatever technologies make sense for their service and not bounded to the choices made at the start of the project.
- The microservices architecture enables each microservice to be deployed independently. As a result, it makes continuous deployment possible for complex applications.
- The microservices architecture enables each service to be scaled independently.

### Cons

- Microservices architecture adding a complexity to the project just by the fact that a microservices application is a distributed system.
- Microservices has the partitioned database architecture, which becomes more challenging for developers to maintain & manage infrastructure.
- Testing a microservices application is also much more complex than in case of the monolithic application.
- It is more difficult to implement changes that span multiple services. You need to carefully plan and coordinate the rollout of changes to each of the services.
- Deploying a microservices-based application is also more complex. A monolithic application is simply deployed on a set of identical servers behind a load balancer. In contrast, a microservice application typically consists of a large number of services. Each service will have multiple runtime instances.
- Since the overall infrastructure becomes large compared to monolithic you will end up having more resources to develop & maintain your application.

## Monolithic or microservices?

Building complex applications are inherently difficult. A Monolithic architecture better suits simple, lightweight applications. There are opinions which suggest starting from the monolith first and others which recommend not to start with monolith when your goal is a microservices architecture. But anyway it is important to understand Monolithic architecture since it is the basis for microservices architecture where each service by itself is implemented according to monolithic architecture. The Microservices architecture pattern is the better choice for complex, evolving applications. Actually, the microservices approach is all about handling a complex system, but in order to do so the approach introduces its own set of complexities and implementation challenges.

Finally, the call is yours to choose the approach but I would suggest thinking from long-term perspective & considering the available resources(**budget, time, team**) when you start designing your new architecture.