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
doSomethingComplicated()
doSomeSecureOperationWith(session.currentUser());
```

How can we be sure that the user we've authenticated is still the current user when we
`doSomeSecureOperationWith(session.currentUser())`? In general, we can't. It could have
been changed by the call to `doSomethingComplicated`. It might even have been changed
by another thread.

This problem can of course be mitigated by using local variables, e.g.

```java
user = session.currentUser();
authenticate(user);
doSomethingComplicated()
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

### Real Example: Verse View

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

### Simple Example: Mutable Log

The following `Log` class defines mutable objects with two simple operations: `write(message)` and `clear()`.
When you perform one of these operations on a `Log`, it returns the history of messages
written so far as an immutable State Proclamation.

One idiosyncrasy of the Log class is that you can't observe its true initial state.
You have to send it a message, either `write` or `clear`, to access the state.
This is okay because we probably want newly-initialized Logs to be blank, so we
can send `clear` to generate the first proclamation.

You can copy-paste this code into [Verse](https://verse.js.org/2.0.0-alpha.0) to see the tests run.

```javascript
define({
  Log() {
    let messages = []
    return {
      clear,
      write,
    }
    
    function clear() {
      return messages = []
    }
    
    function write(message) {
      return messages = [...messages, message]
    }
  },
  
  'test creating a blank Log'() {
    assert(Log().clear(), equals, [])
  },
  
  'test writing a message to a Log'() {
    assert(Log().write('hello'), equals, ['hello'])
  },
  
  'test writing multiple messages to a Log'() {
    const l = Log()
    l.write('one')
    assert(l.write('two'), equals, ['one', 'two'])
    assert(l.write('three'), equals, ['one', 'two', 'three'])
  },
  
  'test clearing a Log'() {
    const l = Log()
    l.write('hello')
    assert(l.clear(), equals, [])
  },
  
  'test clearing a Log and then writing more messages'() {
    const l = Log()
    l.write('before clear')
    l.clear()
    assert(l.write('after clear'), equals, ['after clear'])
  },
  
  'test writing to a Log does not alter earlier state proclamations'() {
    const l = Log()
    let dontChangeMeBro = l.write('one')
    l.write('two')
    assert(dontChangeMeBro, equals, ['one'])
  },
  
  'test clearing a Log does not alter earlier state proclamations'() {
    const l = Log()
    let dontChangeMeBro = l.write('one')
    l.clear()
    assert(dontChangeMeBro, equals, ['one'])
  }
})
```

---

{References to smaller patterns}
