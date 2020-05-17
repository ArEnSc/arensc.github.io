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

OOP is a terrible paradigm, stop using inheritance it’s bad practice, is something that you will hear around on the internet and through some idealogues. Yes that was clickbait.

Is inheritance a bad design decision?  

Not so if you know how to design, and how to calculate change distance and complexity arising from the choice of using inheritance.

TL;DR 
This article is about reframing the way we think about our code by applying graphs to the code that allow you to see a latent structure, where in you can make design decisions. 

We know that the rule of thumb with inheritance, is one or two levels of inheritance is often enough, if your parent class model shares a lot of common variables or functionality that you plan to extend or use in your child you should consider subclassing to keep the code DRY. Anymore than that you should consider the reprocussions.

So in this tutorial I am going to explain a way to measure inheritance complexity introduced in inheritance to measure the complexity of change. This will allow you to make an informed decision. This technique can be applied to all of software architecture.

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

More over many other combinations when we speak from the perspective of other objects, but here we just take a look at A. 

Previously we discussed depth distance from A to D, how about the breath ?
or how about we just subclass from A?  

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

Here the distance between A and CBD is 1, but the width or breadth of A is 3 does that have an impact in change? if so whos perspective ? now lets cut into this a bit deeper. (Excercise left to the reader after completing the article)

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

If we take a look at the graph, we know that we have to change 4 functions 1 variable and have them behave in their original manner. 

If we were to want to remove A completely. 
The change distance on this artifical design is quite high. 
This is due to the potiential dependencies created by inheritance. 

When we design using inheritance we should take this into consideration. 

When we design we should consider that there is an extra dimension time and how other people would interact with your design.

That is over time people can extend upon your work making it unlikely you can easily change the base implementation without a lot of maintence.

![Figure](/assets/img/graph.jpg)

Unmistakably we would do this with deprecation.

Note: I didn't cover the specfics of having a public variable and how that would also add to the complexity.

Note On Example
Also If we were to change remove A and change the Hello(), in the examples they are functions that are used in the children and don't do anything so to change then isn't a huge issue, but the point is statically those changes must be made 



