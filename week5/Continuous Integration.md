# What is Continuous Integration?

##### Continuous Integration (CI) is a development practice where developers integrate code into a shared repository frequently. it is the practice of integrating changes from different developers in the team into a mainline as early as possible, Each integration can then be verified by an automated build and automated tests. 

By integrating regularly, you can detect errors quickly, and locate them more easily.

This makes sure the code individual developers work on doesn’t divert too much. When you combine the process with automated testing, continuous integration can enable your code to be dependable.

<b>Example:</b>
1) The developer takes code from the shared repository to work on it, possibly creating a new branch for a new feature.

2) Once the new feature is complete, the developer pushes it back to the shared repository.

3) The CI server determines that changes have been made and begins to build and test the application, ensuring that the changes have not caused the application to break. The tests focus on <b>total functionality</b> to ensure that no part of the application has been compromised.

4) The development team is notified of the test results. In the event of a failure, the team will know that the new code has caused the failure and can begin to isolate and fix the issue. If the changes are successful, the team moves on to the continuous delivery phase.

### Continuous Deployment

Continuous Deployment is closely related to Continuous Integration and refers to keeping your application deployable at any point or even automatically releasing into production if the latest version passes all automated tests.

### Continuous Delivery

is the practice of keeping your codebase deployable at any point. Beyond making sure your application passes automated tests it has to have all the configuration necessary to push it into production.



![deployment](https://ajiethkumar.files.wordpress.com/2017/04/slide-14-1024-e1491333889709.jpg)


## Travis CI


Travis CI is an open source hosted continuous integration tool used to build and test software projects hosted at GitHub. 

It does this by automatically testing your code every time you push it up to GitHub, returning a report that states if the new build passed or failed all of the tests (such as those wrtitten in TAPE contained within the JSON file for the project), 

![travis](https://i.pinimg.com/originals/74/62/f9/7462f9e8b7e415f45c88f7243e40ecb7.png)

Travis CI is a web based platform and can be used to test build versions of your code simply by creating an account and signing into the webpage at https://travis-ci.org/ and linking it to your GitHub account. It then has access to your repos and can run tests everytime you push/pull new code.



![travisDashboard](https://cdn.travis-ci.org/images/landing-page/laptop-f308ed79defa4f49c5f01af29a60084d.png)


Here is a great step by step turotial on how to get travis set up and running on your code: https://github.com/dwyl/learn-travis

Below we will show you how to use Travis CI to to test the intergrations of your code.



## Part 2: Continuous Integration Example


- Initiating the travis.yml file in order to integrate the Travis-Ci into your repo.

![Travis.yml](https://i.imgur.com/6O0QpMT.png)

- This how a failing test looks like in TravisCi

![FaillingTestExample](https://i.imgur.com/JlTVnz3.png)

- This how a passing test looks like in TravisCi

![passingTestExample](https://i.imgur.com/5fmVL5q.png)

- You can access all tests logs of all the branches and see the tests history as well.

![branches](https://i.imgur.com/ThbERk1.png)

- In this screenshot you can see how Travis progress on your github pull request page, it is useful so you make sure you are not merging a broken code to your project.

![github & Travis integration](https://i.imgur.com/JUwoTd8.png)
![github & Travis integration](https://i.imgur.com/QOdWxCJ.png)
![](https://i.imgur.com/2bnykBZ.png)
