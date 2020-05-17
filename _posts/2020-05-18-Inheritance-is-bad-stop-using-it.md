---
layout: post 
title: Inheritance is bad don't use it.
tags: [Swift,OOP,Functional Programming]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

OOP and Inhertance the bane of all programming practices.

<!--more-->

OOP is a terrible paradigm, stop using inheritance it’s bad practice, is something that you will hear. Is inheritance a bad design decision?  

Not so if you know how to design, and how to calculate change distance and complexity arising from the choice of using inheritance.

The rule of thumb with inheritance, one level of inheritance is often enough, if your parent class model shares a lot of common variables or functionality that you plan to extend or use in your child you should consider subclassing to keep the code DRY.

So in this tutorial I am going to explain a way to measure inheritance complexity introduced in inheritance to measure the complexity of change when you want to make an informed decision. This technique can be applied to all of software architecture.

This technique uses graph theory to measure distances between objects using edges.

Okay let's write some code inheritance of classes in swift is denoted by classTemplate:<ClassToInheritFrom>

```swift
class A {
}

class B:A {
}

class C:B {
}

class D:C {
}
```

A -> B -> C -> D

The picture we should visualize in this situation is a series of nodes from a graph.

If you don't know what that is here's an article
https://en.wikipedia.org/wiki/Graph_theory

Here we can describe the distance from A using the edges.
The distance from D to A is 3 
The distance from C to A is 2
The distance from B to A is 1

More over many other combinations when we speak from the perspective of other objects, but here let's just look at A. 

Previously we discussed depth distance from A to D, how about the breath? 

```swift

class A {
}

class B:A {
}

class C:A {
}

class D:A {
}

//A -> [C,B,D]

```


Where the distance between A and CBD are one, but the width or breadth of A is 3

Since we are putting the graphical abstraction over OOP code we have a way to measure the change distance if we were to change functions or variables in A’s design. 

How about functions and variables now?

```swift

class A {
  public var someNumber:Int = 0
  public func hello() -> String {
        return ""
  }
}

class B:A {
}

class C:B {
}

class D:C {
}

```


Let's go back to the first example and 
add a variable to class A and a function func Hello() -> String that returns a string

public variable someNumber to A from the static code meta we have effectively just propagated variables and functions from A across all objects related to it.

What does that mean from a graphical perspective ? 

``` swift
class A {
  public var someNumber:Int = 0
  public func hello() -> String {
        return ""
  }
}

class B:A {
	public func useHelloB() {
		hello()
	}
}

class C:B {
	public func useHelloC() {
		hello()
	}
}

class D:C {

	public func useHelloD() {
		hello()
	}

	func useVarC() {
		print(a)
	}
}
```

If we take a look at the graph, we know that we have to change 4 functions 1 variable and have them behave in their original manner. If we were to want to remove A completely. The change distance on this design is quite high. This is due to the dependencies created by inheritance. When we design using inheritance we should take this into consideration. That is over time people can use.


![Figure](assets/img/graph.jpg)

