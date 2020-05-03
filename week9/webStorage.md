
# Web storage 


## What are local storage and session storage and what is the difference between the two?

The two mechanisms within Web Storage are as follows:

* SessionStorage:
 Available for the duration of the page session (as long as the browser/tab is open, including page reloads and restores)
Data is never transferred to the server.
Storage limit is larger than a cookie (at most 5MB).

* LocalStorage:
localStorage is a way to store data on the client’s computer. It allows the saving of key/value pairs in a web browser and it stores data with no expiration date. localStorage can only be accessed via JavaScript, and HTML5. 
Storage limit is larger than a cookie (at most 5MB).
<hr>

## Why would you use cookies vs local/session storage?

### Cookies

There are two types of cookies: persistent cookies and session cookies.
1. Session cookies do not contain an expiration date. Instead, they are stored only as long as the browser or tab is open. As soon as the browser is closed, they are permanently lost. This type of cookie might be used to store a banking user’s credentials while they are navigating within their bank’s website since their information would be forgotten as soon as the tab is closed.

2. Persistent cookies do have an expiration date. These cookies are stored on the user’s disk until the expiration date and then permanently deleted. They can be used for other activities such as recording a user’s habits while on a particular website in order to customize their experience every time they visit.

- Stores data that has to be sent back to the server with subsequent requests. Its expiration varies based on the type and the expiration duration can be set from either server-side or client-side (normally from server-side).
- Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
- Size must be less than 4KB.
- Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie



### LocalStorage


- Stores data with no expiration date, and gets cleared only through JavaScript, or clearing the Browser cache / Locally Stored Data
- Storage limit is the maximum amongst the three

### SessionStorage

- The sessionStorage object stores data only for a session, meaning that the data is stored until the browser (or tab) is closed.
- Data is never transferred to the server.
- Storage limit is larger than a cookie (at least 5MB).

![](https://i.imgur.com/dGawlkP.png)


<hr>

## Demo a simple usage of localStorage and sessionStorage


## If you want to know what are the limits of the Web Storage Support Test on your browser, [check this site](http://dev-test.nemikor.com/web-storage/support-test/)    





### References:
1. [Web Storage](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
2. [medium](https://medium.com/swlh/cookies-vs-localstorage-whats-the-difference-d99f0eb09b44)
3. [scotch](https://scotch.io/@PratyushB/local-storage-vs-session-storage-vs-cookie)
