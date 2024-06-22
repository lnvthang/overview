# REVISION LESSON 03 - OOP

## Outline
1. Define, Class
2. Encapsulation + Access Modifier + Get/Set
3. Static
4. Inheritance
5. Polymorphism + Virtual + Override + Abstract
6. Abstraction + Interface
7. Notes
---

## Fundamental knowledge

### 1. Define, Class

- OOP = **Class** + **Object**
- Object have 2 parts: properties and methods
- Constructor: 
    - There are 2 methods: Argument and without argument
- Deconstructor
    - Remove object, only 1 method and auto call
    - Called when finish method, program, block
    - Syntax:
```csharp
    ~Person() {
        Console.WriteLine("Cancel");
    }
```
---

### 2. Encapsulation + Access Modifier + Get/Set

- There are 5 access modifier: public, private, protected, internal, protected internal

|Access modifier| Description                       |
|-                   |-                                  |
| public             | Be able to access class or method |
| private            | Only internal class can access |
| protected          | Such private, in addition, it's posible access from inheritance class  |
| internal           | Only access internal a assembly, used for class |
| protected internal | Such internal, in addition, it's posible access from inheritance class |

- Internal for class, private for properties in class if you don't declare access modifier for them
- Get + Set
- Syntax

```csharp
public double Money
{
    get { return money; }
    set {
        if (value <= 10 || value >= 0)
        {
            money = value;
        }
    }
}
```

---

### 3. Static

- Only allocated a memory for program, so use static to general some thing manage  
- There are 4 parts: static + variable, method, class and constructor
- Static will be declared only a memory during program compiled, remove when finished program
- Avoid wasting memory because static used by name class, no need to initialize instance
- Static class: Only contain static properties(variable, method)
- Static constructor:
    - No need access modifier
    - Call once

---

### 4. Inheritance
- public or protected are inheritanced for sub_class, except private

- Using **base** keyword to inheritanced constructor **with argument** for sub_class by super_class
- Syntax

```csharp
    public Cat(double w, double h) : base(w,h) 
    {
    }

    // derived class | base class
    class sub_class : super_class {}
    ---
    public class sub_class extends super_class {} // Java
    public class sub_class : super_class {} // CSharp
```

---

### 5. Polymorphism + Virtual + Override + Abstract

- Virtual is keyword to declare a virtual method (it's possible override)
- Override is keyword to override super_class method
- Super_class: **virtual** => sub_class: **override**
- Syntax

```csharp
class Animal 
{
    public virtual void Speak() 
    {
        Console.WriteLine("Animal is speaking...");
    }
}

class Dog : Animal
{
    public override void Speak() 
    {
        Console.WriteLine("Dog is speaking...");
    }
}


class Cat : Animal
{
    public override void Speak() 
    {
        Console.WriteLine("Cat is speaking...");
    }
}

class Program
{
    static void Main(string[] args) {
        Animal cat = new Cat();
        Animal dog = new Dog();

        cat.Speak();
        dog.Speak();

        Console.ReadLine();
    }
}

```

- Abstract

```csharp
abstract class Animal 
{
    public abstract void Speak();
}
```

---

### 6. Abstraction + Interface
- Class can implement **interfaces** but extend **a class**
- Interface can implement **interfaces** but can't implement **class**

| Interface | Abstraction |
| - | - |
| Be able to inheritanced the other interfaces |  Be able to inheritanced a class and the other interfaces |
| Only contain method and no need content method |  Be able to contain properties and method |
| No need to use override keyword |  Have to use override keyword |
| Access modifier: public |  Access modifier: all of them |
| Class can implement interfaces | Class only implement a abstract class or class |


---

### 7. Notes
- Java

```java
class sub_class extends super_class {  
   //methods and fields
}

class Pig implements IAnimal {
    //methods
}
```
- Csharp

```csharp
class sub_class : super_class {  
   //methods and fields
}

class Pig : IAnimal {
    //methods
}
```