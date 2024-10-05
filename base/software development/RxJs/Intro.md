Reactive Extension(Rx) is a library for composing asynchronous and event-based programs using observable sequence and [[LINQ]] style query operators.

## Example code showing how similar high-order functions can be applied to an array and an observable


Iterable
```
getDataFromLocalMemory()
    .filter (s => s != null)
    .map(s => `${s} transformed`)
    .forEach(s => console.log(`next => ${s}`))
```

Observable
```
getDataFromNetwork()
    .filter (s => s != null)
    .map(s => `${s} transformed`)
    .subscribe(s => console.log(`next => ${s}`))
```

## What is Reactive Programming

Reactive programming is programming with asynchronous data streams. A stream can be used as an input to another one. Even multiple streams can be used as inputs to another stream. You can *merge* two streams. You can *filter* a stream to get another one that has only those events you are interested in

```
--a---b-c---d---X---|->

a, b, c, d are emitted values
X is an error
| is the 'completed' signal
---> is the timeline
```

Stream can emit three different things: a value (of some type), an error, or "completed" signal. Consider that the "completed" takes place, for instance, when current window or view containing that button is closed. We capture theses emitted events only asynchronously, by defining a function that will execute when a value is emmited, another function when an error is emited, and another function when 'completed' is emitted. The "listening" to the stream is called **subscribing**. 
```
 clickStream: ---c----c--c----c------c-->
               vvvvv map(c becomes 1) vvvv
               ---1----1--1----1------1-->
               vvvvvvvvv scan(+) vvvvvvvvv
counterStream: ---1----2--3----4------5-->
```

Reference:
1. [[Node js]]