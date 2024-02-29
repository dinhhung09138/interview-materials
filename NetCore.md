### What is different .NET Core and .NET Framework?

- .NET Core open source, compatible with Linux, Windows, MacOS, Does not support Desktop application development, Support microservices development. Lightweight for command line interface
- .NET Framework. Few components are open source. Compatible only with Windows. Supports web, desktop application development. Does not support microservices development. Heavy for Command Line Interface.

### What is Kestrel?

Kestrel is an opensource, cross-platform, and asynchronous server which hosts .NET application.
It is provided as a default server for .NET Core, it is compatible with all the platforms and their versions which .NET Core supports. Usually, its used as an edge-server. which mean it is the server which faces the internet and handles HTTP web request from client directly. Its a listening server with a command-line interface.

### What is .NET Core middleware?

It is a layer, software, or simple class which all the requests and responses have to go through.
The middleware decides to pass the request to the next components or not, or perform some processing an the request before or after passing it.

The middleware order:

- Exception/error handling. to process exception and redirect when the application throw error.
- Use HSTS( Http strict transport security) a standard to protect visitors by ensuring that their browsers always connect to the website over HTTPs.
- Https Redirection middleware, redirects HTTP request to HTTPS
- Static File middleware, return static files. provide no authorization checks, and file including *wwwroot* folder.
- Cookie Policy Middleware. conform the app to the EU General Data Protection Regulation.
- Routing Middleware. to route requests
- Authentication Middleware. Authenticate the user before they’re allowed access to secure resources
- Authorization Middleware authorizes a user to access secure resources
- Session Middleware establishes and maintains session state.
- Endpoint Routing Middleware. to add Razor Pages endpoints to the request pipeline

### Implement Middleware?

- Create a class with publish constructor with a parameter of type RequestDelegate
- A public method named Invoke or InvokeAsync this method must return a task and accept a first parameter of type HttpContext
- To inject middleware, add builder.UseMiddleware<> into the function Configure() method.

### Startup class

It is the central, where we can defines and register services and third-party in ConfigureService method, set up request pipeline in Configure method and setting the application.

### ConfigureService() method

Where you configure the application’s services, or third-party libraries. These services are registered with the build-in DI container and can be injected into your application’s component such as controller, middleware, and other serivices

### Configure() method

Used to set up the request pipeline for handing incoming HTTP request. This method defines how an [ASP.NET](http://ASP.NET) core application will response to different HTTP Request.

### What are service lifetimes in .NET Core

.NET Core support design pattern called Dependency Injection, which helps in the implementation of IOC (Inversion of Control) During registration, dependencies require their lifetime to be defined.

There are 3 types of lifetimes supported by .NET Core:

- Transient Service: Instance is created each time it is requested
- Scoped Service: user-specific instance is once per user and shared across all the requests.
- Singleton Service: Single instance is created once a lifetime of the application

### How configuration works and reading values from the appsetting.json files

key-value pairs across sources (appsetting and environment). Access values buy key using IConfiguration to control app and behavior without hardcode.

### Option Pattern and how is it used in configurate?

It is a design pattern used to manage and load configuration settings from various sources, primarily appsettings.json file.

- defining strongly typed class. You can create classes with properties representing your configuration file. This provides type safety and better code readablity
- Bind configuration: IOption<> interface to bind the corresponding section of the configuration file to your options class.
- Dependency Injection: register the IOptions serivces in the Dependency Injection container. This allows your code to access configuration data throughout the application

### How to config and manage multiple environments?

Configuration.

- Using environment variable ASPNETCORE_ENVIRONMENT values like Development, Staging, or Production
- Multiple aspsettings.json files:
- Other soruces like Azure key Vault, command-line arguments

### Managing Environment

- Tools: using .NET CLI or deployment platforms like Azure Devops to manage environment specific configuration and deployment processes
- Code isolation: Seperate code to different environments (datadatabase connection string) into different assemblies or modules
- Secret management: use secure methods like azure key, password or API key.

### access HttpContext

- inject IHttpContextAccessor into your services via constructor
- Direct access in controller and razor page.

### Caching and Response Caching in .NET Core

- Response caching: HTTP headers cache like Cache-Control to store static content like images or frequently accessed data in the browser or server memory, reducing server load and improving response times.
- Distributed caching store data across a network or servers. Ideal for dynamic content accessed by multiple users, ensuring consistency and scalability
