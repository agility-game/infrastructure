# 500 - Setting Up Test Automation

Let's look at our example test automation suite next. You can use pretty much any testing framework, programming language or automation tool with GitLab and the approach we are describing here. For this article we are going to use a simple JavaScript (Node.js) based framework, in our case Mocha/Chai. If your team uses a different programming language such as Ruby, Java, PHP, .NET etc., you would just choose a different framework (and corresponding Docker container).

With the ```node``` Docker container we use, everything is already pre-installed and ready to use. So we can just use the ```npm``` package manager to install our required packages (i.e. the testing framework we want to use). So inside our development container we will just install these packages:

```
# Run this inside your container
$ npm install --save-dev mocha chai mocha-junit-reporter
```

Running this command will download and install the packages and will also create new ```package.json``` and ```package-lock.json``` files in our project directory with our dependencies (make sure to also commit these files to your repository). When we then check out the code of our repository on another machine or as part of our GitLab CI/CD run in the future, we can easily install all required packages based on these configuration files.

We also want to make it easier to run our automated tests. For this we are adding a few script aliases to the ```scripts``` section of the ```package.json``` file:

```
// package.json
{
  "name": "agility-game-home",
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "mocha": "npx mocha",
    "mocha-junit": "npx mocha --reporter node_modules/mocha-junit-reporter --reporter-options jenkinsMode=1,outputs=1,mochaFile=results/mocha-test-results.xml"
  },
  "devDependencies": {
    "chai": "^5.0.3",
    "mocha": "^10.2.0",
    "mocha-junit-reporter": "^2.2.1"
  }
}
```
github.com/agility-game/home/package.json

We also need an actual ```test suite``` for this example project. Mocha/Chai makes it easy to create some simple test cases. Just add a new ```test.js``` file and add some tests like shown in the example below. You can also find the full file in this [article's GitLab project](https://gitlab.com/testmoapp/example-gitlab-automation).

One of the included tests fails with a random chance of 50%. This way you can see and test both full passes and failures in GitLab CI/CD and see how both scenarios work.

**NOTE**: We have coded below file so that it adheres to the newer ES Module format, using ```import``` instead of ```require```, and ```"type": "module"``` in ```package.json```.

```
// test.js
import * as chai from 'chai';
const assert = chai.assert;

describe('files', function () {
    describe('export', function () {
        it('should export pdf', function () {
            assert.isTrue(true);
        });

        it('should export html', function () {
            assert.isTrue(true);
        });

        it('should export yml', function () {
            assert.isTrue(true);
        });

        it('should export text', function () {
            // Fail in 50% of cases
            if (Math.random() < 0.5) {
                throw new Error('An exception occurred');
            } else {
                assert.isTrue(true);
            }
        });
    });
	
	// [..]
});
```

github.com/agility-game/home/test.js

We can first try our tests and run them in our local development container. You can use the script alias we've added above to run the tests; simply run ```npm run mocha``` inside the container. The output should look like this (sometimes passing or failing one test if you run the command multiple times):

```
# npm run mocha

> agility-game-home@1.0.0 mocha
> npx mocha



  files
    export
      ✔ should export pdf
      ✔ should export html
      ✔ should export yml
      1) should export text


  3 passing (6ms)
  1 failing

  1) files
       export
         should export text:
     Error: An exception occurred
      at Context.<anonymous> (file:///project/test.js:22:23)
      at process.processImmediate (node:internal/timers:478:21)
```

All good! Failings are deliberately created in the test script to test both cases: pass and fail. Don't worry : )
