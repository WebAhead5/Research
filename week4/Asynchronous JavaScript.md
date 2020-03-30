#  Asynchronous JavaScript








## What is the call stack? 
 
<b>Call Stack :</b> It’s a data structure which records the function calls, basically where in the program we are. If we call a function to execute , we push something on to the stack, and when we return from a function, we pop off the top of the stack.

![](https://i.imgur.com/31QPmch.gif)

 In shortly ,A call stack is a mechanism for an interpreter to keep track     of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function.


## What are Async functions? (HASHEM)

Asynchronous functions are functions in which they are operate in a separate order than the rest of the code via the <b> <font color="Navy"> event loop</b> </font>, returning an <b> <font color="LightSeaGreen"> implicit Promise </b> </font> as its result. But the syntax and structure of code  using async functions looks like standard synchronous functions.

```
// Normal Function
function add1(x,y){
  return x + y;
}
// Async Function
async function add2(x,y){
  return x + y;
}
```
<hr>

**<font size=5> Duty of the <b> <font color="Navy"> event loop  </b> </font></font>**


Event loop basically handles the execution of multiple lines in the program over time, each time invoking the JS Engine. This means that the JS Engine is on-demand execution.Thus, he needs surrounding environment that schedules the events (JS code executions).

![EventLoop](https://miro.medium.com/max/1400/1*FA9NGxNB6-v1oI2qGEtlRQ.png)



<hr>

**<font size=5> So what is <b> <font color="LightSeaGreen"> promise </b> </font>in Javascript ?</font>**


A <b> <font color="LightSeaGreen"> promise  </b> </font> is an object that wraps an asynchronous operation and notifies when it’s done. This sounds exactly like callbacks, but the important differences are in the usage of Promises. Instead of providing a callback, a promise has its own methods which you call to tell the promise what will happen when it is successful or when it fails. The methods a promise provides are <b> <font color="blue"> “then(…)”</b> </font> for when a successful result is available and <b> <font color="PaleVioletRed"> “catch(…)”  </b> </font> for when something went wrong.


In a similar way, async functions can contain an <b> <font color="Maroon"> “await(…)”  </b> </font> expression that pauses the execution of the async function to wait for the passed Promise's resolution, then resumes the async function's execution and evaluates as the resolved value.

```

function sayHello() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('Hello ..');
    }, 2000);
  });
}

async function msg() {
  const msg = await sayHello();
  console.log('Message:', msg);
}

msg()

```

```
async function logFetch(url) {
  try {
    const response = await fetch(url);
    console.log(await response.text());
  }
  catch (err) {
    console.log('fetch failed', err);
  }
}
```








## Blocking code (JAKE)

<b>Blocking code</b> is any code that prevents the execution of further code becuase it is being excuted <b><font color="red"> synchronously</font></b> rather than <b><font color="green">asynchronously.</font> </b>

A good <b>example</b> of what may constitute blocking code is an operation that accesses an external api or database (that may take a long time to execute and rely on an external source); doing this in a single thread will <b>force all the other code to wait</b> for that execution to finish.

Blocking code can quickly slow down our application, so we need to use things like <b>callbacks, setTimeout()</b> or <b>promises</b>  to ensure things are executed in the correct order, but without causing to many delays for the end user.
    
    
    //Blocking
    
    const data = readFileSync('/file.md')   // blocks here until file is read
    
    console.log(data)                       // then runs log once data loaded

    nextFunction()                          // will only continue with other 
                                               code after data is logged
---

    // Non-blocking
    
    readFile('/file.md', (data) => {       //runs function
       console.log(data)}                  //log contained within data call

    nextFunction()                         //can now run asynchronously before 
                                             data loaded



## What is a callback function? Give an example of a callback function and explain what happens when it is executed (MEHIAR)

**Simply put:** A callback is a function that is to be executed after another function has finished executing ,hence the name ‘call back’.
 
**More complexly put:** In JavaScript, functions are objects. Because of this, functions can take functions as arguments, and can be returned by other functions. Functions that do this are called **higher-order** functions. Any function that is passed as an argument is called a **callback function**.

**example:**

```
T.get('search/tweets', params, function(err, data, response) {
  if(!err){
    // This is where the magic will happen
  } else {
    console.log(err);
  }
});
```
* T.get simply means we are making a GET request to Twitter.
* There are three parameters in this request: ‘search/tweets’, which is the route of our request, params which are our search parameters, and then an anonymous function which is our callback.

A callback is important here because we need to wait for a response from the server before we can move forward in our code. We don’t know if our API request is going to be successful or not so after sending our parameters to search via a GET request, we wait. Once Twitter responds, our callback function is invoked. Twitter will either send an err (error) object or a response object back to us. In our callback function we can use an if() statement to determine if our request was successful or not, and then act upon the new data accordingly.