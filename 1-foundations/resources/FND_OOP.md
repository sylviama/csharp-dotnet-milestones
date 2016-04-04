# Object Oriented Programming 

There are four tenets of object oriented programming, and you encountered all of them during your experience with JavaScript, which itself is an object oriented language.

## Inheritance with Classes

We taught you in the front end course how to handle inheritance in JavaScript with the prototypal style. In C#, you inherit with classes.

```c#
// Base class
class Animal {
    // Simple properties
    public string species { get; set; }
    public double speed { get; set; }
    public int legs { get; set; }


    // Public method
    public void walk () {
        Console.WriteLine("Base class walk method");
        speed = speed + (0.1 * legs);
    }
}

// Derived class
class Lizard : Animal {
    // Adding additional properties to what is inherited from Animal
    public string scaleColor { get; set; }
    public bool camouflage { get; set; }
}

Lizard larry = new Lizard();
larry.legs = 4;
larry.scaleColor = "Brown";
larry.camouflage = false;
larry.walk();
Console.WriteLine("A {0} lizard moving at {1} m/s", larry.scaleColor, larry.speed);
```

## Polymorphism

[Polymorphism](https://msdn.microsoft.com/en-us/library/ms173152.aspx) means that different objects may share the same set of properties and methods, but each may use those properties and methods to achieve different behavior.

For example, in your base class of Animal, you define a general rule of how fast an Animal can walk. However, in the derived Lizard class, you can override that rule to give Lizards a slightly different behavior. For every leg they have, they can move twice as fast as a generic Animal.

In C#, you use the `virtual` keyword on a method, which allows any derived class to have its own implementation. The derived class can then use the `override` keyword to tell the compiler that it is redefining the base class' method.

```c#
// Base class
class Animal {
    // Simple properties
    public string species { get; set; }
    public double speed { get; set; }
    public int legs { get; set; }


    // Public method that can be redefined by derived classes
    public virtual void walk () {
        Console.WriteLine("Animal class walk method");
        speed = speed + (0.1 * legs);
    }
}

// Derived class
class Lizard : Animal {
    // Adding additional properties to what is inherited from Animal
    public string scaleColor { get; set; }
    public bool camouflage { get; set; }

    // Redefining the base class implementation
    public override void walk () {
        Console.WriteLine("Lizard class walk method");
        speed = speed + (0.1 * legs);
    }
}

// Create a Lizard
Lizard larry = new Lizard();
larry.legs = 4;
larry.scaleColor = "Brown";
larry.camouflage = false;
larry.walk();

Console.WriteLine("A {0} lizard moving at {1} m/s", larry.scaleColor, larry.speed);

// Create an Animal
Animal andy = new Animal();
andy.legs = 4;
andy.walk();

Console.WriteLine("An animal moving at {0} m/s", andy.scaleColor, andy.speed);

```

## Encapsulation

## Abstraction

### Principles of Object-Oriented Programming
* does Jurnell have Lecture notes?


#### Sonda's Notes on Object Oriented Principles
* it exists because this is how humans understand the world.
* every object has an attribute. An attribute is a set of orthogonal features used to uniquely identify an object.
###### Four Main Principles (memorize the things	!):
  * **Inheritance** → the receiving of properties from a parent
  * **Polymorphism** → Jurnell’s Definition: you can solve the same problem in many different ways, meaning there is no one right answer, but many possible ones that leads to the same solution. Eliza’s Definition: a type whose values and properties are similar to other types // the functionality you have in the base class can be propagated through the children
  * **Encapsulation** → packaging code into containers in which others can interact with what’s inside this containers through specific access ways.
  * **Abstraction** → encapsulating code such that it can be used again and again in a general way.

* refactoring is one of the most important tools a developer can have in order to make the software more readable, efficient, etc.
* data structures and linked lists doesn’t necessarily say anything about how you implement it. You will still need a specific way to implement this data to do something meaningful.


## Resources
* https://en.wikipedia.org/wiki/Object-oriented_programming
* https://msdn.microsoft.com/en-us/library/dd460654.aspx
* http://people.cs.aau.dk/~normark/oop-csharp/pdf/all.pdf
* http://people.cs.aau.dk/~normark/oop-csharp/html/notes/theme-index.html