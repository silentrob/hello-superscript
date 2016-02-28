## SuperScript Bootstrap

Welcome to the wonderful world of building chatbots!

We will assume you already have Node and NPM installed. To use SuperScript you need to make sure you have Node 0.12.x installed. Later version do not work yet.

You can start by cloneing this repo locally using the command 
`git clone https://github.com/silentrob/hello-superscript.git`

You will then want to run `npm install` This will load in all the dependencies. 

This example will show you how to create a basic trigger, topic and plugin, and use 2 sample clients. (Telnet and Slack)

## Basic Workflow

1. You will want to make sure you have `mongo` running, all the conversation and user data is stored in mongo, namely, `Gambits`, `Replies`, `Topics` and `Users`.

This can be done by downloading mongo from `https://www.mongodb.org/downloads#production`

Once installed you run it from the command line by `sudo mongod`

2. Lets compile our first trigger and store that in mongo. I already created the topic folder and ss file see `./topics/main.ss` 

We can compile the data two ways, either by typing `parse` from the command line which generates a intermediate json representation that we can manually import, or by doing a parse and load combind step. Lets do the latter as it removes the need to manually import the JSON file ourselves.

Run `./node_modules/superscript/bin/cleanup.js`

The output should look something like:
```
users is clear
topics is clear
replies is clear
gambits is clear
Time to Process 1.009 seconds
Number of topics 2 parsed.
Number of gambits 1 parsed.
Number of replies 1 parsed.
Number of convos 0 parsed.
Number of Gambits: 0
Number of Replies: 0
Everything imported
```

It should be noted that this task will also cull the existing data before adding new data.

As we can see we have added one Gambit and One Reply as expected. We also have two topics, one called `main`, and one the system creates called `random`.


