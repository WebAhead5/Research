
# <p style="text-align: center">**Unit vs integration testing** </p>

<!-- <p align="center">
  <img  src="https://i.imgur.com/5vOo3Md.png">
</p> -->
The testing tree ![](https://i.imgur.com/5vOo3Md.png)

# Unit Test  

### What is it ?

When splitting the code into smaller pieces (Mostly functions) and running a test in order to verify that every unit is providing the expected outcome. hence, unit tests should be performed as often as possible.

### How it should be Done ?

- ##### Test one thing at a time in Isolation:
  All classes should be tested in isolation and     should not depend on anything!
    
- ##### Test across boundaries:
  Testing the boundaries and the edge cases are places where the code might fail. 
- ##### Name the tests clearly.
- ##### Write test that reveal a bug, then fix it:
  If you find a bug, write a test that reveals it, then you can fix the bug by debugging the test until it passes the test. Which means you are "testing the test".

----



# What is an integration test? 

## Introduction:
Integration testing is uaually done after “Unit testing”. Once all the individual units are created and tested, we start combining those “Unit Tested” and start doing the integrated testing.

The individual modules are first tested in isolation. Once the modules are unit tested, they are integrated one by one, till all the modules are integrated, to check the combinational behavior, and validate whether the requirements are implemented correctly or not.

Hint integration testing does not happen at the end of the cycle, rather it is conducted simultaneously with the development. So in most of the times, all the modules are not actually available to test and here is what the challenge comes to test something which does not exist!

## Reason for integration testing:
1. when applications are developed, it is broken down into smaller modules and individual developers are assigned a single module. The logic implemented by one developer is quite different than another developer, so it becomes important to check whether the logic implemented by a developer is as per the expectations and rendering the correct value in accordance with the prescribed standards.
2. Many times the face or the structure of data changes when it travels from one module to another. Some values are appended or removed, which causes issues in the later modules.
3. Modules also interact with some third party tools or APIs which also need to be tested that the data accepted by that API / tool is correct and that the response generated is also as expected.
4. Many a time developer deploys the changes without unit testing it. Integration testing becomes important at that time.

## Advantages
1. This testing makes sure that the integrated modules/components work properly.
2. Integration testing can be started once the modules to be tested are available. It does not require the other module to be completed for testing to be done, as Stubs and Drivers can be used for the same.
3. It detects the errors related to the interface.

## Challenges
1. Integration testing means testing two or more integrated systems in order to ensure that the system works properly. Not only the integration links should be tested but an exhaustive testing considering the environment should be done to ensure that the integrated system works properly.
2. Managing Integration testing becomes complex because of few factors involved in it like the database, Platform, environment etc.
3. While integrating any new system with the legacy system, it requires a lot of changes and testing efforts. Same applies while integrating any two legacy systems.
4. Integrating two different systems developed by two different companies is a big challenge as for how one of the systems will impact the other system if any changes are done in any one of the systems is not sure.

```
# Example -
Lets assume that you work for an IT organization which has been asked 
to develop an online shopping website for Camp World, a company that 
sells camping gear.

After requirements gathering, analysis and design was complete, one 
developer was assigned to develop each of the modules below.

User registration and Authentication/Login
Product Catalogue
Shopping Cart
Billing
Payment gateway integration
Shipping and Package Tracking

After each module was assigned to a developer, the developers began 
coding the functionality on their individual machines. They deployed 
their respective modules on their own machines to see what worked 
and what didn’t, as they went about developing the module.

After they completed the development, the developers tested their 
individual functionalities as part of their unit testing and found 
some defects. They fixed these defects. At this point they felt 
their modules were complete.

The QA Manager suggested that integration testing should be 
performed to confirm that all the modules work together.

When they deployed all of their code in a common machine, they 
found that the application did not work as expected since the 
individual modules did not work well together. There were bugs 
like – after logging in, the user’s shopping cart did not show 
items they had added earlier, the bill amount did not include 
shipping cost etc.

In this way, Integration Testing helps us identify, fix issues 
and ensure that the application as a whole, works as expected.
```

## Approaches or Types
###     1. Big Bang Integration Testing
As per the below image all the modules from ‘Module 1’ to ‘Module 6’ are integrated simultaneously then the testing is carried out.

![](http://tryqa.com/wp-content/uploads/2012/01/What-is-big-bang-integration-testing1.jpg)

###     2. Top-down Integration Testing
Testing takes place from top to bottom, following the control flow or architectural structure (e.g. starting from the GUI or main menu). Components or systems are substituted by stubs.

![](http://tryqa.com/wp-content/uploads/2012/01/What-is-top-down-integration-testing.jpg)

###     3. Bottom up Integration Testing
Testing takes place from the bottom of the control flow upwards. Components or systems are substituted by drivers. Below is the image of ‘Bottom up approach’:

![](http://tryqa.com/wp-content/uploads/2012/01/what-is-bottom-up-integration-testing.jpg)

###     4. Incremental Integration Testing
###     5. Sandwich Integration Testing
###     6. Functional Incremental Testing

## References and more readings:
https://www.softwaretestinghelp.com/what-is-integration-testing/
http://tryqa.com/what-is-integration-testing/

----

# When would you use each kind of test?
![](https://i.imgur.com/2VOXaCt.jpg)

Use unit tests:
- After adding new unit 
- Changing code in exisit unit
- Bug fix in a unit


Use integration tests:

- After adding new moudle 
- Updating moudle version
- Change in any third party code




