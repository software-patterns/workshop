# The Process of Repair: A Programmer's Manual

## TOC

- part 0: introduction
- part 1: feeling quality
- part 2: seeing code
- part 3: shaping patterns
- part 4: the process of repair

## Introduction

- This is a book for software teams
- Specifically, teams working in a situation where they
  must be agile (requirements not fully known in advance of
  coding and deployment)
- Code is the primary communication mechanism of an agile team
  - must be primary, for work to be efficient
  - lots of knowledge implicit in code that is difficult to
    communicate in email, documentation, or even
    face-to-face conversations.
- Cultural norms of code quality allow the team to
  collaborate effectively, without working at cross purposes.
- Yet code quality does not mean adhering to a list of
  superficial rules about style, cyclomatic complexity, file
  length, etc.
- it is possible to write hard-to-understand, unmaintainable
  code that follows such rules. Indeed, that is the easiest
  way to comply with them.
- in this book, I hope to elucidate what code quality really
  is, and how it affects the collaboration and sense of
  community within a team.
- I will try to demonstrate, as concretely as I can, the way I
  "see" code and manipulate it in my mind, and how these
  habits of thought make quality jump to the fore.
- I will give you concrete techniques, in the form of patterns,
  to make the rote labor of coding easier so you can focus your
  attention on quality.
- And finally, I will present a process in which to apply these
  techniques: one that is general enough to be used by teams of
  any size from one to ten people, and flexible enough to
  accommodate many different preferences and work styles.
- The key to the flexibility of the process is the focus on code
  and code quality as primary communication mechanisms of
  the team.

## Glossary

- *application*: a collection of one or more programs
  intended to do something useful (solve a problem, make
  money, entertain) for the benefit of *stakeholders*.
  Contrast with *program*.
- *program*: an executable file that runs on a computer.
  I also use *program* somewhat loosely to refer to the
  source code for a single executable. Contrast with
  *application*.
- *routine*: a procedure or function: a unit of source code
  that comprises: a scope for variables; an algorithm,
  defined in terms of primitive operations and calls to
  other routines; a set of parameters; and possibly a return
  value.
- *procedure*: a type of routine that may affect the
  outside world and access global state.
- *function*: a type of routine whose only inputs are its
  parameters, which are filled by immutable values, and
  whose only output or effect is to return a value to its
  caller.
- *method*: a type of *routine* that is executed by an
  *object* in response to a *message*, and that typically is
  able to call private methods and refer to private
  variables of that object.

## Feeling Quality

- quote Pirsig's vision of a qualityless world
- in the real world, we can't escape quality, good or bad
- when you finish implementing a feature in your codebase, how will you feel?
  - energized? excited? ready to go on to the next thing?
  - or tired, frustrated, foggy-brained, irritable?
- people think they can "power through" bad quality. They're wrong.
- there's no mind over matter. Minds are matter. Your ability to continue doing
  valuable work after finishing that feature is dependent on how you felt about finishing
  it, whether you want it to be or not.
- misconception that STEM fields are quality-free
- drilled into us in school by the notion that there's a
  "right answer" in math and science, but "no single right
  answer" in Literature and Art.
- some people love the "one right answer" subjects. Those are
  the people who typically become computer programmers.
- but where does the "one right answer" come from?
- science and mathematics do not make progress by rote learning
  of existing right answers. And indeed, the whole concept
  of a "right" answer in math or science is suspect
  - Kuhnian paradigm shifts
  - Non-Euclidean geometry
  - Poincaré
- all this leads us to suspect that there *is* something
  qualitative about math, science, engineering. But what is it? How
  to see it, create it?
- Quality is "a subtle kind of freedom from inner contradictions" (CA)
  - a harmony between the whole and its parts.
- When you look at the painting of a master, you don't see shading,
  lighting, composition. The painter has mastered these techniques
  and can break the rules. The mastery of each part, frees
  the whole; it leaps forth from the canvas. Before we
  even have had time to analyze it, it impresses us.
- And yet, if we look more closely, and with an analytical eye,
  we see tremendous care and skill evident in each part.
- This care is what frees the whole from being a mere
  agglomeration of parts. There is
  nothing distracting, nothing awkward, no superfluous detail,
  and nothing missing either. Each part exists because it
  supports the whole. Because there are no little out-of-place
  details troubling the parts, they do not trouble us: they
  melt away into insignificance. We feel free to ignore them
  in our appreciation of the whole. But if we do attend to
  the parts, we see the evident care that has been lavished
  on them, and we see that it is just this care that allows
  the feeling of the whole to come into being.
- The same is true of writing. Good writing flows; we get
  caught up in it. We forget about mere words and sentences
  and lose ourselves in the intoxication of meaning. But
  if we do happen to look more closely, we see that this
  flow is created by the care of all the little parts: the
  word order, the insertion of a clause to adjust the timing
  of the sentence, rhythm, how topics are introduced and
  left off and woven back in. And again, it is just this
  care of the parts that frees us from being distracted by
  them, and allows us to be caught up in the whole.
- What can this possibly mean for engineering?
- Few people appreciate code for its own sake. Rare is the person who admires
  a codebase the way they might admire a painting or a symphony.
- Quality in engineering is practical rather than artistic.
- But this is not because Quality in engineering is different from
  Quality in art. Quality is the same everywhere. Engineering quality
  is practical because *engineering* is practical. When
  Quality is found in engineering, it heightens the practicality
  of it just as it heightens the aesthetic experience of art.
- So what does engineering quality feel like to the person
  reading or maintaining code?
- Comfort with the system that comes from a holistic
  understanding of how it works. This holistic understanding
  may come initially from documentation that describes,
  simply and briefly, how the program is structured, or it
  may be cultural: a shared pattern language.
- But the holistic understanding is also supported by
  specific details. You can look at each detail and quickly
  get an understanding of how it relates to the pieces
  around it:
  - in terms of code organization
  - in terms of call hierarchy
  - in terms of its responsibilities and interface
  - in terms of how it is allowed to affect the application
    components (classes, functions, variables, databases,
    filesystems, external services, etc.) outside it.
- Each detail you observe reinforces and refines your
  concept of the whole. There is no contradiction between
  the parts, no "backtracking" as you find out that what you
  thought was true is actually false. There is only a
  filling in of the details of what you already know.
- Code that supports this kind of gradual unfolding of
  understanding does not happen by accident. The creation of
  code that has this quality follows exactly the same
  sequence as the process of understanding.
- The holistic architecture of the program is defined first,
  according to the largest patterns in the pattern language.
- A sketch of the program, no more than a skeleton of the
  major architectural components, is made to work. At this
  point, the program can be deployed to a testing
  environment, though it is almost certainly not ready for
  public release.
- Each subsequent change to the program takes shape as a
  an addition of detail corresponding to a refinement of the
  team's understanding of what the program should do.
- As the program grows, the feeling generated by this
  process of change is more and more one of care, community,
  and belonging. And the process *must* generate this
  feeling, if the program is to have a long and prosperous
  life.
- because the code is a shared resource. We must beware the
  tragedy of the commons.
  - Like a forest, it can be tended carefully, thinned,
    replanted.
  - Or it can be clear-cut, its abundant potential harvested
    for all its worth.
  - Or, perhaps a more apt metaphor, it can grow wild until
    it burns disastrously.
- this feeling of care and community is a very deep,
  emotional one. But it is not just a subjective thing, a
  matter of something that "good people" will feel
  regardless of what is around them. Nor is it vague
  and mystical. It is generated, by objective aspects of the
  environment, in an utterly mechanical and practical way.
- (cite the broken window study)
- Quality is a communication mechanism
  - directs attention and care to the objects and attributes
    that a culture values
  - people mimic what they see around them, but also what
    they imagine around them. If you see a broken window,
    you imagine that someone broke it, so maybe you break
    another one.
  - so Quality in a product is a way of communicating
    between the crafter and the reader/user/inhabitant about
    what is important and what is not.
- Because quality is a communication mechanism that creates
  our sense of community, it must be personal. Otherwise, it
  will fail to create this sense of community, because the
  creator is invisible or impersonal.
  - egoless in the sense of "not forcing you to fit into my
    master plan"
  - but personal in the sense that the crafter's personality
    is apparent in the work
  - there is a vision of "quality" that is impersonal, in
    which everything must be honed, optimized, and smoothed
    to an idealized perfection. You see this type of quality
    in expensive manufactured goods
  - but this type of quality fails to produce the type of
    care that allows for growth. Because the artifact is
    already "perfect", any deviation from this perfection,
    any flaw or mar or stain or damage, is a step down in
    quality. So the only reactions that people can have to
    this quality are conservatism (protecting the perfection
    from change) or disdainful rebellion (lack of care for
    perfection). Because the creator has been erased, there
    is no opportunity for any kind of co-creation, or dialog
    between the original creator and the maintainer, where
    the maintainer adds something of their own that
    harmonizes with the quality that was originally there.
    The maintainer feels no connection with, and no
    obligation to, the creator. Obligations such as
    consistency must be enforced with standards and external
    incentives and punishments.
- Sarah Mei calls this type of quality "livability".
- Richard Gabriel refers to "habitability" of code in
  _Patterns of Software_, which I think is basically the
  same concept
- Livability is not hackability. That is the ability to
  quickly make functional changes to code without care for
  its surface appearance. Hackability has short-term appeal,
  but a codebase that suffers many hacks will quickly become
  a tarpit.
- Example: CI job naming conventions:
  - Livable: 'Build Payments library v3 on Ubuntu 18'
  - Idealized: 'releng_payments3_ubuntu1804_bld'
  - Hackable: 'pay12'
- The "livable" example is not as machine-parseable as the
  idealized one, but it would be easy enough to add more
  information to it if needed. It prioritizes the reader's
  understanding over any idealized notion of perfection or
  uniformity. The "hackable" version
  conveys nothing except a hint at the product name, but it
  is perfectly clear how to hack in a new job: just
  increment the number.
- Christopher Alexander identifies this "livable" Quality,
  that is personal and yet egoless, that connects creators
  and maintainers in a harmonious community, and that arises
  from the gradual unfolding of structure within the
  framework of a pattern language: he calls it the Quality
  Without a Name.

In summary:
- Quality is "a subtle kind of freedom from inner
  contradictions", a harmony between the whole and the
  parts in which the parts support the whole without
  distracting from it, and yet are well-formed wholes in
  themselves.
- This quality is visible in art, writing, and engineering.
- In math, science, and engineering, Quality is a property
  of solutions and explanations that are
  more easily apprehended rationally. It is pragmatic,
  because humans have scarce cognitive resources. But
  the creation of Quality itself is not a rational process.
- The quality is achieved by careful shaping of the parts
  (so that they do not become awkward or distracting) while
  keeping the whole in mind
- quality in a codebase allows engineers to quickly
  understand it and make changes easily
- To maintain a high level of quality, the quality must be
  of a kind that inspires a feeling of community, so that
  people care intrinsically about maintaining it
- The quality that has this effect is what Christopher
  Alexander calls the Quality Without a Name.

## Seeing Code

- I'm a visual learner (sometimes). How can this section
  accommodate other learning styles?

### Visualizing call graphs

- a pyramid with `main()` at the top and low level leaf
  functions with no dependencies at the bottom
- if `main()` is instead on the left and the leaf nodes on
  the right, this fits better with how we read code: you can
  imagine pasting the source code of each routine on top of
  the node, and drawing lines from each function call to the
  node representing that function
- if my goal is to simply represent calls, not dependencies,
  I don't worry about "merging" identical nodes. I just let
  the graph be a tree, with functions called from multiple
  places duplicated
- what about recursive or co-recursive functions? I rarely
  encounter these in my day-to-day work, so I don't have
  mental habits for representing them. A flowchart may be
  a better representation in this case (think of old
  programs with lots of GOTOs)
- To clarify, I can't instantiate the entire call graph of
  a program in my visual working memory. That would be
  insane. But the fact that I *could*, given enough time and
  paper, draw out a graph that has the same structure as
  what I see in my head when I read code makes me more
  confident in reading the code and understanding what calls
  what.

### Visualizing test coverage

- each test is a pin that holds some part of the program's
  behavior in place
- this type of visualization gets more complicated, and
  clashes with the call graph visualization, when I test
  using stubs, mocks, and spies (dummies and fakes are ok,
  see the patterns on testing). So I don't use stubs, mocks
  or spies in my tests.

### Visualizing Layers

- slice the call graph into:
  - procedures, side effects
  - application-specific functions
  - application-agnostic functions

- kind of two dimensions here:
  - application-specific or not
  - side-effecting or not

- structure layers with application-specific code "inside"
  and agnostic framework/library code "outside"

```
Side Effects
------------
main()
------------
app procedures
------------
app functions
------------
libraries
```

In many languages this seems awkward because now the top
of the call stack is main(), in the middle of the layer
cake, so the layers no longer correspond visually to the
structure of the call hierarchy.
But Verse literally structures the call graph this way.
Procedures do not have dependencies on side-effecting code.
Instead, side effects are expressed as a `yield`, or
temporary return of control, from the procedure to its
caller (the Verse framework).

- c.f. "hexagonal architecture", "clean architecture"
- but more subtle. You don't have to follow any fancy,
  heavyweight patterns to structure code this way.
- Gary Bernhardt's "Functional Core, Imperative Shell"
  concept

### Isomorphism Between Object-Oriented and Procedural Styles

You may wonder where object-oriented programming fits into
all of this, since up till now I have only talked about
procedures and functions.

The fact is, if you have routines that form closures and
allow mutable local variables, you can create objects. There
is nothing special about object-oriented languages except
that they provide convenient syntax for doing this.

Here's how to create a simple counter object with `inc`
and `value` methods in JavaScript, using no object-oriented
syntax, only closures:

```javascript
function Counter(count=0) {
  const self = {
    inc,
    value,
  }
  return self

  function inc() {
    count++
    return self
  }

  function value() {
    return count
  }
}

Counter().inc().inc().value() // => 2
Counter(5).inc().value() // => 6
```

What about inheritance? To quote Brian Will, "Inheritance is
irrelevant. No one defends it anymore." You do not need
inheritance to write good object-oriented code. Composition
is much more powerful and actually makes for simpler, more
readable, more reusable code.

Here is another way of representing object-oriented code
as functions, as described by Anjana Vakil:

OO version:

```
class Bob {
  greeting() {
    return "hi"
  }

  farewell() {
    return "bye"
  }
}

new Bob().greeting()
// => "hi"
new Bob().farewell()
// => "bye"
```

Functional version:

```
function Bob() {
  return function(message) {
    if (message == "greeting") {
      return "hi"
    } else if (message == "farewell") {
      return "bye"
    } else {
      throw new NoSuchMethodException()
    }
  }
}
```
