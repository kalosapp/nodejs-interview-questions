# Node.js Interview Questions

| Sl.No|  Questions       |
|------|------------------|
| 01. |[What is Node.js and why is it important?](#q-what-is-nodejs-and-why-is-it-important)|
| 02. |[What are the benefits of Node.js?](#q-what-are-the-benefits-of-nodejs)|
| 03. |[How do you handle errors in Node.js?](#q-how-do-you-handle-errors-in-nodejs)|
| 04. |[How do you create and use custom modules in Node.js?](#q-how-do-you-create-and-use-custom-modules-in-nodejs)|
| 05. |[How do you handle routing in a Node.js application?](#q-how-do-you-handle-routing-in-a-nodejs-application)|
| 06. |[What are the best practices for security in a Node.js application?](#q-what-are-the-best-practices-for-security-in-a-nodejs-application)|
| 07. |[How do you optimize the performance of a Node.js application?](#q-how-do-you-optimize-the-performance-of-a-nodejs-application)|
| 08. |[Describe Node.js internal architecture?](#q-describe-nodejs-internal-architecture)|
| 09. |[How to catch unhandled exception in node process?](#q-how-to-catch-unhandled-exception-in-node-process)|
| 10. |[Difference between process and threads in Node.js](#q-difference-between-process-and-threads-in-nodejs)|
| 11. |[Design patterns that you have used in Node.js?](#q-design-patterns-that-you-have-used-in-nodejs)|
| 12. |[How to do authorization in Node.js?](#q-how-to-do-authorization-in-nodejs)|
| 13. |[How to do authentication in Node.js?](#q-how-to-do-authentication-in-nodejs)|
| 14. |[How we can block main thread in Node.js?](#q-how-we-can-block-main-thread-in-nodejs)|
| 15. |[What is event and eventEmitter in Node.js?](#q-what-is-event-and-eventemitter-in-nodejs)|

<br/>

## Q. ***What is Node.js and why is it important?***

* Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It is an open-source, cross-platform runtime environment that allows developers to run JavaScript code on the server-side. Node.js provides an event-driven, non-blocking I/O model that makes it lightweight and efficient, making it perfect for building fast and scalable network applications.

* Node.js is important because it allows developers to use JavaScript for both front-end and back-end development. This means that developers can use the same programming language and familiar concepts across the entire stack, making development more efficient and streamlined. Additionally, Node.js has a large and active community that has created a vast ecosystem of libraries and modules, making it easy to perform common tasks and add functionality to applications.

* Node.js is also well-suited for real-time applications, such as chat applications and games, because of its event-driven, non-blocking I/O model. It can handle a large number of concurrent connections, making it ideal for building high-performance web servers and other networking applications.

* Node.js is also widely used in microservices architecture, as it allows for building small, focused, and independent services that can be easily maintained, deployed, and scaled.

In summary, Node.js is an open-source, cross-platform JavaScript runtime environment that allows developers to run JavaScript code on the server-side. It is lightweight, efficient, and well-suited for building fast and scalable network applications, real-time applications, microservices and it's important because it allows developers to use the same language and concepts across the entire stack, and it has a vast ecosystem of libraries and modules.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***What are the benefits of Node.js?***

From a web server development perspective Node has a number of benefits:

  * Great performance! Node was designed to optimize throughput and scalability in web applications and is a good solution for many common web-development problems (e.g. real-time web applications).

  * Code is written in "plain old JavaScript", which means that less time is spent dealing with "context shift" between languages when you're writing both client-side and server-side code. 

  * JavaScript is a relatively new programming languages and benefits from improvements in language design when compared to other traditional web-server languages (e.g. Python, PHP,  etc.) Many other new and pouplar languages compile/convert into JavaScript so you can use TypeScript, CoffeeScript, ClojureScript, Scala, LiveScript, etc.

  * The node package manager (NPM) provides access to hundres of thousands of resuable packages. It also has best-in-class dependency resolution and can also be used to automate most of the build toolchain.

  * Node.js is portable. It is available on Microsoft Windows, macOS, Linux, Solaris, FreeBSD, OpenBSD, WebOS, and NonStop OS. Furthermore, it is well-supported by many web hosting providers, that often provide specific infrastrucutre and documentation for hosting 
    Node sites.

  * It has a very active third party ecosystem and developer community, with lots of people who are willing to help. 
    
<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How do you handle errors in Node.js?***

* Try-catch blocks: This is a standard JavaScript construct that allows you to catch and handle errors that occur within a try block. It is commonly used to handle synchronous errors.

* Error-first callbacks: This is a common pattern in Node.js for handling asynchronous errors. An error-first callback is a function that takes two arguments: an error object and a result object. If an error occurred, the error object will be an instance of the Error class or a subclass of it, otherwise it will be null.

* Promises: Node.js has built-in support for promises, which are a way to handle asynchronous code in a more elegant and composable way. You can use the .catch() method on a promise chain to handle errors.

* Global error handler: It's also a good practice to have a global error handler to handle unexpected errors that may occur in your application. You can use the process.on('uncaughtException') or process.on('unhandledRejection') events to set up a global error handler.

* Domains: Domains are a way to handle errors and to maintain a separate context for different parts of an application.

* Async-Await: The async-await pattern is a more recent addition to javascript, it allows handling asynchronous code in a more synchronous way.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How do you create and use custom modules in Node.js***

In Node.js, custom modules are created using the exports or module.exports objects. The exports object is a reference to the module.exports object, and it is used to make properties and methods available to other modules.

Here is an example of creating a custom module called myModule:

```js
// myModule.js

exports.greet = function(name) {
    console.log("Hello, " + name + "!");
}

exports.sum = function(a, b) {
    return a + b;
}
```
This module exports two functions: greet and sum.

You can use the require function to import the custom module in another file:

Copy code
const myModule = require('./myModule');

myModule.greet("John"); // Output: Hello, John!
console.log(myModule.sum(1,2)); // Output: 3
You can also use the module.exports object to create a single object or function that will be exported by the module. For example:

```js
// myModule.js

module.exports = {
    greet: function(name) {
        console.log("Hello, " + name + "!");
    },
    sum: function(a, b) {
        return a + b;
    }
};
```
This module exports a single object that has two properties: greet and sum.

When creating custom modules, it is also a good practice to use a consistent naming convention and to document the module with clear and detailed comments that explain what the module does and how to use it.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How do you handle routing in a Node.js application***

In a Node.js application, routing refers to the process of determining how to handle a specific request based on the URL and HTTP method of the request. There are several ways to handle routing in a Node.js application, including:

Using the built-in http module: The http module in Node.js provides a low-level way to handle routing. You can use the http.createServer() method to create an HTTP server and then use the server.on('request') event to handle incoming requests. Within the event handler, you can use the url and method properties of the request object to determine how to handle the request.

Using a framework: There are several popular web frameworks for Node.js such as Express, Koa, Hapi, Meteor. These frameworks provide a higher-level abstraction for handling routing, making it easier to define and handle routes.

Using a Router: Some frameworks like Express provide routing middleware, which can be used to define routes and handle incoming requests.

Using a Router library: There are several libraries that provide routing functionality such as fastify-routes, koa-router, hapi-router. These libraries can be used with any web framework and can be used to handle routing.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>


## Q. ***What are the best practices for security in a Node.js application?***
* Input validation: Validate all user inputs to prevent malicious data from being passed to your application. This includes validating user input for type, format, and length.

* Use a web application firewall (WAF): A WAF can help protect your application from common web attacks such as SQL injection, cross-site scripting (XSS), and cross-site request forgery (CSRF).

* Use HTTPS: Use HTTPS to encrypt all communication between the client and the server.

* Use a security middleware: Use security middleware such as Helmet, cors, and rate-limiting to protect your application from common web vulnerabilities.

* Use dependency management: Keep your dependencies updated and use a tool like npm-check-updates or Snyk to regularly check for vulnerabilities.

* Use environment variables: Use environment variables to store sensitive information such as passwords, keys, and tokens.

* Use session management: Use a session management library such as express-session to securely store user sessions.

* Use authentication and authorization: Use authentication and authorization to control access to resources and ensure that only authorized users can access sensitive data.

* Use encryption: Use encryption to protect sensitive data such as passwords, credit card numbers, and personal information.

* Use Logging: Use logging to track user activity, detect suspicious activity, and troubleshoot issues.

* Keep your Node.js version up-to-date: As with any software, vulnerabilities are discovered and fixed over time. Keeping your Node.js version up-to-date is important to ensure that you are protected from known vulnerabilities.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How do you optimize the performance of a Node.js application?***

* Profiling and monitoring: Use tools such as the built-in Node.js profiler, the Node.js Debugger, and other performance monitoring tools to identify bottlenecks and measure the performance of your application.

* Optimizing resource usage: Optimize the usage of memory, CPU, and other resources by removing unnecessary objects, reducing the number of function calls, and using caching.

* Optimizing database queries: Optimize the performance of your database queries by using indexes, reducing the number of queries, and using connection pooling.

* Optimizing network communication: Optimize the performance of network communication by using a load balancer, using a Content Delivery Network (CDN), and compressing data.

* Optimizing the code: Write efficient and optimized code by following best practices, using the latest features of the language, and using a linter to check the code quality.

* Caching: Caching is a powerful technique to improve the performance of your application. Node.js provides a built-in cache API, and there are also several caching libraries available.

* Scaling: When the traffic increase, you can scale your application horizontally by adding more servers to handle the load.

* Use a CDN: A Content Delivery Network (CDN) can help to distribute your content across multiple servers, reducing the load on your application.

* Use a Load balancer: Use a load balancer to distribute the traffic across multiple servers, improving the performance and availability of your application.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***Describe NodeJS internal architecture***

Node.js is built on top of several underlying technologies, which work together to provide its functionality. The internal architecture of Node.js can be broadly divided into three main components:

1. The V8 JavaScript engine: This is the JavaScript engine developed by Google that is used to execute JavaScript code in Node.js. It is built in C++ and is responsible for compiling and executing JavaScript code.

2. The libuv library: This is a C library that provides an event loop and other asynchronous I/O functionality to Node.js. It is responsible for managing the event loop and handling non-blocking I/O operations such as file system access, network communication, and timers.

3. The Node.js Core API: This is the set of built-in JavaScript modules that provide the core functionality of Node.js, such as the HTTP server, the file system, and the process management. These modules are built on top of the V8 engine and libuv library, and provide a high-level JavaScript API for interacting with the underlying system.

The architecture of Node.js is based on the event-driven, non-blocking I/O model. When a request comes to the server, the libuv library is responsible for handling it and creating an event. The event loop runs in a single thread, and it uses non-blocking I/O operations to handle multiple events simultaneously. The event loop checks the events in the queue and based on the type of event, it'll call the appropriate callback function.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How to catch unhandled exception in node process?***

In Node.js, you can use the process.on('uncaughtException') event to catch unhandled exceptions. This event is emitted when an exception is thrown and not caught by any try-catch block or promise rejection handler.

Here is an example of how to use the process.on('uncaughtException') event to catch unhandled exceptions:

```js
process.on('uncaughtException', (err) => {
    console.error(`Caught uncaughtException: ${err}`);
    // Perform any cleanup or logging here
    process.exit(1);
});
```
It's important to note that when an unhandled exception occurs, the process will exit by default. The above example shows how to prevent the process from exiting by calling process.exit() after handling the exception.

In addition to uncaughtException, you can also listen to unhandledRejection event, which will trigger when a promise is rejected and no rejection handler is attached to it.

```js
process.on('unhandledRejection', (reason, p) => {
    console.error(`Caught unhandledRejection: ${reason}`);
    // Perform any cleanup or logging here
});
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***Difference between process and threads in Node.js***

In Node.js, a process refers to an instance of the Node.js runtime environment. Each process has its own memory space and runs in its own context.

Threads, on the other hand, are lightweight units of execution that run within a process. They share the same memory space and can run in parallel.

Node.js uses a single thread for executing JavaScript code and a separate thread for performing I/O operations. This means that all JavaScript code runs on a single thread, but I/O operations such as file system access, network communication, and timers are handled asynchronously on separate threads, allowing the JavaScript thread to continue executing without blocking.

The event loop is the mechanism that allows Node.js to handle multiple I/O operations asynchronously using a single thread. When a non-blocking I/O operation is initiated, the JavaScript thread sends it to the system's kernel, and continues to execute the next instruction in the event loop. The kernel will signal the event loop when the I/O operation completes, and Node.js will execute the callback associated with that operation.

This design allows Node.js to handle a large number of concurrent connections with a relatively low number of threads, making it well-suited for high-concurrency, low-latency network applications.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***Design patterns that you have used in Node.js***

Here's few design pattern in Node.js:

1. **Module pattern**: This pattern is used to create self-contained and reusable modules in Node.js. The module pattern wraps the methods and variables in a closure, which creates a private scope, and then returns an object containing the methods that should be exposed.
```js
const privateVariable = 'private value';

function privateMethod() {
  console.log(privateVariable);
}

module.exports = {
  publicMethod: () => {
    privateMethod();
  },
};
```

2. **Factory pattern**: This pattern is used to create objects with similar characteristics, but with different implementations. In Node.js, it is often used to create different types of database connections or to implement different types of middleware.

```js
class SimpleMembership {
  constructor(name) {
    this.name = name;
    this.cost = 50;
  }
}

class StandardMembership {
  constructor(name) {
    this.name = name;
    this.cost = 150;
  }
}

class PremiumMembership {
  constructor(name) {
    this.name = name;
    this.cost = 500;
  }
}

class MemberFactory {
  static list = {
    simple: SimpleMembership,
    standard: StandardMembership,
    premium: PremiumMembership,
  }

  create(name, type = 'simple') {
    const Membership = MemberFactory.list[type] || MemberFactory.list.simple;
    const member = new Membership(name);
    member.type = type;
    member.define = function() {
      console.log(`${this.name} (${this.type}): ${this.cost}`);
    }
    return member;
  }
}

const factory = new MemberFactory();
const members = [
  factory.create('John', 'simple'),
  factory.create('Mike', 'premium'),
  factory.create('Mary', 'standard'),
];

members.forEach(m => {
  m.define();
});
```
3. **Singleton pattern**: This pattern is used to create a single instance of an object and to provide a global point of access to that instance. In Node.js, it is often used to create a single instance of a database connection or a shared resource.

```js
class Singleton {
  constructor() {
    if (Singleton.instance) {
      return Singleton.instance;
    }

    Singleton.instance = this;
    this.value = Math.random();
  }

  getValue() {
    return this.value;
  }
}

const singleton1 = new Singleton();
const singleton2 = new Singleton();
console.log(singleton1.getValue() === singleton2.getValue()); // true

```
4. **Observer pattern**: The observer pattern is a design pattern in JavaScript and Node.js that is used to allow objects to subscribe to and receive notifications from other objects. It is often used to implement event-driven architectures or to handle asynchronous callbacks.

Here is an example of the observer pattern in Node.js:

```js
class Subject {
  constructor() {
    this.observers = new Set();
  }

  subscribe(observer) {
    this.observers.add(observer);
  }

  unsubscribe(observer) {
    this.observers.delete(observer);
  }

  notify(data) {
    this.observers.forEach(observer => {
      observer.update(data);
    });
  }
}

class Observer {
  constructor(name) {
    this.name = name;
  }

  update(data) {
    console.log(`${this.name} received: ${data}`);
  }
}

const subject = new Subject();
const observer1 = new Observer('Observer 1');
const observer2 = new Observer('Observer 2');
const observer3 = new Observer('Observer 3');

subject.subscribe(observer1);
subject.subscribe(observer2);
subject.subscribe(observer3);

subject.notify('Hello World!');

// Output:
// Observer 1 received: Hello World!
// Observer 2 received: Hello World!
// Observer 3 received: Hello World!
```

In this example, the Subject class has a set of observers and methods to subscribe, unsubscribe and notify them. The Observer class has a method update that is called when the subject notifies its observers.

The Subject class keeps track of a list of observers and notifies them when an event occurs. The Observer class subscribes to the Subject class and provides an update method that is called when the subject notifies its observers.

This pattern allows objects to be decoupled and to communicate with each other in a loosely coupled way, making the system more flexible and easier to maintain. It can be used to implement an event-driven architecture, where the subject is an event emitter and the observers are event listeners.

5. **Decorator pattern**: The decorator pattern is a design pattern in JavaScript and Node.js that is used to add new functionality to an existing object, without modifying its structure. It is often used to add new behaviors or responsibilities to existing classes in a flexible and transparent way.

Here is an example of the decorator pattern in Node.js:

```js
class Component {
  operation() {
    return 'Component';
  }
}

class DecoratorA {
  constructor(component) {
    this.component = component;
  }

  operation() {
    return `Decorator A (${this.component.operation()})`;
  }
}

class DecoratorB {
  constructor(component) {
    this.component = component;
  }

  operation() {
    return `Decorator B (${this.component.operation()})`;
  }

  addedBehavior() {
    console.log('Decorator B added behavior');
  }
}

const component = new Component();
const decoratorA = new DecoratorA(component);
const decoratorB = new DecoratorB(decoratorA);

console.log(decoratorB.operation());
decoratorB.addedBehavior();
```
In this example, the Component class is the base class that defines the basic behavior. The DecoratorA and DecoratorB classes are decorators that add new functionality to the Component class, by wrapping it and calling its operation method. They can also have additional methods and properties.

The DecoratorA class has a operation() method that wraps the operation() method of the Component class and adds some text to it. The DecoratorB class has a similar operation() method, but also has an additional addedBehavior() method.

The example shows how to instantiate the decorators and how to use the operation() method and addedBehavior() method of the final decorated object. This pattern allows to extend an object's behavior in a transparent and flexible way and it's also useful to create an object with a certain behavior, but with added functionality.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How to do authorization in Node.js?***

There are several ways to handle authorization in a Node.js application, depending on the requirements of the application. Some of the common ways are:

1. ***Using Passport.js:*** Passport.js is a popular authentication middleware for Node.js that supports a wide variety of authentication strategies, including local authentication, OAuth, and OpenID Connect. Passport can also be used to handle authorization by adding custom middleware that checks the user's role or permissions before allowing access to certain routes or resources.

2. ***Using JSON Web Tokens (JWT):*** JWT is a standard for creating token-based authentication and authorization. JWT tokens are signed and encoded JSON objects that contain a set of claims, such as the user's ID, role, and permissions. These tokens can be passed in the headers of requests to authenticate and authorize users.

3. ***Using role-based access control (RBAC):*** This is a method of controlling access to resources based on the user's role. In this approach, the application defines a set of roles, such as admin, user, and guest, and assigns them to users. Each role has a set of permissions, such as read, write, and delete, that determine what resources the user can access.

4. ***Using resource-based access control (RBAC):*** This is similar to RBAC, but it's based on the resource that the user is trying to access rather than their role. In this approach, permissions are assigned to resources, and users are granted access to specific resources based on their permissions.

5. ***Using library:*** There are lot of libraries available to handle authorization and authentication in Node.js, such as express-jwt, jsonwebtoken, oauth2-server, and many more.

It's important to understand that the best way to handle authorization depends on the requirements of the application. For example, if the application needs to support multiple authentication strategies, using Passport.js may be the best option. If the application needs to handle authorization based on the user's role, using RBAC may be the best option.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>


## Q. ***How to do authentication in Node.js?***

Authentication is the process of verifying a user's identity, which is an important aspect of any web application. There are several ways to handle authentication in a Node.js application, including:

***1.Using Passport.js:*** Passport.js is a popular authentication middleware for Node.js that supports a wide variety of authentication strategies, including local authentication, OAuth, and OpenID Connect. Passport can be easily integrated into a Node.js application and is highly customizable.

***2.Using JSON Web Tokens (JWT):*** JWT is a standard for creating token-based authentication. JWT tokens are signed and encoded JSON objects that contain a set of claims, such as the user's ID, which are used to authenticate the user. These tokens can be passed in the headers of requests to authenticate users.

***3.Using Sessions:*** In this approach, the server creates a session for each user when they log in, and assigns a session ID that is passed to the client as a cookie. The client then sends this session ID in subsequent requests to authenticate the user.

***4.Using OAuth and OpenID Connect:*** OAuth and OpenID Connect are popular standards for authentication and authorization that allow users to authenticate using existing accounts, such as those from Google, Facebook, or other third-party providers.

***5.Using library:*** There are lot of libraries available to handle authentication in Node.js, such as passport, passport-local, passport-jwt, and many more.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***How we can block main thread in Node.js?***

Node.js uses a single-threaded event loop for executing JavaScript code, and it's designed to handle a large number of concurrent connections with a relatively low number of threads, making it well-suited for high-concurrency, low-latency network applications.

However, there are certain operations that can block the main thread and cause the event loop to stall, resulting in poor performance and unresponsive behavior. Some examples of operations that can block the main thread include:

***1.Synchronous I/O operations:*** Accessing the file system synchronously, such as using the fs.readFileSync() method, can block the main thread while the operation is being performed.

***2.Long-running computations:*** Performing a large number of calculations or complex operations in a single JavaScript function can block the main thread for an extended period of time.

***3.Blocking external libraries:*** Using a library that performs blocking I/O operations or computations can also block the main thread.

***4.Blocking database queries:*** Using a synchronous query or a library that perform blocking queries can block the main thread.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. ***What is event and eventEmitter in Node.js?***

In Node.js, an event is a signal that something has occurred or that something needs to occur. An event can be triggered by various things, such as user input, network activity, or the completion of a task.

An event emitter is an object that allows you to register listeners for specific events and to trigger those events. It is a way to implement the observer pattern, where an object (the event emitter) maintains a list of subscribers (the listeners) and notifies them when an event occurs.

The EventEmitter class is a built-in class in Node.js that provides an implementation of the event emitter pattern. You can use the EventEmitter class to create your own event emitters and to register event listeners.

Here is an example of how to use the EventEmitter class to create an event emitter and register event listeners:

```js
const EventEmitter = require('events');

class MyEmitter extends EventEmitter {}
const myEmitter = new MyEmitter();

// Register event listeners
myEmitter.on('event', () => {
  console.log('event occurred');
});

myEmitter.on('event', (arg1, arg2) => {
  console.log(`event occurred with args ${arg1} and ${arg2}`);
});

// Trigger the event
myEmitter.emit('event', 'arg1', 'arg2');
```

In this example, the MyEmitter class is a child class of EventEmitter and myEmitter is an instance of that class. The on method is used to register event listeners for the event event. The emit method is used to trigger the event and pass any arguments to the listeners. When the emit method is called, the registered listeners will be called in the order they were registered.

EventEmitters are widely used in nodejs, for example the http.Server class, the net.Socket class, the stream.Readable class, and the stream.Writable class all inherit from EventEmitter, so all the classes have the ability to emit events and can have event listeners listening for specific events.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>
