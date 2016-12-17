---
title: Frequently Asked Questions
---

# What is a microservice ?

A microservice typically refers to a small piece of software, that only perform
one or a few tasks, hopefully well.

Complex applications can be then built by combining multiple microservices. This
way of structuring applications aims to promote flexibility and reusability of code.

# Where can I learn more about microservices ?

Here are the Wikipedia pages on [Microservices](https://en.wikipedia.org/wiki/Microservices)
and [Service-oriented architecture](https://en.wikipedia.org/wiki/Service-oriented_architecture).

The following two websites also present good descriptions :
[martinfowler.com](http://www.martinfowler.com/articles/microservices.html),
[microservices.io](http://microservices.io/patterns/microservices.html)

Here are some books about the subject :

* [Building Microservices](https://smile.amazon.com/Building-Microservices-Designing-Fine-Grained-Systems/dp/1491950358)

* [Production-Ready Microservices](https://smile.amazon.com/Production-Ready-Microservices-Standardized-Engineering-Organization/dp/1491965975)

* [REST API Design Rulebook](https://smile.amazon.com/REST-Design-Rulebook-Mark-Masse/dp/1449310508)

* [RESTful Web APIs](https://smile.amazon.com/RESTful-Web-APIs-Services-Changing/dp/1449358063)

# What is a container ?

A container is a way of packaging software in order to make execution and deployment easier. The most popular container technology today is [Docker](https://www.docker.com/what-docker), and this is the platform used by this project.

# What is REST ?

REST stands for Representational state transfer, a convention for APIs that follows the HTTP standards to provide [*a uniform and predefined set of stateless operations*](https://en.wikipedia.org/wiki/Representational_state_transfer).

This is the primary way of interacting with the microservices provided here.

# Why did you create the MSA ?

I often see interesting code, but it's using a different language or framework
than the project I'm currently working on, and integration can be a pain.

Sometimes I look back at old projects of mine, and find it hard to get them
working again, either because my computer is configured differently and/or I
forgot to document a step.

This project is a humble attempt to fix those problems.

# MSA Objectives

- Lower the barrier to entry

  - by providing a quick guide and examples on how to use it

  - by packaging it in a format that can be deployed in less than 5 minutes

- Promote reusability

  - by exposing the functionality over standardized APIs easy to integrate

  - by writing simple software, that do one or very few things, hopefully well

- Provide good enough performance

  - by leveraging techniques such as caching when it makes sense

  - by making it possible to throw more hardware at the problem, if needed


# Can I submit a microservice to the MSA ?

Absolutely ! Check out the [Contribute](/contribute) page to know how.

# Where can I find templates to create my own microservices ?

[This page](/templates) provides more information about the templates, how they are structured and how they can be used to create new microservices.

All the source code can be found on the following [Github page](https://github.com/TheMicroservicesAgency).
