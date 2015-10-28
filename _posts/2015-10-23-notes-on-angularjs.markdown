---
title:  "Notes on AngularJS"
date:   2015-10-23 10:53:00
categories: Notes AngularJS
summary: A few point to notes about angularjs include concept and everything else.
cover-image: minion-lenses-attitude-uniform_1024.jpg
---

- The methods defined by the Module object fall into three broad categories: those that define components for an AngularJS application, those that make it easier to create those building blocks, and those that help manage the AngularJS life cycle. 
- The function passed to the `module.controller` method is used to declare the controller’s dependencies, which are the AngularJS components that the controller requires. AngularJS provides some built-in services and features that are specified using argument names that start with the `$` symbol. 
- All of the Module methods that create AngularJS building blocks accept functions as arguments. These are often _factory functions_, so called because they are responsible for creating the object that AngularJS will employ to perform the work itself. Often, _factory functions_ will return a _worker function_, which is to say that the object that AngularJS will use to perform some work is a function, too. 
- The filter method is used to define a filter, and the arguments are the name of the new filter and a factory function that will create the filter when invoked. Filters are themselves functions, which receive a data value and format it so it can be displayed.
- _Services_ are singleton objects that provide any functionality that you want to use throughout an application.
- _Singleton_ means that only one instance of the object will be created by AngularJS and shared between the parts of the application that need the service.
- The service method takes two arguments: the name of the service and a factory function that is called to create the service object.
- The `module.config` and `module.run` methods register functions that are invoked at key moments in the life cycle of an AngularJS app. A function passed to the config method is invoked when the current module has been loaded, and a function passed to the run method is invoked when all modules have been loaded.
- _Directives_ are the signature feature of AngularJS, setting the overall style of AngularJS development and the shape of an AngularJS application.
- The AngularJS approach is different: You create AngularJS web apps by embracing and enhancing HTML and treating it not as a problem but a foundation on which to build application features. 
- Directives expose core AngularJS functionality such as event handling, form validation, and templates. You use custom directives to apply your application features to views.
- The basic format of the value for the `ng-repeat` directive attribute is `<variable>` in `<source>`, where source is an object or array defined by the controller `$scope`.
- The `$index` variable, which is provided by the `ng-repeat` directive, is to display the position of each item in the array.
- The `ng-repeat` directive repeats a single top-level element and its contents for each object or property that it processes.
- Use `ng-switch` when you need to alternate between smaller, simpler blocks of content and that there is a good chance the user will be shown most or all of those blocks in the normal execution of the web app. This is because you have to deliver all the content that the `ng-switch` directive needs as part of the HTML document, and that’s a waste of bandwidth and loading time for content that is unlikely to be used.
- The `ng-include` attribute is better suited for more complex content or content that you need to use repeatedly throughout an application. Partial views can help reduce the amount of duplication in a project when you need to include the same content in different places, but you must bear in mind that partial views are not requested until the first time they are required, and this can cause delays while the browser makes the Ajax request and receives the response from the server.
- HTML elements define events, which provide asynchronous notifications of user interactions. AngularJS defines a set of directives that specify custom behaviors when different types of event are triggered.
- AngularJS takes a relaxed view of the state of the data model. There are no errors when you retrieve a nonexistent object or property, and when you assign a value to an object or property that doesn’t exist, AngularJS will simply create it for you—producing what is known as an _implicitly defined value or object_.
- When the type attribute is email, url, or number, AngularJS sets the `ng-pattern` automatically to check the formatting. You should not set the `ng-pattern` attribute on these types of input element.
- Basic of the _ng-options_ expression, and it is in the format `<label> for <variable> in <array>`.
- _Controllers_ act as the link between the domain model and the view; they provide data and services to the view and define the business logic required to translate user actions into changes in the model.
- Controllers are the link between the model and views. They use scopes to expose data from the model to views and the logic required to make changes to the model based on user interactions with the view.
- Controllers are created through the controller method provided by the AngularJS Module object. The arguments to the controller method are the name for the new controller and a function that will create the controller. The function is properly known as the _constructor_, but I will refer to it as the _factory function_ because many of the method calls required to create AngularJS components are expressed as one function (the factory) that is used to create another function (the _worker functions_).
- The _factory function_ can use the _dependency injection_ feature to declare dependencies on AngularJS services. Almost every controller will request the `$scope` service, which is used to provide the view with its scope, defining the data and logic that can be used in the view.
- `$scope` isn’t a service but is an object provided by a service called `$rootScope`.
- The most important aspect of scopes is that changes ripple through, automatically updating all of the dependent data values even when they are produced through a behavior. 
- Scopes are really organized in a hierarchy, starting with the root scope. Each controller is given a new scope that is a child of the root scope.
- The root scope is available as a service, so I declare a dependency on it on my controller using the name `$rootScope`.
- All scopes, including the `$rootScope` service, define a number of methods that are used to send and receive events.
- The scope methods for sending and receiving events
    1. `$broadcast(name, args)`
    Sends an event from the current scope down to all of the child scopes. The arguments are the name of the event and an object used to provide supplementary data with the event.
    2. `$emit(name, args)`
    Sends an event from the current scope up to the root scope.
    3. `$on(name, handler)`
    Registers a handler function that is invoked when the specified event is received by the scope.

- The `$broadcast` and `$emit` events are directional and send an event up through the scope hierarchy until it reaches the root scope or down through the hierarchy to each of the child scopes. 
- I defined the property on the `$scope` object using the _array-style notation_. The name of the `$scope` property is set to the value of the `args.type` property from the method argument. Placing `args.type` between the `[` and `]` characters causes the `args.type` property to be evaluated, and its value is used as the name of the scope property.
- The `ng-controller` directive can nested in HTML elements to create an effect known as _controller inheritance_. This is a feature that aims to reduce code duplication by letting you define common functionality in a _parent controller_ and use it in one or more _child controllers_.
- Child controllers can _override_ the _data_ and _behaviors_ of their _parents_, which means that data values and behaviors can be replaced with local versions that have the same name. 
- If you want a value that is initially shared but will be copied when modified, then define your data properties directly on the scope. To ensure that there is only one value, then define your data properties via an object.
- If scopes seem unnecessarily complex and your application doesn’t benefit from _inheritance_ or need to _communicate between controllers_, then you can use _scope-less controllers_. These are controllers that provide _data and _behaviors to views without using scopes at all_. Instead, _the view is provided with a special variable that represents the controller_.
- The format of this expression is `<controller to apply> as <variable name>`, and this example applies the simpleCtrl controller to the div element and creates a variable called ctrl. I then use the ctrl variable to access the data and behaviors in the view, like this: `<input class="form-control" ng-model="ctrl.dataValue">`
- _Filters_ transform the data before it is processed by a directive and displayed in a view without modifying the original data in the scope, allowing the same data to be displayed in different ways in different parts of the application. 
- Filters let you define commonly used data transformations so that they can be applied throughout an application, without being tied to a specific controller or type of data. Filters transform the data as it passes from the scope to the directive but don’t change the source data, allowing you to flexibly format or transform data for display in views.
- Filters contain transformation logic that can be applied to any data in the application for presentation in a view.
- Filters are used to format data before it is processed by a directive and displayed in a view.
- AngularJS comes with _two kinds of built-in filters_: those that _operate on single values_ and those that _operate on collections_. 
- One of the most useful things you can do with filters is chain them together so that multiple filters operate in sequence on the same data.
- Filters are chained together using the bar `(|)` character and are evaluated in the order in which they are written.
- You don’t have to worry about going out of bounds. The `limitTo` filter will return all of the objects in the array if you specify a number that is greater than the size of the array.
- Three different (custom) filters: one that formats a single data value, one that processes an array of objects, and one that builds on functionality provided by other filters.
- Filters are created by the `module.filter` method, which takes two arguments: the name of the filter that will be created and a factory function that creates the worker function that will undertake the actual work. 
- You can create a custom directive whenever the built-in directives don’t meet your needs, when you want to express complex functionality in code rather than in HTML, or when you want to create a self-contained unit of functionality that you can use in multiple AngularJS applications. 
- Directives are intended to be reusable within and across applications, so you avoid creating hardwired dependencies, including references to data created by specific controllers.
- The link function is invoked when AngularJS sets up each instance of the directive and receives three arguments: the scope for the view in which the directive has been applied, the HTML element that the directive has been applied to, and the attributes of that HTML element. The convention is to define the link function with arguments called _scope_, _element_, and _attrs_. 
- The _scope_, _element_, and _attrs_ arguments are regular JavaScript arguments and are not provided via _dependency injection_. This means the order in which the objects are passed to the link function is fixed.
- Unlike AngularJS controllers, directives don’t declare a dependency on the `$scope` service; instead, they are passed the scope created by the controller that supports the view in which the directive is applied. This is important because it allows a single directive to be applied multiple times in an application, where each application may be operating on a different scope in the hierarchy 
- _A library that provides support for method chaining_ is said to provide a _fluent API_, and jQuery, from which jqLite is derived, is one of the most widely used fluent APIs.
- If you prefix your property name with `data-`, then AngularJS will remove the prefix when it builds the set of attributes passed to the link function. This means, for example, that an attribute of `data-list-property` and `list-property` will both be presented as `listProperty` when the name is normalized and passed to the _link function_.
- JavaScript supports a feature called _closures_, which _allows a function to refer to variables outside of its scope_. This is a great feature, and it makes writing JavaScript a more pleasant experience. Without closures, you would have to make sure to define arguments for every object and value that your function needed to access.
- _Immediately invoked function expression (IIFE)_ is a _function that is evaluated immediately (and, as a consequence, is often called a self-executing function)_. Here is the basic structure of an IIFE:

{% highlight JavaScript %}
(function() {
    // ...statements that will be executed go here...
}());
{% endhighlight %}

- One-way bindings on isolated scopes are always evaluated to string values. You must use a two-way binding if you want to access an array, even if you don’t intend to modify it.
- The term _transclusion_ means to _insert one part of a document into another by reference_. In the context of directives, it is useful when you are creating a directive that is a wrapper around arbitrary content. 
- Two specific steps are required to apply _transclusion_. The first is to set the `transclude` definition property to `true` when creating the directive, the second step is to apply the `ng-transclude` directive in the template at the point where you want the wrapped elements inserted.
- Directives that are especially complex or deal with a lot of data can benefit by using a _compile function_ to manipulate the DOM and by leaving the _link function_ to perform other tasks. 
- Aside from performance, there is one advantage to using compile functions, and that is the ability to use _transclusion_ to repeatedly generate contents, much as `ng-repeat` does. 
- The `require` definition object property is used to declare a dependency on a controller.
- The `$render` method is called by the `ng-model` directive when the value has been modified outside the directive and the display needs to be updated.
- The `scope.$apply` method is used to push updates into the data model.
- The NgModel controller provides a simple mechanism for formatting values in the data model so that they can be displayed by a directive. The application of these formatters, which are expressed as functions, transforms the `$modelValue` property into the `$viewValue`.
- The `$formatters` property is an array of functions that are applied in order. The result from the previous formatter is passed as the argument, and the function returns its formatted result.
- _Services_ are used to encapsulate functionality that you want to reuse in an application but that don’t fit neatly into the _Model-View-Controller_ pattern
- _Services_ are commonly used to implement _cross-cutting concerns_, which is a catchall term for any functionality that is affected by more than one component or affects more than one component. In short, if you need to create functionality that doesn’t go elsewhere, then you create a service.
- Modules have two roles in AngularJS. The first is they define the application functionality that is applied to the HTML elements using the `ng-app` directive. The second use of a module is to define functionality, such as _services_, _directives_, and _filters_, in a way that makes it easy to reuse it in different applications.
- Services allow you to package up reusable functionality so that it can be used across the application. Modules allow you to package up reusable functionality so that it can be used across multiple applications.
- Create a service when functionality doesn’t fit into one of the other MVC building blocks and is a cross-cutting concern. Create a module to package functionality so that it can be used in multiple applications.
- Calling the module method with a single argument tells AngularJS that you want to obtain the `Module` object that represents a previously defined module.
- The `constant` and `value` methods also create services—just services that are limited in what they can be used for.
- The AngularJS Module defines three methods for defining services: _factory_, _service_, and _provider_. The result of using these methods is the same—a service object that provides functionality that can be used throughout the AngularJS application—but the way that the service object is created and managed by each method is slightly different
- The simplest way to create a service is to use the `module.factory` method, passing as arguments the name of the service and a factory function that returns the service object.
- Be careful not to reuse the name of a service. If you do, your service will replace the existing one.
- The `$interval` and `$timeout` services provide access to the `window.setInterval` and `window.setTimeout` functions, with some enhancements that make it easier to work with AngularJS.
- Calling the `html5Mode` method with `true` as the argument enables the use of the HTML5 features, which has the effect of changing the parts of the URL that the methods of the `$location` service operate on. 
- Only `constant` values and `providers` can be injected into `config` functions.
- The `$anchorScroll` service scrolls the browser window to display the element whose id corresponds to the value returned by the `$location.hash` method. 
- The `$exceptionHandler` service deals only with uncaught exceptions. You can catch an exception using a JavaScript `try`...`catch` block, and it will not be handled by the service.
- The `$interpolate` service and its provider, `$interpolateProvider`, are used to configure the way that AngularJS performs interpolation, which is the process of inserting expressions into strings. 
- The `$compile` service processes an HTML fragment that contains bindings and expressions to create a function that can then be used to generate content from a scope. 
- The `$http` service is used to make and process Ajax requests, which are standard HTTP requests that are performed asynchronously.
- AngularJS uses a JavaScript pattern called _promises_ to represent the result from an asynchronous operation, such as an Ajax request. A _promise is an object that defines methods that you can use to register functions that will be invoked when the operation is complete_. 
- Promises are a way of registering interest in something that will happen in the future, such as the response sent from a server for an Ajax request.
- Promises are not unique to AngularJS, and they can be found in many different libraries, including jQuery, but there are variations between implementations to accommodate differences in design philosophy or the preferences of the library developers.
- There are two objects required for a promise: a promise object, which is used to receive notifications about the future outcome, and a deferred object, which is used to send the notifications.
- For most purposes, the easiest way to think of promises is to regard them as a specialized kind of event; the deferred object is used to send events via the promise objects about the outcome of some task or activity.
- _Representational State Transfer (REST)_ is _a style of API that operates over HTTP requests_.
- The requested URL identifies the data to be operated on, and the HTTP method identifies the operation that is to be performed.
- The `$animate` service allows you to provide transition effects when elements are added, removed, or moved in the DOM. The `$animate` service doesn’t define any animations itself but relies on the CSS3 animation and transition features. 
- The swipe gestures are useful whenever you want to improve support for touchscreen devices. The `ngTouch` swipe events can be used to detect left-to-right and right-to-left swipe gestures. 
- The method that is not exposed via the Module type is _decorator_, which is used to intercept requests for a service in order to provide different or additional functionality.


---
> The research included neutron resonance spectroscopy, the angular distribution of pion elastic and inelastic scattering on nuclei with optical model fitting.
> <small>- [James Rainwater](http://www.brainyquote.com/quotes/quotes/j/jamesrainw231670.html)</small>