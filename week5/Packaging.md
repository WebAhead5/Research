# Packaging

### :bulb: What is it? 

Application software is delivered in units called packages. A package is a collection of files and directories required for a software product, and is usually designed and built by the application developer after completing the development of the application code. A software product needs to be built into one or more packages so that it can easily be transferred to a distribution medium, be mass produced, and installed by administrators.

In short, packaging in the terms of software is the module that can be added to any program to add an additional options, features or functionaly.


                         Then what a dependency is?
 
                 Software dependency occures when the software
                 depends on others to function.
                 So in order to run the software you are developing,
                 you need to install/require the "External" code.


##### There are two types of dependencies:
* A prerequisite package - meaning your package depends on the existence of another package.
* A reverse dependency - meaning another package depends on the existence of your package.

#### Dependecy Hell:

Using many dependencies may cause several problems, we'll mention few of them here, for example;

* Depending on many libraries will require longer download and increases the amount of disk space needed.
* Long chain of dependency: Similar to the previous problem, but this happens when the dependencies must be installed manually. 
* Using several libraries may lead to conflict between dependencies. 
And that happens, for example, when the software requires two different versions of the same library.

---
### Node Package Manager:

The company behind npm, is npm.Inc

And the name stems from when npm first was created as a package manager for Node.js. Where every npm package is defined in file called package.json.

The content of package.json must be written in JSON.

So after installing the package, we can use it in our code by passing it as an argument to the require function
```
// index.js
var lodash = require('lodash');
```

#### Installing NPM:
* Installing the package locally :house:


    `npm install <package_name>`

    This will create the ***node_modules*** directory in your current directory (if one doesn’t exist yet) and will download the package to that directory.
    for further info you can check this [video](https://www.youtube.com/watch?v=JDSfqFFbNYQ&feature=emb_title)

* Installing the package globally :globe_with_meridians: 

    `npm install -g <package_name>`
        Installing a package globally allows you to use the code in the package as a set of tools on your local computer.
    


> [color=#181] One way of intentionally ignoring files that we want Git to ignore is specifing a list of files names in a file thats called `.gitignore`, by doing so, the git will ignore every file that is specified and wasn't tracked before (by git add)
>


------
Sources:

1. [Computer Hope.](www.computerhope.com/)
2. [Oracle Doc's: Packages](https://docs.oracle.com/cd/E19455-01/805-6338/6j5vn5q4e/index.html) & [Oracle Doc's: Dependencies.](https://docs.oracle.com/cd/E19455-01/805-6338/ch3enhancepkg-28289/index.html)
3. [Dependecy Hell.](https://en.wikipedia.org/wiki/Dependency_hell)
4. [Packages and Modules](https://docs.npmjs.com/packages-and-modules/)
5. [Git Ignore](https://git-scm.com/docs/gitignore) 
