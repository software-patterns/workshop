# Pattern Template

In order to clearly communicate the patterns within a pattern language, it is helpful
to have a standard form for representing a pattern. This file both describes
and exemplifies a pattern style based on the "Alexandrian form" named for Christopher Alexander.
Use it as a base for creating new patterns.

---

**When we give advice about software development, it is tempting and easy to focus on methods
instead of results.**

Methods are attractive because they tell us what to do. Anyone can pick up a book on development
methods and apply it to their project.

Unfortunately, method-oriented advice often focuses on *how* at the expense of *what*: What is
the method supposed to achieve? If you have only a vague sense of what the outcome of a method
is supposed to be, how do you know if it is appropriate for your situation? How do you know
if the method is even working, if you can't compare your results to some expectation?

In the absense of clearly stated goals, methods become dogma, and dogma rots quickly.
New technologies are invented all the time, but it takes years, sometimes decades, for
old methods to catch up. Meanwhile, our objective—to live fulfilling human lives—remains
unchanged.

Methods change; goals stay the same.

**Instead of describing methods, describe patterns: the wholes and relationships that come
into being when the method works exactly as it is supposed to.**

When subgoals are expressed as patterns, people can use whatever tools
they are comfortable with, and whatever methods exist within their culture,
to create a system that has the pattern. Then they can judge what they
have created against the pattern and determine if the pattern is truly
present, and if not, try again.

An important point about patterns is that they do not occur in isolation.
To construct "a" pattern as a thing unto itself is to miss the point.
Patterns are not parts that are assembled to build a system. Rather, they
are phenomena that occur, densely packed and overlapping, within a
system that is alive.

Thus, we actually *cannot* describe precise methods for creating patterns—not
even methods with a shelf-life. Each instance of a pattern
arises in a wholly unique way, conditioned by the context and the other patterns
that intersect it.

> Indeed it turns out, in the end, that what this method does is simply
> free us from all method.
>
> —Christopher Alexander, _The Timeless Way of Building_

This is the beauty of patterns: they free us. They allow us to be ourselves.
Instead of applying science to our methods, and worrying "are we doing it right?",
we can apply science to our *results*, and ask "did it work?" We can work
together as our true, individual selves,
secure in the knowledge that if we go astray, it will not be for long,
because we will see that the patterns are not right, and correct them.

\* \* \*

To add a pattern, copy the markdown below to a new file in `patterns/`. Format the file name like `immutable-values.md`.
Then fill out each section in the template to describe your pattern.

```markdown
# {Title}

{Summary}

---

**{Problem Statement}**

{Problem description}

**{Solution instructions}**

{Solution description}

## Examples

{Examples go here}

---

{References to smaller patterns}
```

The sections are as follows:
- First, the title of the pattern, as a markdown heading. When naming a pattern, remember that all
  the patterns form a language. Names should be brief and evocative, easy to remember and reference
  in text or speech.
- Next, a summary paragraph that contextualizes the pattern within the language, linking to the "larger"
  patterns that form the environment for the present one. You can use relative links like this:
  `[Immutable Values](./immutable-values.md)`.
- Next, a statement of the problem the pattern addresses, in one or two sentences. Use **bold type**
  so the problem statement is easy to find.
- Next, a thorough description of the problem, usually in several paragraphs. Be as specific as
  possible here. If the problem statement is not specific it is next to impossible to assess
  whether the solution is a good one, and thus whether the pattern as a whole is sound. However,
  take care in this section not to expose confidential information about your company or clients.
- Next, a brief statement of the solution, in the form of an instruction. This is also in **bold type**
  as the solution should be easy to find.
- Next, a description of the solution in one or more paragraphs. Include examples under the
  heading `## Examples`.
  
  Examples should be diverse and numerous; you almost cannot have too many.
  When trying to get at the essence of something very abstract there is no subsitute for a
  cornucopia of examples.
  
  Take care not to violate anyone's copyright in this section. If you
  find exemplary but unlicensed code, take the opportunity to ask the author for permission
  to use it as an example. I don't know anyone who dislikes being told that their code is
  exemplary; plus this is a good way to let more people know about this project. ;)
  
- Finally, a list of links to smaller patterns that help reinforce the present pattern and
  make it live.

## Examples

For an example of a pattern, see [this file](./00_PATTERN_TEMPLATE.md).

---

Links to smaller patterns will go here once we have some. "High-quality Examples" is a good
candidate; ask me about Kathy Sierra's videos if you are interested in writing up this pattern.
