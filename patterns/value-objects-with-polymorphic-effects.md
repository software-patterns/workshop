# Value Objects with Polymorphic Effects

*TODO: This pattern really really needs a better name. —benchristel*

This pattern tells you how to shape the most fundamental objects in a system: the nouns
in the [Ubiquitous Domain Language](./ubiquitous-domain-language.md)
of the application. These objects operate on both sides of a [Logic-Dependency Boundary](./logic-dependency-boundary.md).

The objects and functions that collaborate with this pattern will be easy to test within a
[300-Millisecond Test Suite](./300-ms-test-suite.md).

The kernel of the idea for this pattern is due to [Gary Bernhardt](https://www.destroyallsoftware.com), who described
something similar in his talk ["Boundaries"](https://www.destroyallsoftware.com/talks/boundaries).

---

**In unit-tested object-oriented systems, there is often a tension between objects that contain
data and objects that have effects on the world.**

To preserve our peace of mind as we operate on data, we want our fundamental data-containing objects to be
[Immutable Values](./immutable-values.md). Immutable values are a Good Idea drawn from functional
programming, but they are also useful in object-oriented systems.

However, when we use immutable values in our code, we tend to fall into a functional-programming-only
mindset that maintains a strict separation between data and code. In the absence of algebraic
datatypes or multiple dispatch with pattern matching—FP features that
OO languages like Java typically lack—this strict separation is harmful. It prevents us from using polymorphism
effectively.

Consider the following immutable value classes in Java:

```java
class SMSMessage {
  public final PhoneNumber sender;
  public final List<PhoneNumber> recipients;
  public final String body;
  
  public SMSMessage(/* ... */) {
    // set all the data fields here
  }
}

class SlackMessage {
  public final SlackUser sender;
  public final SlackChannel recipients;
  public final String body;
  public final List<Attachment> attachments;
  
  public SlackMessage(/* ... */) {
    // set all the data fields here
  }
}
```

Conceptually, both of these classes represent *messages that can be sent*. In a language like Elixir,
we could write a pattern-matching `send` routine that could handle either of these objects.

```elixir
def send(%SMSMessage{} = sms) do
  # ...
end

def send(%SlackMessage{} = msg) do
  # ...
end
```

The compiler can check for us that we never pass a value to `send` that is not handled by one of the implementations.
This is how languages with a strict separation between logic and data can be typesafe.

In Java, however, there is no clean way to do the same thing. Because the `SMSMessage` and `SlackMessage`
classes contain different data—and contain nothing *but* data—we have to use runtime type-checking
to figure out how to send the message.

```java
class MessageSender {
  public static void send(Object message) {
    if (message instanceof SlackMessage) {
      // send a SlackMessage
    } else if (message instanceof SMSMessage) {
      // send an SMSMessage
    } else {
      // we got some type we don't know about; throw an error!
    }
  }
}
```

The compiler will not help us verify that this code is free of type errors.

Therefore:

**Within a class, maintain a strict separation between data and side-effecting code. Make
it possible to use the object as either a pure datatype, or an interface to affect the
outside world.**

Here is a better structure for the message-sending classes outlined above:

```java
interface SendableMessage {
  void send();
}

class SMSMessage implements SendableMessage {
  public final PhoneNumber sender;
  public final List<PhoneNumber> recipients;
  public final String body;
  
  public SMSMessage(/* ... */) {
    // set all the data fields here
  }
  
  public void send() {
    // ...
  }
}

class SlackMessage implements SendableMessage {
  // ...
  
  public void send() {
    // ...
  }
}
```

Now our classes have two "faces": they are both immutable values and containers for polymorphic,
side-effecting routines. Each of these faces can be used on one side of a
[Logic-Dependency Boundary](./logic-dependency-boundary.md). The "logic" code can construct the
value without having any side effects on the outside world. The "dependency" code can invoke the
side effects without caring about the shape of the data inside the object.
The value object itself is the messenger that communicates between these two aspects of the program.

There is one more thing that must be added for the pattern to be completely alive.
Every value object must have a concept of *equivalence* with other members of its type.

The word "equivalent", decomposed into its Latin roots, means literally "same worth".
Any two objects that are *equivalent* contain equal data, and will have the same effect
on the world if their side-effecting methods are invoked. If we have two objects that
are equivalent, it doesn't matter which one we use.

The concept of equivalence becomes important when we want to test the code on the
"logic" side of the [Logic-Dependency Boundary](./logic-dependency-boundary.md).
Following is a sketch of an Email value class written in Ruby, some logic that uses it, and
a test for that logic.

```ruby
# The value class
class Email
  def from=(sender)
    # ...
  end
  
  def to=(recipient)
    # ...
  end
  
  def subject=(line)
    # ...
  end
  
  def body=(text)
    # ...
  end
  
  def send!
    # ...
  end
end

# ...

# The logic
def billing_notification_email(user, subscription)
  email = Email.new
  email.subject = "We've billed your account for #{subscription.price}"
  email.from = "noreply@example.com"
  email.to = # complicated logic goes here...
  email.body = # complicated logic goes here...
  return email
end

# ...

# The test
describe 'billing_notification_email' do
  it 'notifies the user of being billed for a monthly subscription' do
    user = # ...
    subscription = # ...
    email = billing_notification_email(user, subscription)
    expect(email.subject).to eq "We've billed your account for $42.00"
    expect(email.from).to eq "noreply@example.com"
    expect(email.to).to eq # ...
    expect(email.body).to eq # ...
  end
  
  it 'notifies the user of being billed for a yearly subscription' do
    # ...
  end
end
```

Since there is no way to compare two whole email objects for equivalence, we have
to check each field individually. In some circumstances, this may be exactly what
we want. But remember that these objects, because they also have a side-effecting `send!` method,
precisely represent some *effect* that our program will eventually have on the world.
If we want our tests to specify exactly what that effect must be, we need to check all the fields.

How can we be sure our test is checking all the fields? If we add a new field to the class, how can we
be sure we've updated all the tests in which we intended to check all the fields?

The easy, conventional way to do this is to implement the equality operator on our class to compare
all the fields. Ruby makes it particularly easy to do this. Value classes can
just extend a `Struct`.

```ruby
Email = Struct.new(:from, :to, :subject, :body) do
  def send!
    # ...
  end
end
```

Now we can write our test like this:

```ruby
  it 'notifies the user of being billed for a monthly subscription' do
    user = # ...
    subscription = # ...
    expect(billing_notification_email(user, subscription))
      .to eq Email.new("noreply@example.com", "user@foo.bar", "We've billed your account for $42.00", "...")
  end
```

If we later add new fields to the `Email` class, we will see errors that guide us to update the constructor calls
to initialize those fields.

*I am not a big fan of how Ruby uses positional arguments rather than named arguments in Struct constuctors.
I'd rather read code that looks like this:*

```ruby
Email.new(
  from: "noreply@example.com",
  to: "user@foo.bar",
  subject: "We've billed your account for $42.00",
  body: "Dear User, ..."
)
```

*There are libraries out there that let you do just that, e.g. [tcrayford/Values](https://github.com/tcrayford/Values).
You could also write your own quite easily. —benchristel*

---

The [Side-Effecting Method](./side-effecting-method.md) pattern tells you how to form the relationship between
the data and code in a value object.
