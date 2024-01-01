<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [OOP-1: Intro to OOP ](#oop-1-intro-to-oop)
   * [Key Terms ](#key-terms)
   * [Why LLD ](#why-lld)
   * [Programming paradigms ](#programming-paradigms)
      + [Procedural programming ](#procedural-programming)
      + [Object-oriented programming ](#object-oriented-programming)
   * [Abstraction ](#abstraction)
   * [Encapsulation ](#encapsulation)
- [OOP-2: Access Modifiers and Constructors ](#oop-2-access-modifiers-and-constructors)
   * [Key terms ](#key-terms-1)
   * [Constructors ](#constructors)
   * [Access modifiers ](#access-modifiers)
- [OOP-3: Inheritance and Polymorphism ](#oop-3-inheritance-and-polymorphism)
   * [Inheritance](#inheritance)
   * [What is Polymorphism?](#what-is-polymorphism)
- [OOP-4: Interfaces, Abstract Classes, Composition, Association ](#oop-4-interfaces-abstract-classes-composition-association)
   * [Interfaces](#interfaces)
   * [Abstract Classes](#abstract-classes)

<!-- TOC end -->

## OOP-1: Intro to OOP 

### Key Terms 
  - LLD
      - Low-level design (LLD) is a component-level design process that follows a step-by-step refinement process. This process can be used for designing data structures, required software architecture, source code and ultimately, performance algorithms. Overall, the data organization may be defined during requirement analysis and then refined during data design work. Post-build, each component is specified in detail
  - Procedural programming
      - Procedural programming is a programming paradigm that uses a sequence of steps to solve a problem.
  - Object-oriented programming
      - Object-oriented programming (OOP) is a programming paradigm that uses objects to model real-world things and aims to implement state and behavior using objects.
  - Abstraction
      - Abstraction is the process of hiding the implementation details of a program from the user.
  - Encapsulation
      - Encapsulation is used to hide the values or state of a structured data object inside a class, preventing direct access to them by clients in a way that could expose hidden implementation details or violate state invariance maintained by the methods.
  - Classes
      - A class is a blueprint which you use to create objects.
  - Object
      - An object is an instance of a class.
  
### Why LLD 
  - The goal of LLD or a low-level design (LLD) is to give the internal logical design of the actual program code. Low-level design is created based on the high-level design. LLD describes the class diagrams with the methods and relations between classes and program specs. It describes the modules so that the programmer can directly code the program from the document.
  - A good low-level design document makes the program easy to develop when proper analysis is utilized to create a low-level design document. The code can then be developed directly from the low-level design document with minimal debugging and testing. Other advantages include lower cost and easier maintenance
  - Ultimately, LLD has the following goals:
      - Low level implementation details of a system
      - organization of code
      - write good software
  - What is a good software? 
      - A good software is a software that is
          - easy to maintain
          - easy to scale.
          - easy to extend
  - Maintainability 
      - Software is not static. If you build a valuable product that works perfectly but is difficult to modify and adapt to new requirements, it will not survive in today’s market. Maintainability is a long-term aspect that describes how easily software can evolve and change, which is especially important in today’s agile environment.
      - The ease with which a software system or component can be modified to correct faults, improve performance or other attributes, or adapt to a changed environment
      - ISO 25010 states that a highly maintainable software system must possess the following qualities:
          - Modularity - The product is composed of discrete components such that a change to one component has minimal impact on other components.
          - Reusability - The product makes use of assets that can be re-used in building other assets or in other systems.
          - Analyzability - The impact of an intended change on the product, diagnosis of deficiencies, causes of failures or identification of the components that need to be changed can be analyzed effectively and efficiently.
          - Modifiability - The product can be effectively and efficiently modified without introducing defects or degrading existing product quality.
          - Testability - The test criteria can be established effectively and efficiently, and the product can be tested to determine whether those criteria have been met.
      - Scenarios -
          - How easy it is for a new developer to contribute to the product?
          - Can I add a new feature to the product without impacting existing functionality?
          - Can I get an insight into the product’s performance?
  - Scalability
      - Software scalability is an attribute of a tool or a system to increase its capacity and functionalities based on its users’ demand. Scalable software can remain stable while adapting to changes, upgrades, overhauls, and resource reduction.
      - Scenarios -
          - You just expanded your business to North America and Europe. Will your software be able to handle the users?
          - How will your application perform when it has multiple users using it at the same time?
          - Does your application provide a good user experience?
  - Extensibility
      - Extensibility is a software engineering and systems design principle that provides for future growth. Extensibility is a measure of the ability to extend a system and the level of effort required to implement the extension. Extensions can be through the addition of new functionality or through modification of existing functionality. The principle provides for enhancements without impairing existing system functions.
      - Scenarios -
          - Your application uses PayTM for payment, and you want to add a new payment method. It can be a very simple task based on how your software is structured.
          - You use AWS for deployment and now a client wants to use your application on their own server. Again, will your code be able to handle this?
          - If I change my backend code, will my frontend code be affected?
          - Extensibility vs Reusability
          - Extensibility and reusability have many emphasized properties in common, including low coupling, modularity and high risk elements’ ability to construct for many different software systems, which is motivated by the observation of software systems often sharing common elements. Reusability together with extensibility allows a technology to be transferred to another project with less development and maintenance time, as well as enhanced reliability and consistency
### Programming paradigms 
  - Some paradigms are focused on the execution model, addressing issues like side effects and the sequence of operations during program execution. Others prioritize the organization of code, grouping it into units with associated state modifications, as seen in object-oriented programming. Additionally, certain paradigms concentrate on the stylistic aspects of syntax and grammar, aiming for clarity and expressiveness in code. Overall, these paradigms offer distinct approaches to problem-solving, allowing developers to choose the most suitable one based on their specific needs and preferences.
  - There are two major types of programming paradigms:
      - Imperative - an imperative program consists of commands for the computer to perform to change state e.g. C, Java, Python, etc.
      - Declarative - focuses on what the program should accomplish without specifying all the details of how the program should achieve the result e.g. SQL, Lisp, etc.
  - We will be focusing on the imperative paradigm which has the two following subtypes.

#### Procedural programming 
  - It is based on the concept of the procedure call. Procedures (a type of routine or subroutine) simply contain a series of computational steps to be carried out. Any given procedure might be called at any point during a program's execution, including by other procedures or itself.
  - Think of all programming as managing the relationship between two fundamental concepts: state and behavior. State is the data of your program. Behavior is the logic.
  - Procedural Programming is based on implementing these two concepts separately. State is held in data structures. Behavior is held in functions (also known as procedures or subroutines). A procedural application therefore passes data structures into functions to produce some output.
  - Procedural code thinks of the actions that it has to perform as a series of steps. Imagine you want to transfer some money from one account to another. These are the following steps that you would take:
      - Open the source account
      - Withdraw the money
      - Open the destination account
      - Deposit the money in destination account
  - A procedural version of this program would be:

```java
import java.util.List;

public class AccountTransfer {

  public static void transfer(int source, int destination, int amount) {
      Account sourceAccount = getAccount(source);
      updateAccount(sourceAccount, -amount);

      Account destinationAccount = getAccount(destination);
      updateAccount(destinationAccount, amount);
  }

  public static Account getAccount(int number) {
      return accounts.stream()
              .filter(account -> account.getNumber() == number)
              .findFirst()
              .orElseThrow(() -> new IllegalArgumentException("Account not found for number: " + number));
  }

  public static void updateAccount(Account account, int delta) {
      account.setBalance(account.getBalance() + delta);
  }

  // Sample Account class to represent the structure of an account
  static class Account {
      private int number;
      private int balance;

      public Account(int number, int balance) {
          this.number = number;
          this.balance = balance;
      }

      public int getNumber() {
          return number;
      }

      public int getBalance() {
          return balance;
      }

      public void setBalance(int balance) {
          this.balance = balance;
      }
  }

  // Sample list of accounts
  private static List<Account> accounts;

  public static void main(String[] args) {
      // Initialize accounts with some sample data
      accounts = List.of(new Account(1, 1000), new Account(2, 2000));

      // Example usage of transfer function
      transfer(1, 2, 500);

      // Print updated account balances
      for (Account account : accounts) {
          System.out.println("Account " + account.getNumber() + ": Balance = " + account.getBalance());
      }
  }
}
```
#### Object-oriented programming 
  - Object-Oriented Programming is based on implementing the state and behaviour concepts together. State and behaviour are combined into one new concept: an Object. An OO application can therefore produce some output by calling an Object, without needing to pass data structures.
  - The focus of procedural programming is to break down a programming task into a collection of variables, data structures, and subroutines, whereas in object-oriented programming it is to break down a programming task into objects that expose behavior (methods) and data (members or attributes) using interfaces. The most important distinction is that while procedural programming uses procedures to operate on data structures, object-oriented programming bundles the two together, so an "object", which is an instance of a class, operates on its "own" data structure.
  - Advantages of OO include the potential for information hiding: if a caller needn't pass any data structure, then the caller needn't be aware of any data structure, and can therefore be completely decoupled from the data format.

```java
public class OopBankAccount {
  private Integer number;
  private Integer balance;

  public OopBankAccount(Integer number, Integer balance) {
      this.number = number;
      this.balance = balance;
  }

  void deposit(Integer amount) {
      this.balance  += amount;
  }

  void withdraw(Integer amount) {
      this.balance  += amount;
  }

  void transfer(OopBankAccount destination, Integer amount) {
      this.withdraw(amount);
      destination.deposit(amount);
  }

}
```
  - Advantages:
      - Reusability: Through classes and objects, and inheritance of common attributes and functions.
      - Security: Hiding and protecting information through encapsulation.
      - Maintenance: Easy to make changes without affecting existing objects much.
      - Inheritance: Easy to import required functionality from libraries and customize them, thanks to inheritance.
  - Disadvantages:
      - Beforehand planning of entities that should be modeled as classes.
      - OOPS programs are usually larger than those of other paradigms.
      - Banana-gorilla problem - You wanted a banana but what you got was a gorilla holding the banana and the entire jungle
### Abstraction 
  - the creation of abstract concept-objects by mirroring common features or attributes of various non-abstract objects or systems of study[3] – the result of the process of abstraction. is a mechanism which represent the essential features without including implementation details
  - Objects in an OOP language provide an abstraction that hides the internal implementation details. Similar to the coffee machine in your kitchen, you just need to know which methods of the object are available to call and which input parameters are needed to trigger a specific operation. But you don’t need to understand how this method is implemented and which kinds of actions it has to perform to create the expected result.
  - Advantages of Abstraction:
      - Abstraction is used to create a boundary between the application and the client code. This could help us to reduce the design and implementation complexity of software.
      - In complex software, abstraction helps us separate responsibilities into software entities (classes, method, etc.) that only know the required functionality of each other but not how that functionality is implemented.
      - Abstraction maximizes ease of use for the relevant information. In other words, the code with proper abstraction help programmers to quickly make sense of what that code does and what it is meant to be used for. It avoids code duplication and increases code reusability.
      - Abstraction allows the programmer to simplify programming and shift focus from implementation details of actions toward the classes, available methods, etc. It will enable the user to avoid writing low-level code.
      - It allows the programmer to change the internal implementation of methods or concrete classes without hampering the interface.
      - Using abstraction, we can increase the code security as only relevant details will be provided to users.
### Encapsulation 
  - encapsulation refers to the bundling of data with the methods that operate on that data, or the restricting of direct access to some of an object's components. Encapsulation is used to hide the values or state of a structured data object inside a class, preventing direct access to them by clients in a way that could expose hidden implementation details or violate state invariance maintained by the methods
  - Encapsulation may also refer to a mechanism of restricting the direct access to some components of an object, such that users cannot access state values for all of the variables of a particular object. Encapsulation can be used to hide both data members and data functions or methods associated with an instantiated class or object.
  - Advantages of Encapsulation:
      - Hiding Data - Users will have no idea how classes are being implemented or stored. All that users will know is that values are being passed and initialized.
      - More Flexibility - Enables you to set variables as read or write-only. Examples include: setName(), setAge() or to set variables as write-only then you only need to omit the get methods like getName(), getAge() etc.
      - Easy to Reuse - With encapsulation it's easy to change and adapt to new requirements.
  - Classes  
      - A class is a blueprint for creating objects (a particular data structure), providing initial values for state (member variables or attributes), and implementations of behavior (member functions or methods). The user-defined objects are created using the class keyword.
      - When an object is created by a constructor of the class, the resulting object is called an instance of the class, and the member variables specific to the object are called instance variables, to contrast with the class variables shared across the class.
      - In order to create a class in Java, you need to use the class keyword.

```java
 class AsiaCup {
  private String name;
}
```
  - A class is a blueprint which you use to create objects. An object is an instance of a class - it's a concrete 'thing' that you made using a specific class. So, 'object' and 'instance' are the same thing, but the word 'instance' indicates the relationship of an object to its class.
  - You can create a new instance of a class by using the new keyword and the constructor of the class.
  - `AsiaCup instance1 = new AsiaCup();`
  - `AsiaCup instance2 = new AsiaCup();`
  - Changing the value of a member variable is done by using the dot operator (.) to access the member variable.
```
instance1.name = "Asia Cup 2022";
instance2.name = "Asia Cup 2023";

System.out.println(instance1.name); // Asia Cup 2022
System.out.println(instance2.name); // Asia Cup 2023 
```

## OOP-2: Access Modifiers and Constructors 

### Key terms 
- Constructor
    - a constructor (abbreviation: ctor) is a special type of subroutine called to create an object. It prepares the new object for use, often accepting arguments that the constructor uses to set required member variables.
- Access modifier
    - An access modifier defines the accessibility of a class, attribute, method or constructor. There are four types of access modifiers in Java: public, protected, default (no modifier), and private.

### Constructors 
  - Default constructor 
      - A default constructor is a constructor created by the compiler if we do not define any constructor(s) for a class.
      - A default constructor is a constructor that either has no parameters, or if it has parameters, all the parameters have default values. If no user-defined constructor exists for a class and one is needed, the compiler implicitly declares a default parameterless constructor.
      - A default constructor is also known as a no-argument constructor or a nullary constructor. All fields are left at their initial value of 0 (integer types), 0.0 (floating-point types), false (boolean type), or null (reference types) An example of a no-argument constructor is:

```java
public class Student {
    private String name;
    private String email;
    private Integer age;
    private String address;
    private String batchName;
    private Integer psp;

    public Student() {
        // no-argument constructor
    }
}
```
  - Notice a few things about the constructor which we just wrote. First, it's a method, but it has no return type. That's because a constructor implicitly returns the type of the object that it creates. Calling new Student() now will call the constructor above. Secondly, it takes no arguments. This particular kind of constructor is called a no-argument constructor.
  - Syntax of a constructor
      - In Java, every class must have a constructor. Its structure looks similar to a method, but it has different purposes. A constructor has the following format <Constructor Modifiers> <Constructor Declarator> <Constructor Body> 
      - Constructor declarations begin with access modifiers: They can be public, private, protected, or package access, based on other access modifiers. Unlike methods, a constructor can't be abstract, static, final, native, or synchronized.
      - The declarator is the name of the class, followed by a parameter list. The parameter list is a comma-separated list of parameters enclosed in parentheses. The body is a block of code that defines the constructor's behavior.
      - Constructor Name (Parameter List)
  
  - Parameterised constructor
      - Now, a real benefit of constructors is that they help us maintain encapsulation when injecting state into the object. The constructor above is a no-argument constructor and hence value have to be set after the instance is created.
      - `Student student = new Student();`
      - `student.name = "Eklavya";`
      - `student.email = "ek@drona.in"; `
      - The above approach works but requires setting the values of all the fields after the instance is created. Also, we won't be able to validate or sanitize the values. We can add the validation and sanitization logic in the getters and setters but we wont be able to fail instance creation. Hence, we need to add a parameterised constructor. A parameterised constructor has the same syntax as the constructors before, the onl change is that it has a parameter list.

```java
public class Student {
    private String name;
    private String email;

    public Student(String name, String email) {
        this.name = name;
        this.email = email;
    }
}
```
  - Now the objects can be created with the following syntax:
  - Student student = new Student("Eklavya", "ek@drona.in"); 
  - In Java, constructors differ from other methods in that:
      - Constructors never have an explicit return type.
      - Constructors cannot be directly invoked (the keyword “new” invokes them).
      - Constructors should not have non-access modifiers.

### Access modifiers 

- There are two types of modifiers in Java: access modifiers and non-access modifiers.
- The access modifiers in Java specifies the accessibility or scope of a field, method, constructor, or class. We can change the access level of fields, constructors, methods, and class by applying the access modifier on it.
- There are four types of access modifiers in Java:
    - public - The access level of a public modifier is everywhere. It can be accessed from within the class, outside the class, within the package and outside the package
    - protected - The access level of a protected modifier is within the package and outside the package through child class. If you do not make the child class, it cannot be accessed from outside the package.
    - private - The access level of a private modifier is only within the class. It cannot be accessed from outside the class.
    - default - The access level of a default modifier is only within the package. It cannot be accessed from outside the package. If you do not specify any access level, it will be the default.

## OOP-3: Inheritance and Polymorphism 

### Inheritance

  - Inheritance is the mechanism that allows one class to acquire all the properties from another class by inheriting the class. We call the inheriting class a child class and the inherited class as the superclass or parent class.
  - The idea behind inheritance in Java is that you can create new classes that are built upon existing classes. When you inherit from an existing class, you can reuse methods and fields of the parent class. Moreover, you can add new methods and fields in your current class also.
  - Inheritance represents the IS-A relationship which is also known as a parent-child relationship.
  - Imagine, as a car manufacturer, you offer multiple car models to your customers. Even though different car models might offer different features like a sunroof or bulletproof windows, they would all include common components and features, like engine and wheels.
  - It makes sense to create a basic design and extend it to create their specialized versions, rather than designing each car model separately, from scratch.
  - In a similar manner, with inheritance, we can create a class with basic features and behavior and create its specialized versions, by creating classes, that inherit this base class. In the same way, interfaces can extend existing interfaces.
  - Let us create a new class User which should be the parent class of Student:

```java
public class User {
    private String name;
    private String email;

    public User(String name, String email) {
        this.name = name;
        this.email = email;
    }
}
```

- Now, let us create a new class Student which should be the child class of User. Let us add some methods specific to the student class:

```java
public class Student {
    private String batchName;
    private Integer psp;
    
    ...
}
```

  - Now in order to inherit the methods and fields of the parent class, we need to use the keyword extends:

```java
public class Student extends User {
    private String batchName;
    private Integer psp;
    
    ...
}
```
  - To pass the values to the parent class, we need to create a constructor and use the keyword super:

```java
public class Student extends User {
    private String batchName;
    private Integer psp;
    
    public Student(String name, String email, String batchName, Integer psp) {
        super(name, email);
        this.batchName = batchName;
        this.psp = psp;
    }
}
```

  - Types of inheritance 
      - There are four types of inheritance:
          - Single - A single inheritance is when a class can have only one parent class.
          - Multilevel - A multilevel inheritance is when a class can have multiple parent classes at different levels.
          - Hierarchical - When two or more classes inherits a single class, it is known as hierarchical inheritance.
          - Multiple - When a class can have multiple parent classes, it is known as multiple inheritance.
  - Diamond problem 
      - In multiple inheritance one class inherits the properties of multiple classes. In other words, in multiple inheritance we can have one child class and n number of parent classes. Java does not support multiple inheritance (with classes).
      - The "diamond problem" (sometimes referred to as the "Deadly Diamond of Death") is an ambiguity that arises when two classes B and C inherit from A, and class D inherits from both B and C. If there is a method in A that B and C have overridden, and D does not override it, then which version of the method does D inherit: that of B, or that of C.

### What is Polymorphism?

- What is Polymorphism?
    - Polymorphism is one of the main aspects of Object-Oriented Programming(OOP). The word polymorphism can be broken down into “Poly” and “morphs”, as “Poly” means many and “Morphs” means forms. In simple words, we can say that ability of a message to be represented in many forms.
    - Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance. Polymorphism is a Greek word that means "many-shaped" and it has two distinct aspects:
        - At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays. When this polymorphism occurs, the object's declared type is no longer identical to its run-time type
        - Base classes may define methods, and derived classes can override them, which means they provide their own definition and implementation. At run-time, when client code calls the method, the CLR looks up the run-time type of the object, and invokes that override of the virtual method. In your source code you can call a method on a base class, and cause a derived class's version of the method to be executed.
    - Polymorphism in Java can be achieved in two ways i.e., method overloading and method overriding.
    - Polymorphism in Java is mainly divided into two types.
        - Compile-time polymorphism
        - Runtime polymorphism
    - Compile-time polymorphism can be achieved by method overloading, and Runtime polymorphism can be achieved by method overriding.
    - Subtyping
        - Subtyping is a concept in object-oriented programming that allows a variable of a base class to reference a derived class object. This is called polymorphism, because the variable can take on many forms. The variable can be used to call methods that are defined in the base class, but the actual implementation of the method is defined in the derived class.
        - For example, the following is our User class:

```java
public class User {
    private String name;
    private String email;
}
```
  - The user class is extended by the Student class:

```java
public class Student extends User {
    private String batchName;
    private Integer psp;
}
```
  - The Student class inherits the name and email properties from the User class. The Student class also has its own properties batchName and psp. The Student class can be used in place of the User class, because the Student class is a subtype of the User class. The following is an example of how this works:
  - `User user = new Student();`
  
  - Method Overloading
      - Method overloading is a feature that allows a class to have more than one method having the same name, if their argument lists are different. It is similar to constructor overloading in Java, that allows a class to have more than one constructor having different argument lists.
      - Let's take an example of a class that has two methods having the same name but different in parameters.

```java
public class User {
    private String name;
    private String email;

    public void printUser() {
        System.out.println("Name: " + name + ", Email: " + email);
    }

    public void printUser(String name, String email) {
        System.out.println("Name: " + name + ", Email: " + email);
    }
}
```
  - In the above example, the class has two methods with the same name printUser but different in parameters. The first method has no parameters, and the second method has two parameters. This is called method overloading.
  - The compiler distinguishes these two methods by the number of parameters in the list and their data types. The return type of the method does not matter.
  
  - Method Overriding
      - Runtime polymorphism is also called Dynamic method dispatch. Instead of resolving the overridden method at compile-time, it is resolved at runtime.
      - Here, an overridden child class method is called through its parent's reference. Then the method is evoked according to the type of object. In runtime, JVM figures out the object type and the method belonging to that object.
      - Runtime polymorphism in Java occurs when we have two or more classes, and all are interrelated through inheritance. To achieve runtime polymorphism, we must build an "IS-A" relationship between classes and override a method.
      - If a child class has a method as its parent class, it is called method overriding.
      - If the derived class has a specific implementation of the method that has been declared in its parent class is known as method overriding.
      - Rules for overriding a method in Java
          - There must be inheritance between classes.
          - The method between the classes must be the same(name of the class, number, and type of arguments must be the same).
      - Let's add a method to our User class:

```java
public class User {
    private String name;
    private String email;

    public void printUser() {
        System.out.println("Name: " + name + ", Email: " + email);
    }
} 
        - Now, let's add a method to our Student class:
        - public class Student extends User {
    private String batchName;
    private Integer psp;

    @Override
    public void printUser() {
        System.out.println("Name: " + name + ", Email: " + email + ", Batch: " + batchName + ", PSP: " + psp);
    }
}

```
  - In the above example, we have added a method to the Student class that overrides the method in the User class. The Student class has a method with the same name and parameters as the User class. The Student class method has an additional print statement that prints the batchName and psp properties.
  - The @Override annotation is optional, but it is a good practice to use it. It is used to ensure that the method is actually being overridden. If the method is not being overridden, the compiler will throw an error.

    - Advantages of Polymorphism
        - Code reusability is the main advantage of polymorphism; once a class is defined, it can be used multiple times to create an object.
        - In compile-time polymorphism, the readability of code increases, as nearly similar functions can have the same name, so it becomes easy to understand the functions.
        - The same method can be created in the child class as in the parent class in runtime polymorphism.
        - Easy to debug the code. You might have intermediate results stored in arbitrary memory locations while executing code, which might get misused by other parts of the program. Polymorphism adds necessary structure and regularity to computation, so it is easier to debug.
          
  - Problems with Polymorphism
      - Implementing code is complex because understanding the hierarchy of classes and its overridden method is quite difficult.
      - Problems during downcasting because implicitly downcasting is not possible. Casting to a child type or casting a common type to an individual type is known as downcasting.
      - Sometimes, when the parent class design is not built correctly, subclasses of a superclass use superclass in unexpected ways. This leads to broken code.
      - Runtime polymorphism can lead to the real-time performance issue (during the process), it basically degrades the performances as decisions are taken at run time because, machine needs to decide which method or variable to invoke

## OOP-4: Interfaces, Abstract Classes, Composition, Association 

### Interfaces
    - An interface is a reference type in Java. It is similar to a class, but it cannot be instantiated. It can contain only constants, method signatures, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods.
    - It can be thought of as a blueprint of behavior. It is used to achieve abstraction and multiple inheritance in Java.
    - Why use an interface?
        - It is used to achieve abstraction.
        - Due to multiple inheritance, it can achieve loose coupling.
        - Define a common behavior for unrelated classes.
    - How to create an interface?
    - Let us create an interface for a Person

```java
public interface Person {
    String getName();
    String getEmail();
}
```

- Now let's create a class that implements the Person interface:

```java
public class User implements Person {
    private String name;
    private String email;

    public User(String name, String email) {
        this.name = name;
        this.email = email;
    }

    @Override
    public String getName() {
        return name;
    }

    @Override
    public String getEmail() {
        return email;
    }
}
```

### Abstract Classes
  - An abstract class is a class that is declared abstract. It may or may not include abstract methods. Abstract classes cannot be instantiated, but they can be subclassed. When an abstract class is subclassed, the subclass usually provides implementations for all of the abstract methods in its parent class. However, if it does not, then the subclass must also be declared abstract.
  - Why use an abstract class?
      - It is used to achieve abstraction.
      - It can have abstract methods and non-abstract methods.
      - When you don't want to provide the implementation of a method, you can make it abstract.
      - When you don't want to allow the instantiation of a class, you can make it abstract.
  - How to create an abstract class?
      - Let us create an abstract class for a Person You can create an abstract class by using the abstract keyword. Similarly, you can create an abstract method by using the abstract keyword.

```java
public abstract Person {

    public abstract String getName();
    public abstract String getEmail();
}
```

- Now let's create a class that extends the Person abstract class:

```java
public class User extends Person {
    private String name;
    private String email;

    public User(String name, String email) {
        this.name = name;
        this.email = email;
    }

    @Override
    public String getName() {
        return name;
    }

    @Override
    public String getEmail() {
        return email;
    }
}
```
