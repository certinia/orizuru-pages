---
---

# Prerequisites
You will need to install a number of programs and create several accounts before you can start building apps with Orizuru.

#### Versions
Orizuru Tools has been tested with the following versions of prerequisites. Earlier versions *may* work, but we have not verified this. If possible, you should upgrade to the latest Generally Available versions.

|Program|Minimum version|
|-------|---------------|
|Node.js|8.9.1|
|NPM|5.5.1|
|Heroku CLI|6.14.38|
|SFDX CLI|6.0.16|

### Node.js
Get it [here](https://nodejs.org/en/).

You can check if it's already installed by running the following command on the command line.
```shell
node -v
```
This should return a valid version number, e.g.
> v8.9.1

### NPM
NPM is bundled with Node.js.
If it's not installed, then you should install a more recent version of Node.js.

You can check if it's already installed by running the following command on the command line.
```shell
npm -v
```
This should return a valid version number, e.g.
> v5.5.1

### Heroku CLI
Get it [here](https://devcenter.heroku.com/articles/heroku-cli).

You can check if it's already installed by running the following command on the command line.
```shell
heroku -v
```
This should return a valid version number, e.g.
> heroku-cli/6.14.38-9bfc11a (darwin-x64) node-v9.2.0

### SFDX CLI
Get it [here](https://developer.salesforce.com/tools/sfdxcli).

You can check if it's already installed by running the following command on the command line.
```shell
sfdx -v
```
This should return a valid version number, e.g.
> sfdx-cli/6.0.16-3780698 (darwin-x64) node-v8.6.0

### Git CLI
Get it [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

Check if you already have it by running the following command on the command line.
```shell
git --version
```
This command should return a valid version number, e.g.
> git version 2.13.6 (Apple Git-96)

### Heroku Account
Sign up for one [here](https://signup.heroku.com/).

Ensure you are logged into your account in the Heroku CLI by running the following command on the command line.
```shell
heroku apps
```
This command should list your Heroku applications.
If you are not logged in, the Heroku CLI will prompt you to enter your username and password. Do so.
> === you@example.com Apps <br>
> my-orizuru-app (eu)

Note: You should enter your billing details in Heroku.
Although most of the Orizuru templates use free dynos and free plans for add-ons, installing add-ons will fail if you haven't entered billing details, *even if the add-on is free*.

### SFDX Developer Hub
Sign up for a trial [here](https://developer.salesforce.com/promotions/orgs/dx-signup).

### Orizuru Tools
Orizuru tools are installed using NPM. Run the following on the command line:
```shell
npm install @financialforcedev/orizuru-tools --global
```

You may receive an EACCES error when you try to install a package globally.
This indicates that you do not have permission to write to the directories that npm uses to store global packages and commands.
Refer to the [npm docs for fixing permissions](https://docs.npmjs.com/getting-started/fixing-npm-permissions) to resolve this.

You can check if you already have it by running the following command on the command line.
```shell
orizuru -v
```
This command should return a valid version number, e.g.

> FinancialForceDev Orizuru <br>
> Version: 1.1.0 <br>
> Copyright (c) 2017 FinancialForce.com, inc.  All rights reserved.
