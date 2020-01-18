# FrontEnd Interview Questions Part 1

Created By: Chris Trinh
Last Edited: Jan 17, 2020 3:22 PM

- What is Semantic Element in HTML5?
    - Non-semantic(div, span) - tells nothing about the content
    - Semantic(form, table, article) - defines content
- View port height & width in CSS3?
    - New set of unites designed for one pagers, full-width grids, typography. 4 Units, 2 for each axis.
    - vw : 1/100 viewporth width
    - vh: 1/100th viewport height;
    - vmin: 1/100th of the smallest side
    - vmax: 1/100th of the largest side
- What is CSS breakpoints?
    - Points where website content responds according to the device width. Shows possible lay out for the user
- CSS Best Practice about ID and Class?
    - Allows for separation for unique cases of html elements to be css'd differently from other elements of the same property.
- What is SASS/SCSS?
    - Sass(Syntactically awesome style sheets is a preprocessor scripting language that is intepreted or compiled into Cascading Style Sheets.
    - Sass is the scripting language and has more features such as nesting elements and using variables
- What is mixin in Sass/SCSS?
    - Abstraction of common patterns into a semantic and reusable chunk.
    - e.g taking the styles for a common button and creating a selector for it'
- What's new in ES6?
    - Brings javascript new syntax and allows for more readable and modern code. Less code to do more.
    - Arrow functions, classes, rest and spread operators, let + const, destructuring, and more
- What is Event Bubbling?
    - When an event happens on an element, runs handlers on it, then parents, then ancestors.
- What is prototype inheritance in JavaScript?
    - Objects ability to access methods and other properties from another object.
    - ES5 uses prototypes
- Abstract function in JavaScript?
    - One of the four central principles (encapsulation, inheritance, polymorphism)
    - Hides certain details and only shows essential features of the objects. Allows for understandability and maintainability of the code.
    - Reduce code duplication and allows for simplicity to do a function without doing too much.
- What is `this` keyword in Arrow function?
    - this is lexically bound : uses this from the code that contains the arrow function. We don't have to use bind and it'll go up a scope.
- What is `this` keyword in normal function?
    - this may be different each time this is called and have to bind to an outer function
- What is the difference between localStorage and sessionStorage?
    - Local storage saves to the browser, (up to 10Mb).
    - Session Storage is the same but the information will be deleted after closing your browser. (5MB)
    - Cookies store small amounts of data like 4KB and can be accessed through server/browser
- What is CORS?
    - Cross-Origin Resource Sharing is a mechanism that uses additional HTP headers to let a web app run at one origin and allow sit to have permission to get information from a different server origin.
    - Web app makes cross-origin http request when it request from a server different from its own origin.
- What is HTTP request?
    - Packet of information that one system sends to another.
    - Package of binary data sent by client to server.
    - Consists of Request Line and Headers (0 or more each request)
- How many HTTP methods we have?
    - Get - retrieve data
    - Post - create data to a server
    - Delete -  delete data
    - Patch - Apply modification or update data
- What is API and REST API?
    - API - set of functions and procedures that allow creation of applications to access data of a system
    - REST API (Representational State Transfer) - Uses existing API methods, to handle multiple types of call and return different data formats
- What do you need in an AJAX request?
    - Usually type of request, url, and data if its post or patch method
- Make an AJAX request?

        $(function() {
          function LoadPersons(data) {
            // do something with data
          }
          
          $.ajax({
            type: 'POST',
            url: url,
            data: JSON.stringify(parameters),
            contentType: 'application/json;',
            dataType: 'json',         
            success:function(result) { 
              // do something with persons (data)             
              // e.g.
              LoadPersons(data);         
            }     
          }); 
        });

- How does the browser work?
    - The web server locates and sends information to the web browser displaying the results.
    - Browsers contact server. Server sends pages built with HTML. Then browser interpret and displays on the computer.
- What is Pure Function in JavaScript?
    - Functions that accept input and returns a value without modifying data outside its scope (Side Effects)
    - Return output depends on the arguments given to the function.
- Event Handling in JavaScript?
    - JS interaction with html handled through events when user or browser manipulate the page.
    - Page load, calls an events. Others include clicking a button, pressing a key, closing a window, resizing a window.
- JavaScript execution context?
    - An environment in which javascript is executed. Variables, objects, and functions javascript code has access to.
    - [https://blog.bitsrc.io/understanding-execution-context-and-execution-stack-in-javascript-1c9ea8642dd0](https://blog.bitsrc.io/understanding-execution-context-and-execution-stack-in-javascript-1c9ea8642dd0)
- How to manage your state in React?
    - Redux is a huge way. But now you can use React Context API or even hooks to manage states inside functional components
    - Also a thing called Mobx and Apollo
- How Redux works?
    - Action Creators, reducers, middlewares, pure function, immutable.
    - Uses reducers to create an action and next state and applies the information to that state.
- What is Presentational Component and Functional Component?
    - Presentational is strictly UI and not much use of data.
    - A react component is considered 'pure' if it has the same output for same state and props