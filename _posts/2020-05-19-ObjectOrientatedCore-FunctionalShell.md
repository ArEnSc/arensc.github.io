---
layout: post 
title: Object-Oriented Shell, Functional Core - Managing State in Modern Applications
tags: [Swift, OOP, Functional Programming]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

Combining the best of object-oriented and functional programming paradigms to build maintainable SCRUD applications.

<!--more-->

## Introduction

Object-Oriented Shell, Functional Core (OSFC) represents a powerful architectural pattern that emerged from my experience with both Haskell's pure functional approach and the pragmatic realities of OOP languages. This technique offers a compelling solution for managing complexity in modern SCRUD (Search, Create, Read, Update, Delete) applications.

The core principle is elegantly simple: encapsulate side effects within an object-oriented shell while keeping business logic pure and functional at its core. This separation yields code that's both testable and maintainable.

## Understanding State in Applications

Before diving into pure and impure functions, let's establish a clear taxonomy of state in applications:

### 1. Global State
Variables accessible throughout the entire application for both reading and writing. While powerful, global state introduces coupling and makes reasoning about code flow challenging.

### 2. Object State
Member variables confined within object boundaries. Access control (public/private) determines visibility, providing encapsulation while maintaining flexibility.

### 3. Persisted State
Data stored in databases or file systems (e.g., CoreData, SQLite). This state survives application restarts and requires careful synchronization with in-memory representations.

## The Two Faces of Side Effects

Understanding side effects is crucial for applying OSFC effectively:

### Static Side Effects
These manifest at compile time. Remove a singleton's method, and your IDE immediately highlights every broken reference. While disruptive, static side effects are predictable and manageable.

### Runtime Side Effects
Far more insidious, runtime side effects emerge during execution. A function modifies a shared variable, another function reads it later expecting the original value—suddenly, you're debugging seemingly impossible behavior. These effects compound exponentially as systems grow.

## Pure Functions: The Functional Core

### Definition
In object-oriented contexts, a pure function exhibits three key characteristics:
1. **No self modification** - It doesn't alter the object's state
2. **Immutable inputs** - Parameters remain unchanged
3. **Deterministic output** - Always returns a value (synchronously or asynchronously)

For asynchronous operations, the return mechanism might involve callbacks, promises, observables (Rx), or other async patterns—but the principle remains: predictable input-output relationships.

### Why Pure Functions Matter

Pure functions offer compelling benefits:

- **Testability**: Deterministic behavior makes unit testing straightforward
- **Composability**: Chain pure functions without fear of hidden interactions
- **Reasoning**: Understand functions in isolation without tracing global effects
- **Refactoring**: Remove or relocate pure functions safely

This dramatically reduces cognitive load. When reading pure functions, you need only understand their inputs and outputs—not the entire system state.

## The Reality of Impure Functions

Despite their benefits, pure functions alone cannot build complete applications. SCRUD operations inherently require state mutation—updating databases, modifying UI, handling user input. This is where the object-oriented shell comes in.

Consider this practical example:

```swift
class TaskManager {
    private var tasks: [Task] = []
    
    // Impure: Modifies object state
    func deleteTask(at index: Int) {
        tasks.remove(at: index)
        persistTasks() // Side effect: Database write
    }
    
    // Pure: Returns new array without modifying state
    func tasksFiltered(by status: TaskStatus) -> [Task] {
        return tasks.filter { $0.status == status }
    }
}
```

## Practical Implementation in Swift

Let's examine how Swift's type system helps enforce these patterns:

### Free Functions and Side Effects

```swift
class Account {
    var balance: Int = 0
}

struct Transaction {
    let amount: Int
}

// This appears pure but isn't—reference types allow mutation
func processTransaction(account: Account, transaction: Transaction) {
    account.balance += transaction.amount // Side effect!
}

// Truly pure version returns new state
func calculateNewBalance(currentBalance: Int, transaction: Transaction) -> Int {
    return currentBalance + transaction.amount
}
```

Key insight: Swift's value types (structs) naturally encourage pure functions, while reference types (classes) require discipline to avoid unintended mutations.

### Member Functions in Classes

```swift
class BankAccount {
    private var balance: Int = 0
    
    // Pure member function - doesn't reference self's mutable state
    func calculateInterest(principal: Int, rate: Double) -> Int {
        return Int(Double(principal) * rate)
    }
    
    // Impure - modifies state
    func applyInterest(rate: Double) {
        let interest = calculateInterest(principal: balance, rate: rate)
        balance += interest
    }
}
```

## The Graph Theory Perspective

Viewing code through graph theory illuminates why pure functions reduce complexity:

- **Nodes**: Variables and state
- **Edges**: Read/write relationships
- **Pure functions**: Isolated subgraphs with no outgoing edges

Pure functions create localized computation graphs disconnected from the larger system state graph. This isolation is what makes them so powerful—changes propagate predictably within boundaries.

## Best Practices for OSFC

1. **Identify boundaries**: Clearly separate pure business logic from stateful coordination
2. **Push effects outward**: Keep side effects at the system's edges
3. **Leverage type systems**: Use Swift's structs for data, classes for coordination
4. **Test the core**: Focus testing efforts on pure functions
5. **Document effects**: When functions must be impure, clearly document their side effects

## Conclusion

Object-Oriented Shell, Functional Core isn't about choosing sides in the OOP vs. FP debate. It's about leveraging each paradigm's strengths: OOP's encapsulation for managing effects and FP's purity for expressing logic.

In your next project, try identifying one complex business rule and extracting it into pure functions. You'll likely find the resulting code more testable, readable, and maintainable. The journey toward better architecture begins with a single pure function.

*Next in this series: We'll explore advanced patterns for chaining pure functions and managing asynchronous operations within the OSFC paradigm.*