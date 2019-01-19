# State Proclamation

*TODO: This pattern is in search of a better name.*

The [stateful objects](./state-atoms.md) on the logicward side of a [logic-dependency boundary](./logic-dependency-boundary.md)
convey their internal state to the rest of the program via immutable
messages. This minimizes the risk of state changes causing
[spooky action at a distance](https://en.wikipedia.org/wiki/Action_at_a_distance_(computer_programming)),
while ensuring that all program components that need access to the state can get it.

---

**In every nontrivial program that processes a sequence of inputs over time, there is some mutable state.
But if many parts of the program are allowed to modify or even directly observe this state, the
intelligibility of the program will be compromised.**

When programming with state, we must reconcile two opposing forces. The state is in many
cases the beating heart of the program, the nexus that links incoming data to all the other
components. Therefore, we want to make the state readily accessible. However, we are also
aware of the danger of distant program components corrupting the state or being
corrupted by changes to it. Therefore, we want to restrict access to the state.

The first force—the need to make the state accessible—is by far the most powerful early
on in the life of a program. What happens if we yield to this force?

The most straightforward way to make state available is to
pass around references to the stateful objects. Many editors will even autogenerate getter methods
for accessing objects' internal state. However, following this path of least resistance
leads to serious problems. If anyone with a reference to an object can send it messages that
change its state, we can't be sure that inappropriate changes are not being made to
the state, unless we read the whole program.

We can use [interface segregation](https://en.wikipedia.org/wiki/Interface_segregation_principle) to 
mitigate this. If the stateful object implements a "read only" interface, and is only made available under
the guise of that interface to program components that should have read-only access, the sanctity
of its state can be preserved.

However, the interface segregation technique leaves behind a subtle problem: keeping around references to a
mutable object destroys referential transparency. The following pseudocode illustrates the issue:

```java
// session is a mutable object
authenticate(session.currentUser());
sleep(100);
doSomeSecureOperationWith(session.currentUser());
```

How can we be sure that the user we've authenticated is still the current user when we
`doSomeSecureOperationWith(session.currentUser())`? In general, we can't.

This problem can of course be mitigated by using local variables, e.g.

```java
// session is a mutable object
user = session.currentUser();
authenticate(user);
sleep(100);
doSomeSecureOperationWith(user);
```

But this does nothing to ensure that `user` has the same value as other calls
to `currentUser()` that may exist elsewhere in the program.

Therefore:

**Express the public state of a mutable object as a State Proclamation:
an immutable value type that can be freely passed around a program. Do not
share references to the mutable object; instead, the part of the program
responsible for updating the object's state should distribute State Proclamation
values.**

{Solution description}

## Examples

The [core](https://github.com/benchristel/verse/blob/master/src/core/Core.js) of
[Verse](https://benchristel.github.io/verse) is a small tree of stateful objects
that use State Proclamation to keep the UI informed of their internal state.
Verse calls the State Proclamation type the "view". It looks like this:

```javascript
view = {
    displayLines: [
      'lines printed',
      'on the screen'
    ],
    error: null,      // or an Error, if the program has crashed
    
    syntaxErrors: {}, // maps filenames to Errors
    
    testResults: {},  // maps test names to Errors
    
    form: [],         // the list of form fields displayed on the screen
    
    formId: 0,        // unique ID to ensure that forms are displayed
                      // and processed correctly
  }
```

---

{References to smaller patterns}
