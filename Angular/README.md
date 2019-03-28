# Angular Interview Questions

What is Angular?
```
AngularJS is a JavaScript framework. 
Angular is a front-end or client-side Framework
It can be added to an HTML page with a <script> tag.
Angular (2/4/5) is not a programming language like Javascript or Typescript.
AngularJS extends HTML attributes with Directives, and binds data to HTML with Expressions.
The ng-app directive defines an AngularJS application.
The ng-model directive binds the value of HTML controls (input, select, textarea) to application data.
The ng-bind directive binds application data to the HTML view.
The ng-controller directive defines the controller.
```

Building Blocks of Angular
```
Modules
Components
Templates
Metadata
Data binding
Directives
Services
Dependency injection
```

What’s new in Angular 5?
```
Angular 5 supports Typescript version 2.4
Angular 5 supports RxJS 5.5 which has new features like Pipeable Operators
A build tool to make the js bundles (files) lighter
Ahead of Time (AOT) is updated to be on by default
Events like ActivationStart and ActivationEnd are introduced in Router
```

Name the building blocks of Angular.
```
• Modules
• Component
• Template
• Directives
• Data Binding
• Services
• Dependency Injection
• Routing
```

Which of the Angular life cycle component execution happens when a data-bound input value updates?
```
ngOnChanges is the life cycle hook that gets executed whenever a change happens to the data that was bound to an input. 
```

Differentiate between Components and Directives in Angular 5.
```
Components break up the application into smaller parts; 
whereas, Directives add behavior to an existing DOM element. 
```

What does a router.navigate do?
```
When we want to route to a component we use router.navigate.  
Syntax: this.router.navigate([‘/component_name’]); 
```

What are Services in Angular and what command is used to create a service?
```
Services help us in not repeating the code. With the creation of services, 
we can use the same code from different components. Here is the command to create 
a service in angular, ng g service User (a UserService is created when this command is used). 
```

What is Dependency Injection in Angular 4?
```
When a component is dependent on another component the dependency 
is injected/provided during runtime. 
```

What is Routing in Angular 5?
```
Routing helps a user in navigating to different pages using links. 
```

How to handle Events in Angular 5?
```
Any activity (button click, mouse click, mouse hover, mouse move, etc) of a user on a 
frontend/web screen is termed as an event. Such events are passed from the view 
(.HTML) page to a typescript component (.ts). 
```

In how many ways the Data Binding can be done?
```
Data Binding happens between the HTML (template) and typescript (component). 
Data binding can be done in 3 ways:
(i) Property Binding (ii) Event Binding (iii) Two-Way Data Binding. 
```

Differentiate between ng-Class and ng-Style.
```
In ng-Class, loading of CSS class is possible; 
whereas, in ng-Style we can set the CSS style. 
```

### What is the difference between AngularJS and Angular?
    Angular is a completely revived component-based framework in which an application is a tree of individual components.

    Some of the major difference in tabular form

    | AngularJS | Angular |
    |---- | ---------
    | It is based on MVC architecture  | This is based on Service/Controller |
    | This uses use JavaScript to build the application| Introduced the typescript to write the application |
    | Based on controllers concept| This is a component based UI approach|
    | Not a mobile friendly framework| Developed considering mobile platform|
    | Difficulty in SEO friendly application development| Ease to create SEO friendly applications|
	
	
### What is TypeScript?
    TypeScript is a typed superset of JavaScript created by Microsoft that adds optional types, 
	classes, async/await, and many other features, and compiles to plain JavaScript. Angular built 
	entirely in TypeScript and used as a primary language.
    You can install it globally as
    ```
    npm install -g typescript
    ```
    Let's see a simple example of TypeScript usage,
    ```typescript
    function greeter(person: string) {
        return "Hello, " + person;
    }
    let user = "Laxman";
    document.body.innerHTML = greeter(user);
    ```
    The greeter method allows only string type as argument.
	
### What are the key components of Angular?
    Angular has the below key components,
    1. **Component:** These are the basic building blocks of angular application to control HTML views.
    2. **Modules:** An angular module is set of angular basic building blocks like component, 
	   directives, services etc. An application is divided into logical pieces and each piece of 
	   code is called as "module" which perform a single task.
    3. **Templates:** This represent the views of an Angular application.
    4. **Services:** It is used to create components which can be shared across the entire application.
    5. **Metadata:** This can be used to add more data to an Angular class.
	
### What are lifecycle hooks available?
    1. **ngOnChanges:** When the value of a data bound property changes, then this method is called.
    2. **ngOnInit:** This is called whenever the initialization of the directive/component after Angular 
		first displays the data-bound properties happens.
    3. **ngDoCheck:** This is for the detection and to act on changes that Angular can't or won't detect on its own.
    4. **ngAfterContentInit:** This is called in response after Angular projects external content into the component's view.
    5. **ngAfterContentChecked:** This is called in response after Angular checks the content projected into the component.
    6. **ngAfterViewInit:** This is called in response after Angular initializes the component's views and child views.
    7. **ngAfterViewChecked:** This is called in response after Angular checks the component's views and child views.
    8. **ngOnDestroy:** This is the cleanup phase just before Angular destroys the directive/component.