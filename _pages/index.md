---
title: Welcome to Orizuru
permalink: /
layout: default
isHomepage: true
lang: en
---

# Welcome to Orizuru

Salesforce [Heroku](https://developer.salesforce.com/platform/heroku) is an elastic cloud compute platform which perfectly complements the core Salesforce platform. With Heroku you can choose which programming language you want to use based on the skills you have, the suitability of the language to the type of work you are doing, or by the availability of existing libraries and frameworks for each language. In addition, the Heroku platform allows you to smoothly scale to your computing demands - scaling *up* memory and CPU capabilities, or scaling *out* the number of parallel processors you have available.

Heroku is a great choice where processes would be a poor fit to run in Apex - either because of the memory or CPU time they would consume in Apex, or because publicly available Java, Node, Python or Ruby libraries significantly reduce the amount of code you would need to write.

*FinancialForce Orizuru sets out to make it as simple as possible to add Heroku compute power to your Salesforce applications*

Orizuru has three main parts:

First, we we have a number of freely available packages which provide features which are frequently needed when building Salesforce-Heroku hybrid projects. These include identity, authentication and process flow. These packages are written in Node.js (available via NPM) and Java.  
[This is the Orizuru framework](/docs/package-overview/)

Second, we have built some command line tools that save time when starting new projects. The tools allow you to create your initial project, include the Orizuru framework, and configure security.
[This is a guided tutorial for using Orizuru tools](/docs/tutorial-building-your-first-app/)

Third, we are providing a sample application which demonstrates the Orizuru framework in a realistic and relatable way.  
[This is the Orizuru Sample App](../sample/)

## Why "Orizuru"?
Orizuru means "folded crane" and is the most recognizable and most followed origami pattern. FinancialForce Orizuru is offered as a pattern for building Salesforce Hybrid applications. Japanese words are often used at Heroku; the name *Heroku* is a combination of "heroic" and "haiku" and is itself a nod to Yukihiro "Matz" Matsumoto, best known for the Ruby programming language, which was the first programming language to be supported by Heroku.
