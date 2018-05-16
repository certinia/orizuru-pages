---
title: Sample App
permalink: /sample/
layout: default
lang: en
---

# Orizuru Sample App
[View on Github](https://github.com/financialforcedev/orizuru-sample-app)

This sample app uses the Orizuru framework to solve a real world business problem:

*Your organization makes many deliveries to destinations (Salesforce Contacts). You have many delivery drivers (Salesforce Users), vehicles and warehouses, and you want to determine the most efficient way for your deliveries to reach every destination in a single day.*

This is a generalization of the well-known [Travelling Salesman Problem (TSP)](https://en.wikipedia.org/wiki/Travelling_salesman_problem), which is a difficult problem to solve, and computationally demanding - it would not be a good fit for Apex. It is also a problem for which real world solutions exist in Java and other languages.

The Orizuru sample app uses the [Graphhopper jsprit](https://github.com/graphhopper/jsprit) Java solver to calculate optimal routes.
