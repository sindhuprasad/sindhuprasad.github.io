---
layout: post
title: What I learnt about Object Oriented (OO) programming in Java?
---

Three concepts central to OOP are encapsulation, inheritance and polymorphism. When I was beginner to OO, I thought I would use all these equally while coding. However, I used encapsulation and polymorphism more often than inheritance. 

**Encapsulation:**

Encapsulation is basically hiding data and provide behaviours around it. For example,
lets say I am designing a Triangle class,

```Java
class Triangle {
	private double height, base;

	public Triangle(double height, dobule base){
		this.height = height;
		this.base = height;
	}

	public double area() {
		return 1/2 * base * height;
	}
}
```


Notice how I have not exposed height and base fields of Triangle through getters and setters. Because, the code that uses the above triangle object needs the height and base fields only to calculate the area. That behavior can easily be provided by the triangle class itself through the area method. This is encapsulation.

**Polymorphism:**

Polymorphism is ability to take many forms. When different methods of a class have same name but different signatures, its compile time polymorphism. Another flavor is the runtime polymorphism. Here is an example to demonstrate run-time polymorphism,

```Java
class Person {
	int age, height;
	...
}

class AgeComparator implements Comparator<Person> {
	@override 
	 public int compare(Person a, Person b) {
        return a.age > b.age ? 1 : (a.age == b.age) ? 0 : -1;
    }
}

class HeightComparator implements Comparator<Person> {
	@override 
	 public int compare(Person a, Person b) {
        return a.height > b.height ? 1 : (a.height == b.height) ? 0 : -1;
    }
}

//people is a Collection of People objects

Collections.sort(people, new AgeComparator());

Collections.sort(people, new HeightComparator());
```

Notice, how the sort method of collection uses the compare method for internal sorting. The actual object whose compare method is called is resolved at runtime i.e The sort method in Collector does not know the exact object whose compare method is called until runtime.

**Inheritance:**

Inheritance allows a class to inherit state and behavior from another class. 
```Java
class Smartphone extends Phone {
	...
}
```
Java does not allow multiple inheritance, i.e a class cannot extend from multiple classes. Avoid inheritance unless really needed. Take the following example,

```Java
class Rectangle {
	int height, width;
	...
}
```

If I have to design a Square class using Rectangle, I don't need to extend the Rectangle class as shown below,

```Java
class Square extends Rectangle{
	
}
```

Instead, the Square object can easily be created using Rectangle class by avoiding inheritance. 

```Java
class Rectangle {
	public Rectangle(int height, int width){
		..
	}

	...
	Rectangle createSquare(int length){
		return new Rectangle(length, length);
	}
	
	boolean isSquare() {
	  return this.height == this.base;
	}
}
```
