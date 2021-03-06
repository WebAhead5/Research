# Attacks - Research Week 9

### Brief:

What are the following types of attack?
* Man In The Middle (MITM)
* Cross Site Scripting (XSS)
* Cross Site Request Forgery (CSRF)
* How can you defend against each of them?

<hr>

### Man in the Middle (MITM) 

MITM attack is when a hacker positions himself in a conversation between a user and an application—either to eavesdrop or to impersonate one of the parties, making it appear as if a normal exchange of information is underway.

The goal of an attack is to steal personal information, such as login credentials, account details and credit card numbers. Targets are typically the users of financial applications.


![](https://www.imperva.com/learn/wp-content/uploads/sites/13/2017/09/man-in-the-middle-mitm-attack.png)



### MITM attack progression 

![](https://media2.giphy.com/media/nujsQOINyCSqc/giphy.gif?cid=ecf05e4712a84bf31c1a2bd38f76aadbb7e0891ffa622145&rid=giphy.gif)


**1) Interception**

Occurred when the attacker intercepts user traffic through the attacker’s network before it reaches its intended destination.

The most common (and simplest) way of doing this is a passive attack in which an attacker makes free, malicious WiFi hotspots available to the public.

**Attackers will use one of the following methods to intercept user's data :**

* ***IP spoofing*** : Attacker will disguise himself as an application by altering packet headers in an IP address. As a result, users attempting to access a URL connected to the application are sent to the attacker’s website

* ***Address Resolution Protocol (ARP) spoofing*** : Attacker will link his MAC address with the IP address of a legitimate user on a local area network using fake ARP messages. As a result, data sent by the user to the host IP address is instead transmitted to the attacker.

* ***DNS spoofing*** : Attacker will infiltrate into a DNS server and altering a website’s address record. As a result, users attempting to access the site are sent by the altered DNS record to the attacker’s site.


**2) Decryption**

After interception, any two-way SSL traffic needs to be decrypted without alerting the user or application. A number of methods can be used to achieve this:

* ***HTTPS spoofing*** : Attacker will send a fake certificate to the victim’s browser once the initial connection request to a secure site is made. which the browser verifies according to an existing list of trusted sites.The attacker is then able to access any data entered by the victim before it’s passed to the application.

* ***SSL BEAST*** :Victim’s computer will be infected with malicious JavaScript that intercepts encrypted cookies sent by a web application. Then the app’s cipher block chaining (CBC) is compromised so as to decrypt its cookies and authentication tokens.

* ***SSL Hijacking*** : Attacker will pass forged authentication keys to both the user and application during a TCP handshake. This sets up what appears to be a secure connection when, in fact, the man in the middle controls the entire session.


* ***SSL Stripping*** : Attacker will downgrade the HTTPS connection to HTTP by intercepting the TLS authentication sent from the application to the user. The attacker sends an unencrypted version of the application’s site to the user while maintaining the secured session with the application. Meanwhile, the user’s entire session is visible to the attacker.


#### How can we defend against Man in the Middle Attacks?

- Avoiding WiFi connections that aren’t password protected.

- Paying attention to browser notifications reporting a website as being unsecured.

- Immediately logging out of a secure application when it’s not in use.


- Not using public networks (e.g., coffee shops, hotels) when conducting sensitive transactions.


<hr>

### Cross Site Scripting (XSS) (Amir)

Cross-site Scripting (XSS):is a client-side code injection attack allowing the injection of malicious code into website.
it is very common website  attacks, with almost every website requiring the user to have javascript turn on.
Rather than being an attack on the website itself, it uses the website as means to attack the users of that website,
when you can get your XSS permanently on a website all those who visit that page will have the javascript executed by their browser.
 By doing this, attackers may have access to personal data, cookies, webcams, and even more.

XSS differs from other web attack vectors (e.g., SQL injections), in that it does not directly target the application itself. Instead, the users of the web application are the ones at risk.
![](https://i.imgur.com/D4pRmkH.png)


**What are the types of XSS attacks?**
1)Reflected XSS, where the malicious script comes from the current HTTP request. 
2)Stored XSS, where the malicious script comes from the website's database.(when an application receives data from an untrusted source and includes that data within its later HTTP responses in an unsafe way).
3)DOM-based XSS, where the vulnerability exists in client-side code rather than server-side code. (example)

Here is how a DOM-based XSS attack can be performed for this web application:

The attacker embeds a malicious script in the URL: http://www.example.com/userdashboard.html#context=<script>SomeFunction(somevariable)</script>.
The victim’s browser receives this URL, sends an HTTP request to http://www.example.com, and receives the static HTML page.
The browser starts building the DOM of the page and populates the document.URL property with the URL from step 1.
The browser parses the HTML page, reaches the script, and runs it, extracting the malicious content from the document.URL property.
The browser updates the raw HTML body of the page to contain: Main Dashboard for <script>SomeFunction(somevariable)</script>.
The browser finds the JavaScript code in the HTML body and executes it.



**How to Prevent XSS** :
1) Input validation : is especially helpful and good at preventing XSS in forms, as it prevents a user from adding special characters into the fields, instead refusing the request.
2) A web application firewall (WAF): is the most commonly used solution for protection from XSS and web application attacks,WAFs employ different methods to counter attack vectors. In the case of XSS, most will rely on signature based filtering to identify and block malicious requests.
3)  Set the HttpOnly flag:if httponly is set on its token then an XSS attack shouldn't be able to retrieve a session token. Modulo past bugs in browsers and plugins, and server misconfiguration (eg responding to HTTP TRACE).
4)  Scan regularly (with Acunetix)// use different tools like acunetix to check if the app can get xss attacks .



---

### Cross Site Request Forgery (CSRF)

Cross Site Request Forgery is a form of attack that tricks a user into sending a request to a website that the user is logged in to.

For example, if I am logged in on Facebook, only I can perform particular actions with my login credentials (think access tokens and cookies), such as changing my password. But what if I clicked a link that sent a malicious GET request to Facebook's server? Or to a hacker's webpage that manufactured a POST request from my browser to Facebook?

This could be done quite easily. For example, if I was tricked into clicking [a link](https://www.youtube.com/watch?v=dQw4w9WgXcQ) that took me to a website created by a hacker. In theory, all the hacker would need to do is create a form in HTML that sent a POST request to Facebook's '/changepassword' URL and include a generic new password. The form could be submitted automatically with one line of javascript and I could be redirected to another page without realising what had happened.

``` html
<body onload="document.forms[0].submit()">
```

GET requests are even simpler. It can be as simple as an unaware user clicking a link with whichever necessary url request parameters. So for example, an image can be created (showing something that tricks a user into clicking on it), which contains a link to transfer funds:

``` html
<img src="http://bank.com/transfer.do?acct=MARIA&amount=100000" width="0" height="0" border="0">
```
<br>
<details><summary>Cross Site Request Forgery is also known as:</summary>

* CSRF, 
* XSRF, 
* “Sea Surf”, 
* Session Riding, 
* Cross-Site Reference Forgery, and 
* Hostile Linking. 
* Microsoft refers to this type of attack as a One-Click attack in their threat modeling process and many places in their online documentation.)

</details>

##### CORS

Fortunately, Cross-Origin Resource Sharing (CORS) prevents both of the above scenarios. But this is only supported by modern browsers. It also doesn't prevent a successful attack if a request is sent from the same website as the request is being sent to.

Also, be careful not to include this in your code:

``` javascript 
Access-Control-Allow-Origin: *
```
As this will allow permissions from any website and negate any security checks from CORS.

#### How can you defend against Cross Site Request Forgery (CSRF)?

The solution to CSRF attacks is to generate CSRF tokens that can be sent with any potentially sensitive request.

With Express, we can use [csurf](https://github.com/expressjs/csurf). csurf provides a middleware that adds a ```req.csrfToken()``` function, which adds a token to any requests that affect state.

``` cli
$ npm install csurf
```
``` javascript
var csurf = require('csurf')
```

An example provided in the README for csurf:

``` javascript
var cookieParser = require('cookie-parser')
var csrf = require('csurf')
var bodyParser = require('body-parser')
var express = require('express')

// create express app
var app = express()

// create api router
var api = createApiRouter()

// mount api before csrf is appended to the app stack
app.use('/api', api)

// now add csrf and other middlewares, after the "/api" was mounted
app.use(bodyParser.urlencoded({ extended: false }))
app.use(cookieParser())
app.use(csrf({ cookie: true }))

app.get('/form', function (req, res) {
  // pass the csrfToken to the view
  res.render('send', { csrfToken: req.csrfToken() })
})

app.post('/process', function (req, res) {
  res.send('csrf was required to get here')
})

function createApiRouter () {
  var router = new express.Router()

  router.post('/getProfile', function (req, res) {
    res.send('no csrf to get here')
  })

  return router
}
```

A good guide as to ways to mitigate CSRF attacks can be found [here](https://github.com/pillarjs/understanding-csrf)

#### Userful Links
* [Webpage explanation of CSRF](https://owasp.org/www-community/attacks/csrf)
* [9 minute introductory Youtube video explaining problem and solution to CSRF](https://www.youtube.com/watch?v=vRBihr41JTo)
* [Acedemind 14 minute video on Youtube, explaining how to use csurf with Youtube](https://www.youtube.com/watch?v=waAqEjjssxU)
* [csurf](https://github.com/expressjs/csurf)
