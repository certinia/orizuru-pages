---
---

# Building Your First App

## Introduction
In under 10 minutes, you can build your own Node.js Heroku application connected to the Lightning Platform.
Make sure you have completed all of the [prerequisites](/docs/prerequisites/).

Don't worry if you're unfamiliar with Node.js, this tutorial won't include a detailed walk-through of the generated source code - but we'll provide code snippets as and when you need them!

This tutorial relates to orizuru-tools version 2.0.3 or later.
Check your current orizuru tools version by running the command below on the command line.
```shell
orizuru -v
```

If your Orizuru version is below 2.0.3, then update to the latest version using the command:
```shell
npm update @financialforcedev/orizuru-tools --global
```

If you have any issues during this tutorial, check out the [troubleshooting](/docs/troubleshooting/) page.
If you're still having problems, [check if similar issues have already been raised in GitHub](https://github.com/financialforcedev/orizuru-tools/issues).
If you encounter an issue that hasn't been raised before, then go right ahead and create a New Issue.

## What Are We Building?
A simple sample app that spans Lightning Platform and Heroku, but has no UI on either side.
We're going to make requests using Execute Anonymous in the Developer Console on the Lightning Platform.
We're going to see the output of handling those requests in the logs on the Heroku App.

And that's all for now! We'll extend this in later tutorials, but first let's make sure we've got the basics covered.

## Create Your Workspace
1. Create an empty directory - in this example we have created the directory `orizuru-tutorial`.
1. Open the command line and navigate to the new empty directory.<br>
    From here on out, whenever you're asked to run a command, ensure you run it from the command line in this directory.

## Use a Template
1. From the command line in the project root, run the command:
    ```shell
    orizuru setup init
    ```
1. You will be asked to choose a template. Choose `web-node-worker`.
1. All Node.js apps need a [package.json](https://docs.npmjs.com/files/package.json), which describes the shape of the application.
    * The tools will create one for you, by asking you some details about your project.
    * It will guess appropriate answers for each question, so just press Enter on each question to accept the default suggestions.
        * The questions will look like this:
            > ? package name: *(orizuru-tutorial)* <br>
            > ? version: *(1.0.0)* <br>
            > ? description: <br>
            > ? git repository: <br>
            > ? keywords: <br>
            > ? author: <br>
            > ? license: *(ISC)*

Congratulations, you've built your first Orizuru app!

You'll notice that your empty directory isn't so empty now - let's take a closer look at the newly generated files and directories.

|Path|Description|
|----|-----------|
|.vscode/|Hidden directory containing configuration files for VisualStudio Code, the recommended IDE for working with Orizuru|
|src/apex/|Source code for the Lightning Platform component of your app|
|src/node/|Source code for the Heroku component of your app|
|.gitignore|Tells git to exclude certain files/directories from source control - see the [docs](https://git-scm.com/docs/gitignore) for more detail|
|.jsbeautifyrc|Tells [JS Beautify](https://www.npmjs.com/package/js-beautify) the conventions to follow when automatically formatting source code, such as javascript or json files|
|.salesforcedx.yaml|Tells the [SFDX one-click deploy button](https://deploy-to-sfdx.com/repo) how to deploy your app to a new scratch org|
|app.json|Tells Heroku about how to build your app, such as which add-ons to install and the number and type of each dyno|
|package.json|Describes the Node.js app|
|Procfile|Tells Heroku about the entry points into the Heroku component of your app|
|sfdx-project.json|Tells SFDX about how to build the Lightning Platform component of your app|

## Deploy Your App
1. You deploy apps to Heroku using git.
    So let's turn the current workspace into a git repository.
    * From the command line in the project root, run the following commands:
        ```shell
        git init
        git add .
        git commit -m "Initial commit"
        ```
    * This should log out something like the following:
        > Initialized empty Git repository in /path/to/orizuru-tutorial/.git/ <br>
        > [master (root-commit) 4514a8d] Initial commit 41 files changed, 2036 insertions(+) <br>
        > create mode 100644 .gitignore <br>
        > create mode 100644 .jsbeautifyrc <br>
        > ...
1. Now let's deploy to Heroku and the Lightning Platform. From the command line in the project root, run the following command:
    ```shell
    orizuru deploy
    ```
    * Note: Make sure you have verified your Heroku account with your credit card details, or this step will fail!
1. You will be asked which Heroku app to deploy to. You can either create a new one, or choose an existing one.<br>
    If you are part of any Heroku enterprise teams, you can create an app in that team.<br>
    For this tutorial, choose `<<Create new Heroku App>>`.
1. Heroku will create a new app, with a random name, in this case `evening-badlands-29385`.<br>
    Make a note of your Heroku app name - you'll need it later on!<br>
    The tools will push the code up to Heroku. Heroku will detect that it's a Node.js project, install the packages it depends on and start running the app.
1. Great! You've got your Heroku app up, and running. If you want to, you can look at it in your [Heroku Dashboard](https://dashboard.heroku.com).
1. Next, you'll deploy to the Lightning Platform.<br>
    The tools will generate a public and private key pair, which will be used for OAuth authentication between the two components of your app.
    * Again, you'll be asked questions and you can just press Enter to accept the default suggestion.
        * The questions will look like this:
        > ? Country Name (2 letter code) *GB* <br>
        > ? State or Province Name (full name) *Some-State* <br>
        > ? Locality Name (eg, city) <br>
        > ? Organization Name (eg, company) *FinancialForce* <br>
        > ? Organizational Unit Name (eg, section) <br>
        > ? Common Name (e.g. server FQDN or YOUR name) *test@test.com*
1. The tools will open a web browser on the Salesforce login page. Login to your Developer Hub. Once you've successfully logged in, you can close the browser.
1. You will be asked which scratch org to deploy to. You can either create a new one, or choose an existing one.
    For this tutorial, choose `<<Create new SFDX scratch org>>`.
    This will deploy the source code, and assign permission sets to the current user.
1. Now you will be asked to create a [Connected App](https://developer.salesforce.com/page/Connected_Apps).
    * Again, you'll be asked questions and you can just press Enter to accept the default suggestion.
        * The questions will look like this:
        > Create Connected App<br>
        >  You are about to be asked to enter information that will be incorporated into your connected app. <br><br>
        > ? Connected App Name *Orizuru* <br>
        > ? Connected App Email *test@test.com*
    * The new Connected App will be pushed to your scratch org.
    * The corresponding `JWT_SIGNING_KEY` will be pushed up to your Heroku app as a config variable.
1. The sample app uses a Named Credential to specify the URL of the Heroku app.
    * Again, you'll be asked questions and you can just press Enter to accept the default suggestion.
        * The questions will look like this:
        > Create Named Credential <br>
        > ? Named Credential Name *Orizuru*
1. Finally, the tools will open your scratch org in a web browser.

Congratulations, you've deployed your first Orizuru app!

But before you get too carried away, you need to some manual post-install steps.
Sorry, but Salesforce don't allow us to do this programmatically (at least, not yet)!

### Manual Post-install Steps

#### Lightning Platform Post-install Steps
We want to let admins in the subscriber org control which users have access to the connected app, rather than making each user go through the OAuth flow.
1. In the scratch org's Setup, type 'Manage Connected Apps' into the Quick Find search box.
1. Click on Manage Connected Apps in the sidebar. Here you'll see the connected app we prepared earlier.
1. Click on the Edit button next to the Orizuru connected app.
1. In the **OAuth policies** section, change **Permitted Users** from *All users may self-authorize* to *Admin approved users are pre-authorized*.
    * Ok the popup that warns you that currently logged in users will be denied access - there won't be any.
1. Press the Save button at the bottom of the Connected App page.
1. Back on the Manage Connected App page, click on the name of the Connected App.
1. In the **Permission Sets** section, press the **Manage Permission Sets** button.
1. Tick the checkbox next to the OrizuruAdmin permission set, which is already assigned to the current user, then press Save.

#### Heroku Post-install Steps
1. If you created your Heroku app in an Enterprise Team, you may skip this step.
1. Otherwise, you will need to activate your free worker dyno, which is switched off by default.
1. From the command line in the project root, run the following command to switch on the worker dyno, but replace `evening-badlands-29385` with the name of your own Heroku app.
    ```shell
    heroku ps:scale worker=1 --app evening-badlands-29385
    ```
    * This should log out the following
        > Scaling dynos... done, now running worker at 1:Free

## Create Your First Job
Ok, let's recap.
* You've got a scratch org with a named credential, Connected App and some Apex classes.
* You've got a Heroku app with:
    * a web dyno, with an express webserver up and ready to receive requests and publish them to a job queue.
    * a worker dyno, ready to handle jobs in the job queue.

This is a just a skeleton of an app; it doesn't actually do anything yet!
We need to define the types of work we want to perform, and how to perform them.

### Create the Avro Schema
First, we need to make sure that the Lightning Platform and Heroku have a consistent model to describe jobs.
We'll use [Apache Avro](https://avro.apache.org/docs/current/), which allows us to declare the model as JSON in an Avro schema.
Our Node.js app can read the schema dynamically while the app is running.
However, we will need to perform code-generation for Apex which is statically typed.

1. Create the Avro schemas.
    * In `src/node/lib/schema/` create a directory: `api`.
    * In `src/node/lib/schema/` create a file: `fullname_incoming.avsc`.
    * In `src/node/lib/schema/api/` create a file: `fullname.avsc`.
    * In both files, paste in this schema definition:
        ```json
        {
            "type": "record",
            "namespace": "com.example",
            "name": "FullName",
            "fields": [
                { "name": "first", "type": "string" },
                { "name": "last", "type": "string" }
            ]
        } 
        ```
    * You can delete the `add-all-avro-schemas-here.md` file, which is a placeholder for the schemas and simply contains the sample schema definition above.
        
1. Now generate the Apex transport classes from the Avro schema.
    From the command line in the project root, run the command:
    ```shell
    orizuru setup generate-apex-transport src/node/lib/schema/api src/apex/app/main/default/classes
    ```
    * This should log out something like the following:
    > Generating apex transport classes /path/to/orizuru-tutorial/src/node/lib/schemas/fullname.avsc<br><br>
    > Generated apex transport classes (OrizuruTransport.cls) in: /path/to/orizuru-tutorial/src/apex/app/main/default/classes

### Create the Node Handler
1. In `src/node/lib/handler` create a file: `fullname.js`.
    * **Note:** This template app requires filenames to match each Avro schema to the corresponding handler. The filenames MUST match in order for the handler to work correctly.
    * Copy/paste the code below into `fullname.js`.
        ```javascript
        'use strict';

        const
            debug = require('debug-plus')('fullname-handler');

        module.exports = ({ message, context }) => {
            debug.log('Handled event for schema \'api/fullname\'...');
            debug.log('Context:');
            debug.log(JSON.stringify(context));
            debug.log('Message:');
            debug.log(JSON.stringify(message));
        };

        ```
    * You can delete the `add-all-handlers-here.md` file, which is a placeholder for the handlers and simply contains the sample code above.

## Deploy the updated code
1. First, let's increase the debug log level in the Heroku app.<br>
    From the command line in the project root, run the following command to set the DEBUG config variable, but replace `evening-badlands-29385` with the name of your own Heroku app.
    ```shell
    heroku config:set "DEBUG=*" --app evening-badlands-29385
    ```
    * This will set the config variable and restart all dynos
        > Setting DEBUG and restarting evening-badlands-29385... done, v9<br>
        > DEBUG: *
1. Next, commit all of the new files to git and deploy the code again.
    ```shell
    git add .
    git commit -m "Add Fullname job"
    orizuru deploy
    ```
    * Again, you'll be asked questions and you can just press Enter to accept the default suggestion.
        * The tools will remember the Heroku app and scratch org you created earlier, and will highlight them by default when asking you which app you want to deploy to.
        * You will be prompted to recreate the Connected App and the Named Credential, just press Enter to accept the default values.<br>
            This will overwrite the ones deployed before, but will have no effect.

## Try It Out!
1. The `orizuru deploy` should have opened a web browser connected to your scratch org.
    * You can open one at any time using the command
    ```shell
    sfdx force:org:open
    ```
1. Open your app from the [Heroku Dashboard](https://dashboard.heroku.com).
    * In the **More** menu at the top right, click on **View Logs**.
1. In the scratch org, in the **Setup** menu at the top right (i.e. the gear icon), click on Developer Console.
1. In the Developer Console, in the **Debug** menu at the top, click on **Open Execute Anonymous Window**.
1. Copy/paste the code below into the Execute Anonymous Window.
    ```java
    String endpoint = 'callout:Orizuru/api/fullname';
    //Feel free to change this to your own name!
    OrizuruTransport transport = new OrizuruTransport.com_example_FullName('Ori', 'Zuru');
    String sessionId = UserInfo.getSessionId();
    HerokuConnector.newInstance().post(endpoint, transport, sessionId);
    ```
1. Click on the Execute button.
1. Back in the Heroku logs, you will see logging showing:
    * The web server receiving the initial request
    * The worker picking the job up asynchronously
    * The worker logging out your name!
    > 2017-11-23T13:07:52.698250+00:00 heroku[router]: at=info method=POST path="/api/fullname" host=evening-badlands-29385.herokuapp.com request_id=6ae3e116-d2d6-4507-98d2-8a615606f269 fwd="85.222.130.8" dyno=web.1 connect=0ms service=1245ms status=200 bytes=445 protocol=https <br><br>
    > 2017-11-23T13:07:52.710244+00:00 app[worker.1]: Thu, 23 Nov 2017 13:07:52 GMT boilerplate:worker:log Handler received com.example.FullName event. <br><br>
    > 2017-11-23T13:07:52.711212+00:00 app[worker.1]: Thu, 23 Nov 2017 13:07:52 GMT fullname-handler:log Handled event for schema 'api/fullname'... <br><br>
    > 2017-11-23T13:07:52.711940+00:00 app[worker.1]: Thu, 23 Nov 2017 13:07:52 GMT fullname-handler:log {"first":"Ori","last":"Zuru"}
    * Note: You may receive a 401 (Unauthorized) error while the Connected App is replicated across Salesforce instances. Try again in 5 minutes if you see logging like this:
        > 2017-11-23T13:07:52.698250+00:00 heroku[router]: at=info method=POST path="/api/fullname" host=evening-badlands-29385.herokuapp.com request_id=6ae3e116-d2d6-4507-98d2-8a615606f269 fwd="85.222.130.8" dyno=web.1 connect=0ms service=620ms status=401 bytes=415 protocol=https

For the third time, congratulations!
You've built, deployed and used your first Orizuru app!
