## Starting Up

Imagine, at the startup you are working for, you are in charge of building screens alongside multiple developers. Each screen is assigned to each developer. This is great - it's simple, connecting the screen you are working on to your navigation system, easy peasy. There is always going to be some friction to do so, but the friction involved is so tiny it never mattered. 

## Scaling Up

Now things have changed - you are on a team and you are in charge of a set of screens that capture your team's domain. 
(Domain being area of expertise and business vertical)

Worse yet, you have 5 developers or more and you have to communicate with them since this deals with the details of your domain, no longer just screens and UI. 
Everyone on the team is of different background and cultures and communicates differently.

You just want to program, not communicate. 
These techniques should reduce lack of alignment on designs which cost time and interrupts.

This is the problem when you start to scale up.

## Potential Solution

Through First Principles Thinking, we communicate using a Software domain language.

Teams are more successful when they are on the same page. 
To do this, you must have a common language in which you speak. 

We are going to focus on software semantics in UI frameworks.
More specifically, Software Semantics using Types/Interfaces (protocols) and Data Structures.

Let's be more specific and talk about some examples, build a language using those examples,
then start classifying things and agree on a language we can communicate with.

## Part 1: How to Communicate  

Relative to the class declaration what is the difference between these functions?

The problem here is the idea of a function is `not explicit`, because of semantics.

```swift
class ListViewController: UIViewController, 
                          UIScrollViewDelegate, 
                          UITableViewDelegate {

    // Pushes a stream of events
    func scrollViewDidScroll(_ scrollView: UIScrollView) {
        print("Did Scroll")
    }

    // Pushes a single event
    func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        self.downloadVideo(indexPath: indexPath)
    }

    // Pushes a single value and Pulls a single value
    func tableView(_ tableView: UITableView, heightForFooterInSection section: Int) -> CGFloat {
        return 100;
    }

    // Transforms a single event into chain of events
    func downloadVideo(indexPath:IndexPath) {
        print("Downloading Video")

        print("Read from the network (pull data)")

        print("Write to disk (push data to disk)")
    }
}
```

Functions can model and represent pretty much anything. While that is great for expressiveness, there is an underlying implication that newer developers forget to factor in when designing and communicating software designs.

`IN A UI EVENT LOOP FRAMEWORK`, functions can represent a flow of events over a time domain. 

We `COMBINE` and transform those events to create state, forming an implicit state machine.

This is where the idea that software engineering `is plumbing` comes from. 
We have to reframe these functions not for what they are in their `textual representation`, but what they represent and model - the `SEMANTICS`. 


The way we communicate about functions is as follows: 

```
Category - Event Function ... More to come
Behavior - Push or Pull and Push / Pull
Expectation - Stream of Events or Single Event
Type - What are we returning to the Puller? (caller) or what types are being pushed by the pusher 
```

## Isn't this just RX? 
This might sound RX-like and you are right. The RX framework tries `explicitly` to model these concepts using a framework. These concepts, however... `these concepts exist independent` of RX. 

## Event Functions - A Bit More Depth

These functions are a part of a category of event functions. 
Event Functions have two types: 

```
* User Interface / Framework initiated UI Events
* System Initiated Events
```

Let's give `Event Functions` a color like purple, in your mind. This is useful for finding patterns. 

Event functions are `special` and allowed to do multiple things since they are a fundamental building block on which you build functionality. Should you put a bunch of code in that event function? Probably not... you should try and decouple the events from the business logic, however. 

This is usually done through a viewModel, which is basically an implicit state machine, with a `binding` back to the ViewController (view).

The functions you write will be built on top of event functions.

Let's draw and visualize everything we have done so far.

-> Insert visualization here

## Theory to Practice:
From this, we are going to introduce a way using this language to design and build a screen that has a list with 5 people that you can download and `play songs` from. Here we will continue to build upon the ideas of Event Functions with different classes of functions.

