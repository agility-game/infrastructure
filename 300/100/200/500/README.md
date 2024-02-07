# 500 - Setting Up Test Automation

Let's look at our example test automation suite next. You can use pretty much any testing framework, programming language or automation tool with GitLab and the approach we are describing here. For this article we are going to use a simple JavaScript (Node.js) based framework, in our case Mocha/Chai. If your team uses a different programming language such as Ruby, Java, PHP, .NET etc., you would just choose a different framework (and corresponding Docker container).

With the ```node``` Docker container we use, everything is already pre-installed and ready to use. So we can just use the ```npm``` package manager to install our required packages (i.e. the testing framework we want to use). So inside our development container we will just install these packages:

```
# Run this inside your container
$ npm install --save-dev mocha chai mocha-junit-reporter
```

== WE ARE HERE ==
