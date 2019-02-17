# Logic-Dependency Boundary

> [benchristel] TODO: This pattern describes much more than the actual Logic-Dependency
> Boundary. Currently, most of what's here is background and context. The meat of this
> pattern should probably be moved to Test-Loving Architecture, which is currently light
> on specifics.

As part of a [test-loving architecture](./test-loving-architecture.md), create
a clearly-defined boundary between domain-logic code and code that
depends on services and state that are outside your control.

The impetus for writing up this pattern came from a conversation with @pgoodwin.

---

**How many times have you looked at code and wondered if it would touch the database if you ran it?**

In many applications, it's hard to run any piece of code outside its original context without causing
unintended side effects. You look at a class and wonder if you can test it without starting up the database.
You find a code snippet that looks like it will compute some statistics you need and wonder if
you can safely invoke it on the production server (this is common in dynamic languages like Ruby)
without sending emails to all your customers.

Over time, you can learn to "see" when code is going to have nasty side effects like this.
When I read code in an imperative language, I automatically and subconciously assign each piece of it to
one of four categories:

1. **Pure functions** take immutable values as parameters, perform some computation, and return immutable values.
   They are easy to test and understand because, given some parameters, they always return the same value.
2. **Stateful objects** receive messages from the outside world, change their internal state in
   response, and (usually) return a value. The values returned can be different each time, depending on the state.
3. **Mutators** take in stateful objects and send messages to them. They may be simple routines, or
   they may be objects that store references to their "collaborator" objects.
4. **Side-effecting code** does everything else. It communicates with databases. It talks to the network.
   It starts threads and forks off child processes. It reads and writes files. It pokes pixels in the
   graphics buffer.

These are arranged in order from easiest to test (1) to hardest to test (4). 

The first three of these types of code can be composed in a great variety of ways.

- A pure function can of course simply call other pure functions
  to do its computation, but it can also create a stateful object, send some messages to it, construct
  an immutable return value from the responses, and throw the object away.
- A stateful object can create other stateful objects and send messages to them, and of course it can call pure functions.
- Mutators can be thought of as just convenience wrappers for sending a series of messages,
  so they can be used by any of the other types of code too.

Type 4 code is different, though. *Type 4 is a virus*. It is transitive. Everything
that calls Type 4 code—*everything*—becomes Type 4 as well.

That means that if you're not careful, Type 4 code can quickly become the dominant species in your codebase,
and once it is rooted it is *very* hard to remove.

In many codebases, most of the code is type 4. *This type of codebase is very difficult to test and understand.*

**Limit the spread of side-effecting code by marking a clear division between types 1-3 ("logic" code) and Type 4 code
("dependency" code). Create a narrow ribbon of "boundary" code near the root of the call stack to unite the logic and dependency
sides.**

The logic-dependency boundary can take the form of an imperative procedure that might look something like this:

```javascript
doWorkflowFoo() {
  // expressions marked with * are calls to "dependency" code
  data = *loadData()
  plan = planOperation(data)
  answer = *askUserToConfirm(plan)
  if (isAffirmative(answer)) {
    result = computeResult(plan, data)
    *writeResult(result)
    *logSuccess(plan)
  } else {
    *logFailure(plan)
  }
}
```

The above example depicts what a logic-dependency boundary might look like for a CLI. In a game or interactive web UI,
you might see something more like this:

```javascript
eventLoop() {
  state = initialState()
  while (!exited(state)) {
    event = *waitForAny(timerTickStream, uiEventStream, keyEventStream)
    state = nextState(state, event)
    ui = renderUiDom(state)
    *draw(ui)
  }
}
```

All of the logic of the application is contained in the `nextState` and `renderUiDom` functions.

[redux-saga](https://github.com/redux-saga/redux-saga) is a library that makes it easier to implement this pattern for web UIs.

On the server side of a web application, the logic-dependency boundary might look like this for a single endpoint's controller:

```javascript
handleProfilePageRequest(request) {
  params = extractParams(request)
  data = *loadProfilePageData(params)
  dom = renderProfilePage(data)
  ui = toMarkup(dom)
  *sendResponse(ui)
}
```

Note that all of these examples are oversimplified. In particular, the names are meant to be illustrative, not exemplary.

## Caveats

One complicating factor is that, in OO languages,
code types 2 through 4 often look the same from the outside. If all you can see is the interface of a class,
you can't really tell if it's storing state, calling methods on other objects that you pass it, or affecting the
outside world.

Type 3 code is especially difficult to distinguish from Type 4. Even when you can see the internals of
a class, it is hard to tell the difference. Consider the following sketch of a class implementation:

```java
class Type3Maybe {
  A a; B b;
  public Type3Maybe(A a, B b) {
    this.a = a;
    this.b = b;
  }
  
  public void foo() {
    a.foo();
    b.bar();
  }
}
```

If `A.foo()` and `B.bar()` are type 2 or 3, `Type3Maybe.foo()` is type 3.
But if either `A.foo()` or `B.bar()` is type 4, `Type3Maybe.foo()` is also type 4.
If `A` and `B` are interfaces, the confusion gets worse; they may have some
implementations that are type 2 and some that are type 4, so the classification of
`Type3Maybe` depends on what arguments are passed to its constructor at runtime.

Since the type system cannot help us figure out how to classify our code in cases like
this, we must rely on informal contracts between units of code to understand what
`Type3Maybe` is going to do.

These informal contracts can be quite subtle, and can blur the boundaries between
the four types of code. This can be a good thing. The way we think about our code is
almost always subtler than our formal systems can express.

Here is an example in pseudocode in which the distinction between type 3 and type 4 is blurred:

```java
namespace Subscription {
class StatsCollector {
  public static Stats collect(Stream<Subscription> subs) {
    Stats stats = new Stats()
    while (subs.hasNext()) {
      Sub sub = subs.next()
      if (sub.isPaid()) stats.paid++
      if (sub.isCanceled()) stats.canceled++
      if (sub.isActive()) stats.active++
    }
    return stats
  }
}
}
```

Is this code type 3 or type 4? It depends on the implementation of `Stream<Subscription>` passed in.
The stream could be a simple in-memory data structure, which would make `StatsCollector` type 3.
But it could also read from a file or database as we iterate over it,
which would seem to make `StatsCollector` type 4.

And yet, this ambiguity causes us little worry. Why?

One reason is that we trust that while a `Stream` may receive input from the outside world (e.g.
from a file or database), it doesn't alter the outside world in any important way. We trust
that reading the Stream won't cause other things to happen.

Another reason is that, whether the Stream is in-memory or reading lazily from a file, its
input must have come from *somewhere*. It must have been passed to us from Type 4 code whose
purpose is reading input. If the Stream is lazily reading a file, that's okay, because
the code that created it has already "taken responsibility" in some sense for the file read.
Whether the data was loaded into memory eagerly when the Stream was constructed, or will be
loaded lazily when we call `hasNext`, is not our concern.

Depending on the application, the level of abstraction provided by interfaces like `Stream`
can be very powerful.

One danger lingers when the Stream is loaded lazily: it is possible that there will be an
error when it tries to read its input. In that case, it could either throw an exception, or
simply signal the end of the stream. But somehow, the error must be handled. The complexity 
added by the potential for errors is a strong reason not to hide side effects behind interfaces like the Stream,
if you can avoid it.

It's possible that Type 4 code should be broken down into two subtypes: 4.1 **Input** and 4.2
**Output**. In many cases, we do not care when, exactly, our code reads input from the outside
world. Input routines are thus relatively safe to hide behind abstractions like the `Stream` in the
above example.

**Output**, on the other hand, is a different story. The order in which our code outputs data
or affects the world is often crucially important. Therefore, output routines must be explicit
about the fact that they are affecting the outside world.

## Examples

- In his talk ["Boundaries"](https://www.youtube.com/watch?v=yTkzNHF6rMs),
  Gary Bernhardt describes how he separated logic from dependencies in his
  Twitter client `toot`.
- In [Verse](https://benchristel.github.io/verse), the [sagas](https://github.com/benchristel/verse/blob/master/src/ui/sagas/index.js) form the main logic-dependency boundary.
  All interaction between the "dependency" code (the keyboard, time, and storage modules) and the "logic" code
  (the running Process, the test framework, and the view) is mediated by the sagas.

---

Logic and side-effecting code can peacefully inhabit the same object—see [Value Objects With Polymorphic Effects](value-objects-with-polymorphic-effects.md). Isolate your logic code from changes to third-party APIs by putting an [Anti-Corruption Layer](https://medium.com/continuousdelivery/anti-corruption-layer-e24e2025be6f) around your dependency code.
