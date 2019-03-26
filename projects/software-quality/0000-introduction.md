> The Way that can be followed is not the timeless Way.
>
> —_Daodejing_

# Introduction

We programmers often think of our field as an ever-changing
one. But the fact is, the fundamentals of programming—the
semantics of the languages we use, the types of applications
we write—have experienced no revolutions in the last fifty
years.

Lisp, the forerunner of modern functional languages like
Clojure, appeared on the scene in 1958.

Development on Smalltalk, widely considered the precursor of
modern dynamic object-oriented languages like Ruby, began in
the early 1970s.

Perhaps these aren't the languages we want, but they seem to
be close to the best we can come up with. Can we learn to
live with them? Can we make working with them joyful? Can
we, in a word, make them home?

I think we can. And more than that: we can make them
beautiful.

There exists, hidden amidst the technological churn of our
era, a way of programming that is timeless. To discover that
way is the mission of this book.

Imagine, right now, the most wonderful code you can: code
that succinctly communicates your understanding of some
tricky problem; that is as simple as it can be and as
efficient as it needs to be; that makes plain by its
simplicity that it harbors no bugs. Code that is a joy to
change and test and run.

We all want to write code like this, but most of us don't
know how.

Yet all of us have, at some point, created code that has
this amazing quality, seemingly by accident. The quality
emerges when we forget ourselves, when we are working
quickly and yet paying such close attention to the work that
the world around us disappears. Then, when we step back from
the code, we blink in astonishment at what we've created. We
try to piece together how we did it, but the moment is gone.
We can't remember.

Indeed, when we look at the code afterwards it seems to us
that we could not have designed it, because we do not know
how to design code like that. Nevertheless, it seems to have
been designed. Whether the code grew from the seed of its
own nature, or was dictated to us by a muse, we can't tell.

Here is an example of some code I wrote that I have no idea
*how* I wrote. The `apply` function "updates" a value nested
deep in some immutable object, by constructing a new object
with copies of each sub-object that needs to change.

```javascript
let revise = (draft, key, value) => {
  let copy = shallowCopy(draft)
  copy[key] = value
  return copy
}

let apply = (subject, path, transform) =>
  empty(path)?
    transform(subject)
  : revise(
      subject,
      head(path),
      apply(subject[head(path)], tail(path), transform))
```

Don't feel bad if you don't understand this code. I feel I
don't really understand it myself. If I look at it closely I
can convince myself it is correct, but if you asked me to
explain in English how it works, I'd likely just go through
the algorithm line by line, saying words that are already in
the code. I cannot explain it better than it explains
itself.

Here's a longer fragment, from the heart of a web UI
framework I wrote: a pair of mutually recursive methods,
`run` and `runOrThrow`, that step through a routine that the
user of the framework has plugged in.

```
  function run(returnFromYield) {
    handleErrors(() => runOrThrow(returnFromYield))
  }

  function handleErrors(mightFail) {
    if (error) return
    try {
      error = null
      mightFail()
    } catch (e) {
      error = e
    }
  }

  function runOrThrow(returnFromYield) {
    if (gotosThisTurn > 1000) throw new Error('Infinite retry loop detected')

    if (!stack.length) return
    let {value: effect, done} = lastOf(stack).next(returnFromYield)

    if (done) {
      pop()
      run(effect)
      return
    }

    // ...

    switch (effect.effectType) {
      case 'perform':
      store.emit(effect.action)
      run(store.getState())
      return

      case 'waitForEvent':
      gotosThisTurn = 0
      return

      // ...

      case 'retry':
      gotosThisTurn++
      pop()
      push(effect.generator)
      run()
      return

      // ...

      default:
      error = new Error('You `yield`ed something weird: ' + JSON.stringify(effect))
      return
    }
  }
```

Both of these examples were created using test-driven
development. The experience of working on them was that I
had only to sketch the interface and write the first test;
the implementation blossomed out from each subsequent test I
wrote, as if under its own internal power, like a drop of
dye spreading and blossoming in water.

I'm not sure what, if anything, you can get out of
out-of-context code fragments like this. My main point is to
demonstrate that I have really had this strange experience,
of discovering myself writing code that I don't know how to
design.

Could the above code examples be cleaned up? Could they be
locally improved? Certainly. Both are from projects on which
I worked alone. They haven't had the benefit of a team of
reviewers compelling me to choose good names and use
consistent indentation. I mean, just look at that ternary
operator in the first example!

But should they be rearchitected? Will I ever throw them out
and rewrite them? I can't imagine it. Above all, these
pieces of code are *useful*. Their overall structure is in
perfect harmony with their purpose. I can imagine using
them, and growing them, slowly, for as long as I am
programming. They are not stylish or elegant. Yet they have
an easy, sleepy kind of grace, like a rough stone wall or
the gnarled roots of a tree. They have this quality, I
think, because I did not design them; I imposed no external
criteria of "goodness" on them. I merely began them, and let
them unfold. Their usefulness comes simply from the fact
that I began well.







Axioms:

- a happy programmer is more valuable than an angsty one
- the code programmers work on can make them happy
- the unit that must be addressed is the team: it is not
  feasible, nor really desirable, to make programmers
  individually happy, in isolation.

## Who is this book for?

This is a book for software teams.

It is a book for *everyone* on the team: product managers,
UX designers, engineers from junior to senior. All can, I
hope, learn something from this book.

If you don't learn anything, I hope you at least see some of
your own thoughts about software represented here, and can
use this book to speak more confidently about them with
other members of your team.

And if, on the other hand, you can't make heads or tails of
this book, ask around: an experienced teammate may be able
to give you their perspective on it.

My hope, more than anything, is that this book becomes a
kind of hearth: a gathering-place, in which teams find
shared understanding of the work they do every day.

## What is this book about?

In a word? *Quality*.

It explores the idea of *code quality*, its close relative
*software quality*, and how both relate to *quality of life*
for the people who make and use software. My thesis is that
all these forms of quality are connected—that they are in
fact just different aspects of the same thing.

Many words have already been spent on the subject of
software quality, so you might wonder why I'm bothering to
add a book of my own to the pile.

The fact is, I don't believe the other writers on software
quality have expressed their ideas clearly enough. I don't
mean to disparage their work by saying this: I've enjoyed
many of their books, blog posts, and videos, and learned a
great deal from them. This book would not be possible
without them.

But in my professional life, I've too often seen their ideas
taken as dogma and misapplied. It doesn't help that the
various philosophies of software quality appear to be
contradictory, and people tend to gravitate toward one camp
or the other. Should we make our code object-oriented, or
functional, or simply procedural? Write integrated tests, or
unit tests? Test first or test after? Outside-in or
bottom-up? These unresolved tensions have created schisms in
our industry, across which we often fail to communicate
empathetically.

What we need now is to unify all of our disparate ideas
about quality. I believe that, against all appearances, such
a unification is possible. What makes it possible is that
all of the apparently conflicting philosophies of quality
are just grasping different parts of the same proverbial
elephant. If we understand the whole, we will understand how
each piece of advice applies in its proper context.

I've heard it said that "everyone thinks their way is the
right way, and everyone is wrong." I disagree: everyone is
*right*, but *only in a particular context*. What creates
the schisms in our philosophy of quality is that we can't
easily see the boundaries of our current context, so we
think the principles we've discovered are universal.

Though this book, too, is only applicable within a certain
context, I think it is a very broad context. You're most
likely to find this book helpful if:

- You develop software in an agile way: you don't know most
  of the requirements in advance, but instead must
  continuously release new versions based on feedback from
  users.
- You use a runtime environment that frees memory for you.
  Some of the advice in this book is applicable to
  languages (like C) that require you to free memory
  yourself, but proceed with caution.
- You use languages with support for all three major
  programming paradigms (procedural, object-oriented, and
  functional). Popular languages in this category include
  Java, JavaScript, Python, Ruby, Go, Scala, Elixir, Kotlin,
  Swift, C#, Rust, and to some extent C++. The advice in
  this book leans on the ability to opportunistically use
  multiple programming paradigms. As I'll show later, any
  language that has both function closures (lambdas) and
  mutable local variables can be used to write
  object-oriented programs, and so almost certainly falls
  within the scope of this book.

## Summary of Contents

The remainder of this book is divided into four sections.

The first section, **Feeling Quality**, relates our concept
of code quality to visions of quality in other fields, in
particular the mysterious "Quality Without a Name" described
by architect Christopher Alexander. It tries to answer the
questions: How does something as seemingly fuzzy and
subjective as quality fit into the hard, mathematical world
of programming? Are there different types of quality, and if
so which ones do we care about? What is code quality good
for? How do we recognize it? And how do we go about trying
to create it?

In the second section, **Seeing Code**, I lay the groundwork
for the more technical parts of the book by explaining how I
visualize the structure of code and manipulate it in my
mind. These habits of thought are, as far as I can tell,
essential for creating the patterns described in the third
section.

You can use the third section, **Shaping Patterns**, to
guide your process of writing code. The intention is not
to provide a set of dogmatic rules, but to give you a set of
sane defaults, or "first things to try". The point of having
these defaults is to free up space in your mind to pay
attention to quality.

The fourth section, **The Process of Repair**, describes the
larger context of the other three: the software development
culture that we must create for the Quality Without a Name
to fully come into being.
