---
---

# Introduction
Orizuru is a project that helps you build solutions that span Heroku and the Lightning Platform, to get the best of both worlds.

## Two Platforms
The Lightning Platform (previously referred to as Force.com) gives you the *Salesforce advantage*, so that:
* You can build quickly with clicks-not-code
* You can leverage Einstein for Artificial Intelligence
* The end user can make customizations easily
* The end user can use your application from a mobile app

Heroku lets you deploy, run and manage remote web applications. Your app runs in isolated virtualized containers, called dynos. Here, you have far more control than on the Lightning Platform, so that:
* You have a choice of programming language(/s) and third-party libraries
    * Choose those that best solve your business use case
    * Choose those that best complement your existing skillset
* You can complete huge workloads faster using more dynos, or more powerful dynos
* You have greater control over delivering fixes and new functionality

## The Problem
Before you can build your Heroku/Lightning hybrid application, you will need to answer some questions:
* How do I go from Lightning to Heroku?
    * How do I expose the Heroku application to web traffic?
    * How do I ensure the request has come from a genuine Salesforce user?
* How do I go from Heroku back to Lightning?
    * How do I connect to the correct Salesforce org?
    * How do I connect as the user who made the original request?
    * How do I support mulitenancy
* How do I implement background processing?
    * How do I enqueue jobs?
    * How do I keep the user informed of progress?
    * How can I define Data Transfer Objects (DTOs) to ensure my processes have enough information to complete jobs?

Orizuru tackles these common problems, leaving you to concentrate on your own application logic.
