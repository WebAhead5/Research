


<!-- ![](https://i.imgur.com/QFMpLDV.png) -->
# Templating and Serverside rendering
### What is server-side rendering?


<b>Server Side Rendering</b>, also called SSR, is the ability of a JavaScript application to render on the server (rather than in the browser), before it is served to the user. 

This is the inverse to <b>Client Side Rendering</b> (CSR), where the elements are served in parts (multiple get requests to the server), the application is then rendered for the user locally in the browser with JavaScript.

![](https://i.imgur.com/Wn4kUvI.png)

### What are the pros and cons of serverside rendering vs clientside

#### Server-side
Server-side pros:
- Search engines can crawl the site for better SEO.
- It enables pages to load faster.
- Great for static sites.
- It assists with loading the page when the user has a slow internet connection.
- It assists in loading the page when the user has an outdated device or browser.
- Can decrease the number of requests made to the server.


Server-side cons:
<!-- - Frequent server requests. -->
<!-- - An overall slow page rendering. -->
- Full page reloads.
<!-- - Non-rich site interactions. -->
- Complexity increases as the complexity of the application increases.
- Offsetting the rules of a logic-less template requires a lot of helper methods.


<i>Further examples for Apps:</i>
![](https://i.imgur.com/7EZfWTA.png)

#### Client-side

Client-side pros:
- Rich site interactions
- Fast website rendering after the initial load.
- Great for web applications. 
- Robust selection of JavaScript libraries.

Client-side cons:
- Low Search Engine Optimization if not implemented correctly.
- Initial load might require more time.
- In most cases, requires an external library.



### What problems do templating languages solve

- <b>Reduces Code Repetition:</b> You can use templates to reuse code when you have a lot of similar pages to display, eg product pages on a e-commerce site, or profile pages on a social media site.
- <b>Code Modularity:</b> The ability to mix and match html elements seamlessly, for example Headers, Nav bars, video elements by using partial templates.
- <b>Backend pre-rendering of HTML:</b> So that you dont have to manipulate the HTML on the client side using JS/DOM.



### What are some examples of functionality that templating languages provide 


- <b>Conditional logic</b>: 
    - Show different html elements based on given conditions.
  
- <b>Partial templating:</b> 
    - Can be used to edit code once, which will then edit it everywhere you used the template.
- <b>Looping:</b> 
    - Can be used to iterate over a list in order to repeat html within the template, reducing repeitive code.
- <b>Helpers:</b> 
    - Write functions in JS, which can be used within the template to help structure the html file.



## Further Reading
[SSR vs CSR: Free Code Camp article](https://www.freecodecamp.org/news/what-exactly-is-client-side-rendering-and-hows-it-different-from-server-side-rendering-bd5c786b340d/)
