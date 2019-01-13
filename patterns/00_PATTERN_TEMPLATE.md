# Pattern Template

In order to clearly communicate the patterns within a pattern language, it is helpful
to have a standard form for representing a pattern. This file both describes
and exemplifies a pattern style based on the "Alexandrian form" named for Christopher Alexander.
Use it as a base for creating new patterns.

---

**When we give advice about software, it is tempting and easy to overgeneralize.**

As software developers, we are trained to generalize our solutions. When programming, this training can
be beneficial, but when trying to ground *advice* on programming in empirical facts, it is
usually detrimental.

When solutions are overly general, it becomes hard to relate them to any specific problem.
The author may not even explicitly state what problem or problems they are trying to address.
General solutions are superficially attractive because they seem to give us a Grand Unified
Theory or "silver bullet" that will magically improve all the software we write. However,
we have found that in practice they fall short, by failing to account for the intricacies of
any specific situation.

**Resist the temptation to overgeneralize by using this template to document patterns. Contextualize
the patterns within a language: a self-reinforcing web of inter-referenced patterns. Make each
pattern a falsifiable hypothesis about the world, so it can be improved over time as new discoveries
are made.**

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
- Then a horizontal line to mark the beginning of the pattern body. In markdown, this is represented
  by three dashes (`---`).
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
- Then another horizontal line to mark the end of the body of the pattern.
- Finally, a list of links to smaller patterns that help reinforce the present pattern and
  make it live.

## Examples

For an example of a pattern, see [this file](./00_PATTERN_TEMPLATE.md).

---

Links to smaller patterns will go here once we have some. "High-quality Examples" is a good
candidate; ask me about Kathy Sierra's videos if you are interested in writing up this pattern.
