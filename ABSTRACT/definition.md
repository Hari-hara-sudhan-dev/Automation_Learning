Yes. In Java, the **`abstract` keyword** is used with **classes** and **methods**.

### 1. Abstract Class

An abstract class cannot be instantiated (you cannot create its object directly).

```java
abstract class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}
```

❌ Not allowed:

```java
Animal a = new Animal();   // Error
```

✅ Allowed by creating a subclass:

```java
class Dog extends Animal {
}

Dog d = new Dog();
```

***

### 2. Abstract Method

An abstract method has **only declaration** and **no body**.

```java
abstract class Animal {
    abstract void sound();
}
```

Here:

```java
abstract void sound();
```

* No implementation.
* Subclass must provide the implementation.

```java
class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}
```

***

### Rules of `abstract`

#### Rule 1

If a class contains an abstract method, the class must be abstract.

```java
abstract class Animal {
    abstract void sound();
}
```

#### Rule 2

A subclass must implement all abstract methods.

```java
class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}
```

#### Rule 3

Abstract methods cannot have a body.

❌ Wrong:

```java
abstract void sound() {
    System.out.println("Bark");
}
```

#### Rule 4

Abstract classes can have both abstract and normal methods.

```java
abstract class Animal {
    abstract void sound();

    void sleep() {
        System.out.println("Sleeping");
    }
}
```

***

### Interview Answer

> The `abstract` keyword is used with classes and methods. An abstract class cannot be instantiated, and an abstract method contains only the declaration without implementation. Abstraction helps hide implementation details and forces child classes to provide their own implementation.
