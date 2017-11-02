---
title: Framework
permalink: /framework/
layout: default
lang: en
---

# Orizuru Framework

## Orizuru
[View on Github](https://github.com/financialforcedev/orizuru) | [View on NPM](https://www.npmjs.com/package/@financialforcedev/orizuru)

One of the key concepts for scalable Heroku applications is the principle of asynchronous or background workers:

> Background jobs are key to building truly scalable web apps as they transfer both time and computationally intensive tasks from the web layer to a background process outside the user request/response lifecycle. This ensures that web requests can always return immediately and reduces compounding performance issues that occur when requests become backlogged.  
[Heroku Dev Center - Worker Dynos, Background Jobs and Queueing](https://devcenter.heroku.com/articles/background-jobs-queueing)

This is the main Orizuru package and provides the means to define the schema for a work request, and facilitate the transport of the work request from Heroku API through a message queue to the worker process. 

This package also provides the means to incorporate a Node.js worker.

## Orizuru Java
[View on Github](https://github.com/financialforcedev/orizuru-java)

Provides the means to incorporate a Java worker.

## Orizuru Transport RabbitMQ
[View on Github](https://github.com/financialforcedev/orizuru-transport-rabbitmq) | [View on NPM](https://www.npmjs.com/package/@financialforcedev/orizuru-transport-rabbitmq)

Orizuru depends upon a message queue backing service. This library provides Orizuru support to use RabbitMQ as the message queue for Node.js workers

## Orizuru Transport RabbitMQ Java
[View on Github](https://github.com/financialforcedev/orizuru-transport-rabbitmq-java)

Provides Orizuru support to use RabbitMQ as the message queue for Java workers.

## Orizuru Authentication
[View on Github](https://github.com/financialforcedev/orizuru-auth) | [View on NPM](https://www.npmjs.com/package/@financialforcedev/orizuru-auth)

Provides an authentication mechanism for use in Heroku and designed specifically to make use of Salesforce as an identity provider - facilitating identification and validation of users, and the facility to do authenticated calls back into Salesforce.

## Orizuru OpenAPI
[View on Github](https://github.com/financialforcedev/orizuru-openapi) | [View on NPM](https://www.npmjs.com/package/@financialforcedev/orizuru-openapi)

Provides support for OpenAPI/Swagger on the Heroku APIs - which allows the APIs to be used as a Salesforce External Service.


