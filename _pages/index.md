---
title: Welcome to Orizuru
permalink: /
layout: default
lang: en
---

# Welcome to Orizuru

Salesforce Heroku is an elastic cloud compute platform which perfectly complements the core Salesforce platform. With Heroku you can choose which programming language you want to use based on the skills you have, the suitability of the language to the type of work you are doing, or by the availability of existing libraries and frameworks for each language. In addition, the Heroku platform allows you to smoothly scale to your computing demands - scaling *up* memory and CPU capabilities, or scaling *out* the number of processes you have available to run in parallel.

Heroku is a great choice where processes would be a poor fit to run in Apex - either because of the memory or CPU time they would consume in Apex, or because publicly available Java, Node, Python or Ruby libraries reduce the amound of code you would need to write.

FinancialForce Orizuru sets out to make it as simple as possible to add Heroku compute power to your Salesforce development projects.

Orizuru has three main parts:

First, we we have a number of freely available packages which provide features which will be regularly needed when building Salesforce-Heroku hybrid projects. These include identity, authentication and process flow between the platforms. These packages are written in Node.js and available via NPM. This is the [Orizuru framework](../framework/).

Second, we have built some command line tools that save a heap of time starting new projects. The tools allow you to create your initial project, include the Orizuru framework, and configure identification and authentication. These are the [Orizuru tools](../tools/).

Third, we are providing a sample application which demonstrates the Orizuru framework in a realistic and relatable way. This is he [Orizuru Sample App](../sample/).
