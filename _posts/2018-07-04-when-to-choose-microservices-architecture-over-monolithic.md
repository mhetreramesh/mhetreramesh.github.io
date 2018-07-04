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