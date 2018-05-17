---
packages:
    - name: Orizuru Tools
      lang: Node.js
      desc: Command Line tool to install Orizuru packages, generate source code and deploy to both Lightning Platform and Heroku
      gh: https://github.com/financialforcedev/orizuru-tools
      npm: https://npmjs.com/package/@financialforcedev/orizuru-tools
    - name: Orizuru
      lang: Node.js
      desc: Web server that supports publishing/subscribing events in your chosen Transport Layer
      gh: https://github.com/financialforcedev/orizuru
      npm: https://npmjs.com/package/@financialforcedev/orizuru
    - name: Orizuru
      lang: Java
      desc: Web server that supports publishing/subscribing events in your chosen Transport Layer
      gh: https://github.com/financialforcedev/orizuru-java
    - name: Orizuru Auth
      lang: Node.js
      desc: Middleware that uses OAuth and JWT assertions to establish the authenticity of requests from the Lightning Platform, and to read and write data back to the corresponding Salesforce org
      gh: https://github.com/financialforcedev/orizuru-auth
      npm: https://npmjs.com/package/@financialforcedev/orizuru-auth
    - name: Orizuru Transport RabbitMQ
      lang: Node.js
      desc: Transport layer that uses AMQP as the message broker
      gh: https://github.com/financialforcedev/orizuru-transport-rabbitmq
      npm: https://npmjs.com/package/@financialforcedev/orizuru-transport-rabbitmq
    - name: Orizuru Transport RabbitMQ
      lang: Java
      desc: Transport layer that uses AMQP as the message broker
      gh: https://github.com/financialforcedev/orizuru-transport-mq-java
    - name: Orizuru Transport Redis
      lang: Node.js
      desc: Transport layer that uses Redis as the message broker
      gh: https://github.com/financialforcedev/orizuru-transport-redis
      npm: https://npmjs.com/package/@financialforcedev/orizuru-transport-redis
    - name: Orizuru Transport Kafka
      lang: Node.js
      desc: Transport layer that uses Kafka as the message broker
      gh: https://github.com/financialforcedev/orizuru-kafka
      npm: https://npmjs.com/package/@financialforcedev/orizuru-kafka
    - name: Orizuru Open API
      lang: Node.js
      desc: Generates OpenAPI documents from Avro schemas
      gh: https://github.com/financialforcedev/orizuru-openapi
      npm: https://npmjs.com/package/@financialforcedev/orizuru-openapi
---

# Package Overview

| Package | Links |
|---------|:-----:|
{% for package in page.packages -%}
|__{{ package.name }}__<br/>_Language: {{ package.lang }}_<br/><br/>{{ package.desc }}<br/><br/>|[![View in Github][gh] Github]({{ package.gh }}){% if package.npm %}<br/>---<br/>[![View NPM Package][npm]]({{ package.npm }}){% endif %}|
{% endfor %}


[gh]: {{ site.baseurl }}/assets/images/github.svg
[npm]: {{ site.baseurl }}/assets/images/npm-logo.svg

