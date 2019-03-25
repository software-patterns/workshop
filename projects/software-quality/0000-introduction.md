> The Way that can be followed is not the eternal Way.
>
> —Laozi, _Daodejing_.

# Introduction

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
all these forms of quality are connected̈—that they are in
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
