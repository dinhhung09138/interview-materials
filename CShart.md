### How can pass parameter to a method?

- Value parameters. copies the actual value of an argument to the parameter. the change inside the function have no effect on the argument.
- Reference parameters: copies the reference to the memory location of an argument into the formal parameter. It means that changes made to the parameter affect to the argument.
- Output parameters: help method return more than 1 value.

### ref and out

both copy memory address of an argument into method. Use when you want to allow method to modify the value of variable, and any change made inside the method affect the original variable

- ref: the variable must be initialized before it passed to the method
- out: not require initialize but must assign value before it returns.

### Connection Pool?

It is a collection of connections which are shared between the clients requesting one. Once the connections is closed, it returns back to the pool. This allows the connections to be reused.

### Class vs Object

Classes define what the object look like, how they act and what sort of properties do they have. Object do similar-acting make up those classes.

### Class vs Record?

both of them are defined to store data. Record is immutable and class is not. Record only assigns data when it created via constructor

### Class vs Struct?

- Class is reference type, struct is value type
- Class hosted on the heap, structs are hosted on the stack
- Struct are more limited than classes
- Class object are create using the new keyword. while struct instances are not
- Class can assign null. struct cannot
- Structures does not support inheritance

### Managed code and Unmanaged code

- Manage code is a type of code that has been created and compiled within the .NET framework.
- Unmanaged code come from a different software building framework, we can use that features and setting they provides

### Stack and Queue?

- Stack: last in first out. Stacks process value types by top- down hierarchy
- Queue: First In First Out. Queues follow this principle and insert items from the lower and while deleting ones from the top

### Boxing vs Unboxing?

Boxing converts a value type(int, char..) to reference type(object, string,..).

Unboxing convert reference type to value type.

Value type stored in Stack memory and reference type stored in heap memory.

### Value type vs Reference Type?

**Value type** will directly store the variable value in memory. It will also accept both signed (int, short, byte) and unsigned literal (ushort, ulong, uint..)

**Reference data type**: contain a memory address of variable value because the reference types won’t store the variable value directly in memory. (string, object,)

### Stack vs Heap memory?

**Stack memory** is a region of memory that is used to store local variable and function call information. stack is last in first out. Stack very fast to allocate and deallocate memory from it. However, stack  has a limited size and con only store a finite amount of data. If the stack grows to large, it can cause a stack over flow, which can lead to a crash or other unpredictable behavior.

**Heap memory** is a region of memory that is used to store objects. It is not organized in a particular order and can be accessed randomly. Objects are dynamically allocated on the heap by using “new” keyword. when object is no longer needed, it is the responsibility of the garbage collector to deallocate the memory and reclaim it for the future use. The heap is a more flexible region of memory than the stack, but it also slower to allocate and deallocate memory.

### Count vs Count() (braces)

- Count() (braces) is an extension method introduced by LINQ
- Count property is part of the List itself (derived from **ICollection**)

LINQ checks If your **IEnumerable** implements **ICollection** and if it does not uses the **Count** property. So there is no difference which one you use for a List.

### Count() vs Any

Any help code readable. Any allocates some bytes (depending on collection type).

Count faster than Any but not much.

Count method is indeed optimized for collections with known length, So it’s not counting the elements one by one (Dictionary, List).

### Length vs Count

- **Count**: use for collections which is the number of items that can be changed over time.
- **Length**, is the maximum number of items it can hold. and it is immutable

### Array vs List vs Dictionary

**Array**

- Use when data size is fixed and unchanging
- All items are the same kind
- The size is immutable once defined.
- Every item identifiable by a unique index.
- Access an element faster but adding or removing elements is more slower
- Memory use lower than List

**List**

- Use when dynamic data
- A dynamic collection, all items are the same kind.
- Can add more item into the list
- Access an element slower but adding or removing elements is more faster, good to work with dynamic data
- Memory used higher than Array

### Static Method vs SingleTon?

**Singleton**

- Allows access to a single created instance that instance can be passed as a parameter to other methods.
- Singleton objects are stored in the **heap**
- Can clone singleton object as long as the designer allows
- We can implement an interface through a singleton class

**Static class**

- allows only static methods.
- Store in the **Stack**
- Can not clone static class
- Can not implement from an interface

### Variable vs constant?

**Variable** is a place on the computer where data is stored. Each variable has a designed type of data with a specific name assigned to them.

**Constants** are almost the same things as variables except that they have specific values attached to them, which can’t be altered

### Constant vs Read-Only?

**Constant** variables are declared and initialized at compile time.
**Read-only** allocate the value at runtime.

### Partial class?

A partial class divides the definition of a class into different classes that can be found in the same or different source code files.
A class meaning can be written in multiple files, but it is gathered as a single class at runtime.

### Garbage collector?

It is a special tools in .NET that are designed to free up unused space and thus make the framework run and operate faster.

### Encapsulation

It is a function that includes various methods and data with in a project. This is done so that the object of the program could perform its functions smoothly and without any errors

### Inheritance

It is a relationship between two classes. Inheritance happens when one smaller class take on the features and parameters of another, bigger class. This bigger class is the parent class.  two type of inheritance:

- implementation inheritance: When a class derived from another class such that it inherits all the members of the base type it.
- Interface inheritance. when a class or struct inherits only the signatures of the functions from another type.

To prevent a class from being inherited is using **sealed** keyword.

.Net support single implementation inheritance and multiple interface inheritance.

### Overloading

Its allows to have multiple methods within the same class with the same name, but with different parameters. Each of these methods has their own implementation as well. That mean they can behave differently purposes. It is a compile-time polymorphism because each of different overloaded methods is resolved when the application is compiled.

### Overriding

It is a concept where a method in derived class uses the same name, return type and arguments as a method in its base class. In other words, if the derived class contains its own implementation of the method rather than using the method in the base class. It is known as runtime (or dynamic) polymorphism because the type of the calling object is not known until runtime.

### What is interface

Is a standard or contract that contains only signatures of methods or events. The implementation is done in the class that inherits from this interface.

### Abstract class

It is an special class containing abstract methods and properties. It is restricted class that cannot used to create objects (To access it, it must be inherited from another class). Abstract class can have abstract method (it does not have body. The body is provided by the derived class) and regular methods, It designed for inheritance.

### Interface vs Abstract class

Both of them is a special types of classes that contain only methods declaration and not their implementation. When a derived class inherit an interface, it must implement all methods inherited. whereas a derived class inherit an abstract class only implement all abstract methods.

### Using IF-ELSE condition

- Check multiple condition with different logic
- Checking Range of values
- Complex condition
- Having Nullable values

### Using SWITCH CASE condition

- Checking a Single variable with multiple value
- Checking enumeration
- Multiple exact matches
- Code clarity and readability

### Using While

Loop for don’t know repetition based on a condition

### Using Do-White

Loops when you need to run the loop body at least once

### Using For

Loop when you know the exact number of iterations or need a loop counter.

### string vs String

- string is a shorthand, an alias for System.String namespace in .Net framework.
- .NET framework was use String class.
- when C# introduce string is a shorthand notation.

### What is OOP?

Object oriented Programming is a programming model work around object concept. Object is a real world entities like class, that contain some characteristics and behaviors specified in the class template.

With OOP help the development easier, a big software can be easily to write and managed by using OOP. With OOPs, the code can be readability, maintainability, understandability, reusable.

Some features:

- **Inheritance**: It is a concept that allows us to define a new class based on an existing class. The new class inherits the properties and methods of the existing class and also add new properties and methods of its own. Inheritance promotes code reuse, simplifies code maintenance, and improve code organization
- **Encapsulation**: wrapping up of data and information under a single unit. It protect the data that prevent access by the code from outside.
- **Polymorphism**: When we have many classes that are related to each other by inheritance. cat, dog, pig have different sound.
- **Abstraction**: It means that only the required information is visible to the user and the rest of the information is hidden.

### Constructor

It is a special method whose name is the same as class name. The constructors serve the special purpose of initializing the objects. We can create constructor without parameter or any parameters. 5 types: default, parameterized, Copy, Static, and Private constructor

### Deadlock?

It is a situation where two or more threads are unmoving or frozen in their execution because they are waiting for each other to finish

**To prevent DeadLock**

- Avoid holding a lock for too long. We need to release the lock as soon as you don’t need it
- Avoid nested locks
- Use a timeout. after a time you can throw an exception or take other actions
- Use asynchronous programming technique, allows multiple threads to run concurrently without blocking each others.

### concurrency and thread safety?

Thread is a single sequence of instructions that a process can execute. By default , C# provide start single thread, this main thread execute your code line by line. Multiple thread allows a process to manage two or more concurrent thread. Each thread can handle a task independently. Single thread is simpler to implement and debug. while multithread can improve performance by performing tasks concurrently.

### Async and Await

keyword simplify managing multithreaded application easy to read and maintain. with **Async** method, will tell C# to delegate the rest of the functions execution to a worker thread. thus the main thread can do other tasks.

Thread Safe collection: which are designed to ensure safe access to shared resources in multithread environments. ConcurentBag, ConcurrentQueue, ConcurrentStack.

### Different Task and Thread

A thread is a part of the task.

A thread represents the smallest unit of code processing at the OS level, with stacks and kernels.

A task is executed by a TaskScheduler and cannot create its own OS thread.

### Inversion of control?

used to decouple the dependencies between layers and components in the system.
Dependency Inject pattern is an example of an IoC pattern that helps in removing dependencies in the code.

### What is Dependency Injection Design Pattern?

It is a process in which we are injecting the dependent object of a class into a class that depends on that object.
It allows us to develop loosely-coupled code that is flexible, clean, easy to maintain, better testable, and reusable

There are 3 steps:

- Create an Interface or base class is present to provide an abstraction for dependency implementation
- Dependency is registered in a service container
- Service is injected to the class that it depends on.

We have 3 ways to implement DI.

- Constructor inject. is the most commonly used, inject a class inside constructor
- Property Inject.  In sometime we are are inject the services  with some parameters.
- Method inject: We only need to pass the dependency in the method. The entire class does not required dependency, just one method.

### Repository Pattern?

This is the layer between data source and business logic in an application. Repository Pattern is a class defined for an entity and all operations for it. ex. an Repository for entity Customer. with basic CRUD operation and any other possible operations related to it.

With Repository Pattern help:

- Separation of Concerns: It separate the logic for data access from the business logic. It make more clear and maintainable code
- Centralized Data Access: All data access logic is in one place, it makes easier to manage and modify
- Improved Testability: It easy to mock test.

2 Type Repository

- One repository per Entity (non-generic): Use one repository class for each entity.
- Generic Repository: A generic repository is the one that can be used for all the entities. It provides a generic interface and methods (get, add, update, delete)

Problem is Repository pattern always open new database transaction to do specific action, So this is not good for performance. and if they are edit on the same record, one success and one fail. It will result database in-consistency

Unit Of work is involves insert/update/delete operation, all in one single transaction.

Benefit:

- Code is cleaner, easier to reuse and maintain
- Enables us to create loosely coupled systems
- It is easy to mock and replace an real repository with a fake implement for unit test.

### SOLID principle?

SOLID are object oriented design concepts.

- Single Repository Principle: Each class or module should be responsible for only one functionality.
- Open-Closed principle: Open for extension and close for modification.
- Liskov Substitution Principle: Object in the child class can replace supper class without breaking the system.
- Interface Segregation Principle: Separate a big interface into many small interfaces
- Dependency Inversion Principle: High-level modules should not depend on low-level modules. Both should depend on abstractions

### What is Integration Test?

It is a level of software testing where individual units or components of an application are combined and tested as a group to ensure the work together correctly.

### Unit Test vs Integration Test?

Unit test: tests individual units or component of a system isolation, usually using mocks or stubs of dependencies

Integration Test: Tests how multiple unit work together as a whole, verifying that they integrate correctly.

### What is design pattern?

A design pattern is a reusable and generalized solution to a common problem that arises during software design and development.

- Creational Pattern: provide freedom of choice between creating objects by hiding the logic..  Factory, Builder, Singleton, Abstract Factory
- Structural Pattern: help in defining how the structures of classes and objects should be like for defining composition between classes, interfaces and objects. Adaptor, Facade, Decorator, Proxy
- Behavior Patterns: define how the object should communicate and interact with one another. Command, Iterator, Observer,  Strategy