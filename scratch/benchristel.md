## 2019-02-27: Quality: Surface and Form

Seed: _Zen and the Art of Motorcycle Maintenance_:
- "Quality is not 'just' what you like, it's *what you like*."
- To repair a motorcycle, you need to see it not in terms of physical parts but in terms of underlying form. John sees just the physical parts and gets intimidated; the narrator sees *form* (how the parts interact, what their properties are) and understands how to repair the whole.
- The book describes the "romantic" experience of motorcycles as well as the "classical" experience of repair.

*Classical quality* (how a system works) and *Romantic Quality* (i.e. "what people like") are not opposed; they are actually allied. You can't have one without the other.

Why is a motorcycle "dreamy"? There's clearly something aesthetically appealing there, but the appeal is a direct result of the underlying form. The underlying form, is, in turn, a worthy object of analysis because it supports that aesthetic; it is, in a word, useful. Formal analysis of pure abstractions with no relationship to anything useful is not beautiful (and despite what some mathematicians would like you to believe, math is useful). Beauty that's not supported by form is contrived, "fake", and after some time we can see right through it.

We tend to focus on Romantic Quality as being an attribute only of user interface design. But it's also an attribute of internal interfaces. All interfaces are internal from some perspective and external from other perspectives. They are all subject to human interaction at some point. Thus, this union between the two types of quality occurs not just at the outermost interface of a system but at all layers and in all subcomponents of the system.

We tend to see "users" as sheep that need to be led, not inquisitive, intelligent, compassionate humans. We see them this way because the systems they inhabit have forced them into this sheep-like relationship to software (see the passage after the first quote from _ZAMM_ above) where they don't understand how anything works and can only choose between obedience and rebellion.

The people of the future will need to be creative, empathetic, and ethically astute. AI is coming; computers will be our intelligence. We will need to supply wisdom. (Most of the writing about AI risk can be summarized as "AIs are smart, but they're not wise; hence they're dangerous")

We need to create systems that allow people to be this way. The time is now. It is beginning to be possible. Now, more than ever, it is necessary.

## 2019-02-26: Book Titles Etc.

Title: _Priorities_

All engineering challenges are optimization problems.
You have a bunch of different resources: money, computer time, human time,
customer goodwill, technical quality. Many of these are difficult to quantify.
The exchange rates fluctuate constantly. Somehow you must make sense of this chaos
and build something that gives you more resources than you put in.

You can start by prioritizing these resources by value. You want to exchange
less valuable resources for more valuable ones.

You probably undervalue unquantifiable resources—I know I do. (how can you tell, though?)

## 2019-02-20: Outline of a Possible Book

### Introduction

- Known flaws in this book
  - Imperfect metaphors
  - Approaching knowledge through intuition and testing
  - Limits on language
- What is computing?
  - Computation, storage, communication, sensing, signaling
- How do we create software now?
  - XP/"Agile"
  - 3X?
  - Data-driven
  - Lean
  - AI
- Why is change needed?
  - The universe appears absurd from the perspective of the combination of Cartesian dualism + science
    that characterizes post-Enlightenment thought.
  - We think of ourselves as rational beings in a universe of dead matter. This view
    will soon destroy both our environment and our humanity, unless we change it
  - Software engineering is in the eye of the storm. Software is everywhere. If we change, we
    can change the whole of human civilization.
- What is humanizing software?
  - A pattern language (?)
  - A timeless way of programming (?!)
    - Quotes from C.A. to demonstrate parallels
  - Empirical software development
- Why pattern languages?
  - The importance of shared language and vision
- Who can benefit from humanizing software?

### Knitting Computers with Space

- Our pattern languages must begin where C.A.'s end
- Computer systems must interface with physical space
  (not separate, nor entirely suffused) for the system
  containing both to be whole.
- Office layout
- Team structure
- Communication among teams
- Relationship with users and stakeholders
- What to keep from the XP process
- When is it kinder not to react to user feedback?
  - Embrace hacky workarounds
  - Programs that teach
- Versioning, upgrades, and patches
- Software sites

### Programming as Process

- Visualizing the structure of a program
  - Call graph: "top" = main() or other invocation APIs, "bottom" = leaf nodes
  - Horizontal Layers: domain logic on top, application-agnostic (library) code on bottom
  - Vertical slices of input, processing, output (repeated recursively for input and output slices: c.f. the Cantor set!)
  - Tests as pins
- Embarrassingly Obvious Things To Try
  - Get lots of sleep.
  - Take deep breaths.
  - Say "I don't know" or "I'm confused".
  - Take a break.
  - Tell people you value what they do.
- Where should programmers spend their attention?
- Empirical software development

### A Pattern Language for a Program

- (the pattern language)

### What's Next?

- Humanizing Systems or Human Systems or even Living Systems? A generalization of humanizing software?

## 2019-02-15: Life vs. Quality

What is life, or aliveness, in an artifact or space? Is it opposed to "quality" as we typically think of quality in software?

See: Worse is Better. Gabriel says products with looser quality standards, that are not built to match an image of perfection
imposed from outside, have better survival characteristics. I.e. they are literally more alive, because they are better
suited to their environments and better able to self-propagate, in the way that all really living things are.

Hypothesis: Alive things are (not definitionally, but incidentally) palimpsests, products of iterative growth whose surface
appearances say something about the processes that shaped them.

Offices with acoustic ceiling tile feel less alive, because the tile is imposed arbitrarily on the space and hides the
underlying structural elements that reveal how the building is put together.
