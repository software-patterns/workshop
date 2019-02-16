# Logic-Dependency Boundary

As part of a [test-loving architecture](./test-loving-architecture.md), create
a clearly-defined boundary between domain-logic code and code that
depends on services and state that are outside your control.

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
3. **Mutating routines** take stateful objects as parameters and send messages to them.
4. **Side-effecting code** does everything else. It communicates with databases. It talks to the network.
   It starts threads and forks off child processes. It reads and writes files. It pokes pixels in the
   graphics buffer.

These are arranged in order from easiest to test (1) to hardest to test (4). 

The first three of these types of code can be composed in a great variety of ways.

- A pure function can of course simply call other pure functions
  to do its computation, but it can also create a stateful object, send some messages to it, construct
  an immutable return value from the responses, and throw the object away.
- A stateful object can create other stateful objects and send messages to them, and of course it can call pure functions.
- Mutating routines can be thought of as just convenience wrappers for sending a series of messages,
  so they can be used by any of the other types of code too.

Type 4 code is different, though. *Type 4 is a virus*. It is transitive. Everything
that calls Type 4 code—*everything*—becomes Type 4 as well.

That means that if you're not careful, Type 4 code can quickly become the dominant species in your codebase,
and once it is rooted it is *very* hard to remove.

In many codebases, most of the code is type 4. *This type of codebase is very difficult to test and understand.*

**Limit the spread of side-effecting code by marking a clear division between types 1-3 ("logic" code) and Type 4 code
("dependency" code).**

Please don't use Hungarian notation for this, though. I hope and suspect that if everyone on your team has the
four types of code in mind, they won't find it too hard to keep the logic and dependency code separate.

## Examples

- In his talk ["Boundaries"](https://www.youtube.com/watch?v=yTkzNHF6rMs),
  Gary Bernhardt describes how he separated logic from dependencies in his
  Twitter client `toot`.

---

Logic and side-effecting code can peacefully inhabit the same object—see [Value Objects With Polymorphic Effects](value-objects-with-polymorphic-effects.md).
