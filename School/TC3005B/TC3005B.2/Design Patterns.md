---
tags:
  - design-pattern
  - factory
  - singleton
---
Date: 2024-06-05 : 16:21
***

## What is a Design Pattern?

- Something that repeats.
- Avoids confusion of the software engineers. 
- Ways for the **community** to say that software construction is **good**.
- Help in many things: Performance, readability, etc.

## What are they?

- A reusable way of constructing software.
- Ease out maintainability.
- Mitigate errors.

### Benefits

- A big catalog of solutions.
- Standarize the resolution of many problems.
- Condense and simplify the learning of good practices.
- Give a common vocabulary between developers.
- Help us avoid reinventing the wheel.

## Categories

### Creational

- Hide instance details

#### Factory

Create objects the way I want them to.

```java
// Shape.java (Naive Way)
public interface Shape {
	double calculateArea();
	double calculatePerimeter();
}

// ShapeFactory.java (Design-Patter Way)
public class ShapeFactory {
	public static Square createBigSquare() {
		return new Square(10);
	}
	
	public static Square createMediumSquare() {
		return new Square(7);
	}

	public static Square createSmallSquare() {
		return new Square(5);
	}
}

// Circle.java
public class Circle implements Shape {
	Circle(double radius);
	public double calculateArea();
	public double calculatePerimeter();
}

// Square.java
public class Square implements Shape {
	Square(double side)
	public double calculateArea();
	public double calculatePerimeter();
}

// Main.java
public class Main {
	public static void main(String[] args) {
		// Standard way of doing it.
		// With this, I don't have a fixed ammount of shapes.
		Circle c = new Circle(3);
		Square s = new Square(4);

		// Design-Pattern way using a Factory
		Square sBig = ShapeFactory.createBigSquare();
		Square sMedium = ShapeFactory.createMediumSquare();
		Square sSmall = ShapeFactory.createSmallSquare();
		
	}
}
```

#### Abstract Factory

A factory of factories

A parent class for a factoy, that tells me which factory do I need. 

#### Builder Pattern

Create a complex object through simple objects.

This can be seen in the **Amazon Connect SDK**.

#### Prototype

Copy existing objects without making the code dependent of the classes.

Have an object to be copied.

This can be thought of as the DTO-Entity relation. The **DTO** is the prototype.

#### Singleton

The **most common** of them all.

A shared **instance** by all the project.

```java
// Calculator.java
public class Calculator {
	
	public double sum (double x, double y) {
		return x + y;
	}
}

public class CalculatorSingleton {
	private Calculator instance;
	
	public static Calculator getInstance() {
		if (instance == null) {
			instance == new Calculator();
		}

		return instance;
	}
}

// Service.java
public class Service {
	public double sumInts(int x, int y) {
		// This is another calculator (2)
		Calculator c = new Calculator();
		return c.sum(x, y);
	}
	
	public double sumIntsCorrect(int x, int y) {
		Calculator c = new CalculatorSingleton.getInstance();
		return c.sum(x, y);
	}
}

// Main.java
public class Main {
	public static void main(String[] args) {
		// This is one calculator (1)
		Calculator c = new Calculator();
		System.out.println(c.sum(1, 2));

		// This is the correct way.
		Calculator c = new CalculatorSingleton.getInstance();
		System.out.println(c.sum(1, 2));
	}
}
```

#### Facade

Connect to **not compatible** interfaces

Examples can be:
- DTO.
- API.

## Interfaz vs. Abstract Class

### Interfaz
- Solo puede tener métodos abstractos.
- Ayuda a **forzar u obligar** a otra clase a implementar esos métodos.
- No se puede instanciar.
- Interfaz: Una capa que le permite a dos **entes hablar**.
- Se **implementa**.

### Clase Abstracta
- Puede tener métodos concretos.
- Por ello puede tener atributos.
- Pero no puede ser instanciada.
- Se **hereda**.






