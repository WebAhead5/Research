# Test coverage

## What is test coverage?
Test Coverage is an important indicator of software quality and an essential part of software maintenance.

It is defined as a metric in Software Testing that measures the amount of testing performed by a set of test.  it is a technique to ensure that your tests are testing your code or how much of your code you exercised by running the test.

Test coverage can help in monitoring the quality of testing and assist in directing the test generators to create test cases that cover areas that have not been tested. It helps in determining a quantitative measure of Test coverage, which is an indirect measure of quality and identifies redundant test cases that do not increase coverage.

## Why is test coverage useful? 

* It can assure the quality of the test.
* Defect prevention at early stages of project life cycle.
* It helps in finding areas of a program not exercised by a set of test cases.
* Time, Cost and Scope will be in control.
* It can help to determine the paths in your application that were not tested.
* It can determine all the decision points and paths used in the application, which allows you to increase test coverage.
 
## What are Istanbul and nyc, and how do they improve testing?

NYC is a command line interface for Istanbul (a code coverage tool). It can be used to generate a coverage report and give various outputs to highlight lines/functions/modules/etc that have not been covered by testing.

This speeds up testing and ensures that maximum test coverage can be achieved.

The NYC Node module can be used to generate test coverage reports. These reports will track how much of the application code is covered by unit tests. If any code is not being called or tested, NYC will indicate the ‘uncovered’ lines in both the command line and the generated reporting page.


the original purpose of nyc was to  allow a user to capture test
coverage, regardless of how programs are spawning subprocesses,
without     requiring any changes in the instrumented code.

As for the relationship between istanbul and nyc; nyc did start separately, but the two projects merged together as Istanbul moved towards a 2.0 API ... the idea being that nyc would provide the command line interface to this new API.

nyc would be the all-in-one, simple-to-use, command line interface for the Istanbul 2.0 API.


## How to Set Up Testing with NYC and Istanbul

1. Install your dependents:

``` $ npm i -D tape nyc ```

2. Add the following scripts to your package.json
     
![project.json shortcuts](https://i.imgur.com/rGuNxVz.png)


3. Run NYC in the terminal

![run nyc in terminal](https://i.imgur.com/eGm46l6.png)

4. Run coverage in the terminal

![run coverage in terminal](https://i.imgur.com/FZOhWEz.png)

Which gives us the following:


![coverage terminal result](https://i.imgur.com/54NAIBT.png)

(FYI, the below expands on the tabulated items:
* Statements: How many of the statements in you code are executed.
* Branches: Conditional statements create branches of code which may not be executed (e.g. if/else). This metric tells you how many of your branches have been executed.
* Functions: The proportion of the functions you have defined which have been called.
* Lines: The proportion of lines of code which have been executed.
)

Or, if we change the text in our package.json file, we can also get the following:

```
    "coverage":  "nyc --reporter=lcov --reporter=text npm test"
```


![nyc terminal result](https://i.imgur.com/LOyGn06.png)

This [webpage](https://istanbul.js.org/docs/advanced/alternative-reporters/) provides more details on the different viewing options:

It also adds a coverage directory to our app:

![coverage generated directory](https://i.imgur.com/u3ej7yt.png)

5. View summary of test coverage in the index.html file within ~/coverage/lcov-report:

![coverage generated directory - index.html](https://i.imgur.com/RpReTjN.png)

We can open this to see the following:

![index.html ](https://i.imgur.com/oHZvODK.png)

6. Open that index.js file to see which sections of code are missing tests:

![index.html - code snipit](https://i.imgur.com/0vihT43.png)


## Further information

For further information about how test coverage works you can visit these links:

1. [Istanbul (nyc) - Code coverage in Nodejs unit testing](https://www.youtube.com/watch?v=Vw72LgG5AQc)
2. [Code Quality - What is Code Coverage?](https://www.youtube.com/watch?v=Ra42js3AXIQ)
3. [Testing and Code Coverage](https://youtu.be/cxUqnliEWXQ)
4. [Istanbul Tutorials](https://istanbul.js.org/docs/tutorials/)
