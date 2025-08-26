---
layout: post 
title: Code Bites - Object-Oriented Shell Functional Core Pure Functions and Impure Functions.
tags: [Swift, OOP, Functional Programming]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

Object-Oriented Shell Functional Core Part 1
Revenge of the pure functions.

<!--more-->
Object-Oriented Shell Functional Core is a set of techniques that combine my experiences programming in Haskell and programming in OOP languages that give us the best of both worlds in developing SCRUD Apps.

We will discuss Pure and Impure Functions

Some definitions first before we begin.

There are 3 types of States in an Application.
 
Global state, a variable that the whole application can read and write

Object state, member variables, that the members of the object can read and write, or even the callers can access depending on scope accessibility. I.e., public/private

Persisted state, state that you have persisted in an embedded database or database. e.g.,
CoreData

There are two types of side effects: 

Static side effects: When you remove an object member in say a singleton and you compile it and your editor shows you what it broke.

Runtime side effects:
These are a bit more complex, as they require a graphical example to explain. A runtime side effect occurs when a variable is changed by some function while in a running state. When we later read the variable, it was unintentionally changed, resulting in a bug. 

Story Time:

In this code bite, we are going to discuss how to manage object state through immutability and by using pure functions through two specific types of functions: member functions and free functions to reduce cognitive load.

What is a pure function? In an object-oriented programming context, it is a function that does not modify self, and/or its inputs are immutable. In general, it's a function that does not create runtime side effects through write operations. The function also must produce a value from the function via return in the sync case. In the async case, the mechanism to return a value can be via either a callback, a thenable promise-like mechanism, a parallel in TouchBistro's case, or a flatMappable observable in the Rx case.

Why should we have pure functions in our codebase? 
Pure functions are functions that are deterministic, meaning they are easy to test. They make guarantees that they do not change the state at the scope they are used in. They guarantee that there is no read-write relationship between the function scope and the rest of the object or even the object variables entering the function. 

This gives you peace of mind that if we were to remove that function, there wouldn't be a side effect of doing so, other than breaking the chain of functions. If you use the function, there isn't an impact or side effect of doing so.

Thus reducing the cognitive load of maintenance and reading of the code. That is, you do not need to trace the rest of the code to determine what this function can do to the system.

Can every function be pure then? No, not all functions are pure, especially in SCRUD application programming. The idea in SCRUD applications that are largely based on OOP paradigms is that we manage the state through chaining functions async or sync, through implementation patterns, through an object-oriented interface.  

All in all, at the end of the chain we have to present the computation, which is storing state in one of the 3 ways above. Meaning that if there are pure functions, there are impure functions alongside them. 

E.g., we have a member variable representing a list of tasks. If we remove a task from the task list by deleting that task using a function, the function is considered impure.

We will discuss implementation patterns through object-oriented interfaces and chaining in another code bite.

// Pure Free Function: A free function cannot reference self, therefore cannot modify the state of the object, but can it modify its input and cause a runtime side effect? 

```swift
let a = AReferenceType()
 
var b = ValueType()
 
func AFreePureFunction(a:AReferenceType, b:ValueType) {
    a.int = 1
    print("Change and cause Side Effect \(a.int)")
 
    var b = b
    b.int = 1
}
 
AFreePureFunction(a: a, b: b)
print("Side Effect A => int: \(a.int)")
print("Side Effect B => int: \(b.int)")
 
// notice how a was changed in the outer scope but b wasn't
// this has to do with the fact that structs are immutable in that scope.1
```

Yes, reference types can have side effects even if you use a free function. 
What if the reference type contains a value you need for a computation? Make sure that the input is immutable in this case or pass a copy of the input to the function. Look up types that are immutable in Swift for more details, as this is out of scope of the tutorial.

How about class member functions? 

// Class Member Pure Function
```swift

class B: UIViewController {
    var aValue:Int = 0
 
    override func viewDidLoad() {
        super.viewDidLoad()
 
        let newValue = memberPureFunctionThatAddsOne(a:self.aValue)
        print(newValue) // use to update the UI ? use to update a
    }
 
    // Do not reference self here
    func memberPureFunctionThatAddsOne(a:Int) -> String {
        let a = a + 1
        return "\(a)"
    }
}


```

Why is it that a pure function can reduce complexity of the code? In graph theory, when you represent the code as a graph of relationships where read and write are edges to variables that contain state, the pure function only writes/reads values internal to its scope. It produces values and never writes those values to the system. 

If it does that, then we can guarantee that it wouldn't modify the state of the system. It's as simple as that. 

What about structs and functions on structs? Well, that's an exercise left to you. Is this an appropriate solution for some cases? 

Impure Functions:
Any function that does not return a value or writes to the 3 state types above is an impure function. They always exist in the system - all iOS applications require that you manipulate a collection of objects, e.g., a list of objects. That function that you write to perform that operation is impure, assuming you have a list in an object. It will have to modify self to write or change that list. I.e., self.list.deleteAt(i)


