# Patterns

When you observe some set of relationships, causes, and effects occurring
over and over again in software systems (or any type of system), you want some way
of capturing that observation—of distilling the *pattern* to its essence so you can
communicate it to people. This pattern tells you how to do that.

This file both describes and exemplifies a pattern style based on the "Alexandrian
form" named for Christopher Alexander. Use it as a base for creating new patterns.

---

**When we give advice about software development, it is tempting and easy to focus on methods
instead of results.**

Methods are attractive because they tell us what to do. Anyone can pick up a book on development
methods and apply it to their project.

Unfortunately, method-oriented advice often focuses on *how* at the expense of *what*: What is
the method supposed to achieve? If you have only a vague sense of what the outcome of a method
is supposed to be, how do you know if it is appropriate for your situation? How do you know
if the method is even working, if you can't compare your results to some expectation?

*To make this idea concrete: here are summaries of some methods I use every day.
Note the absence of clearly stated goals. In my experience, these methods are
often explained this way, without reference to goals.*

- *TDD: Write a failing test. Modify the program to make it pass. Refactor. Repeat.*
- *Story Points: Estimate amounts of work to be done in abstract "points" rather than
  concrete units like hours. Bugfixes and technical "chores", however, are not given
  points, even though they take time to complete.*
- *Gherkin: Write user stories in the form `GIVEN ..., WHEN ..., THEN ...`.*

*There are good reasons to use all of these methods, but people often
explain them without much more detail than I've given above.* Why *the methods are
useful is often not part of the explanation—or worse, people get the "why" dreadfully
wrong. —benchristel*

When we aren't explicit about goals, methods become dogma, and dogma rots quickly.
New technologies are invented all the time, but it takes years, sometimes decades, for
old methods to catch up. Meanwhile, the forms and relationships we want to create
remain largely the same.

Methods change; goals stay the same.

**Instead of describing methods, describe patterns: the
[centers](https://en.wikipedia.org/wiki/The_Nature_of_Order) and relationships that come
into being when the method works exactly as it is supposed to. Patterns are landmarks we
can use to get our bearings as we experiment our way toward creating
[living wholes](http://dreamsongs.net/Files/AlexanderPresentation.pdf).
We can describe the interactions between patterns—how the patterns support each other—in
the form of a pattern language.**

When people share a pattern language, they can use whatever tools
they are comfortable with, and whatever methods exist within their culture,
to create a system that has the patterns.
Then they can judge what they have created against the patterns and determine
if those patterns are truly present, and if not, try again.

Viewed this way, a pattern language does superficially resemble a kind of method.
You can use the language like a cookbook, creating
and assembling patterns one by one. But this
step-by-step method, though useful, is not prescribed. Indeed, to create really
profound designs, in which the patterns are tightly packed and
interrelated, we have to abandon step-by-step methods and view the
patterns not as recipes but as touchstones. We can then begin to
evaluate, and perhaps even understand, the results of the unconstrained,
informal processes that characterize the work of a master.

> Indeed it turns out, in the end, that what [the pattern language] method does is simply
> free us from all method.
>
> —Christopher Alexander, _The Timeless Way of Building_

Pattern languages free us. They allow us to be ourselves.
Instead of applying science to our methods, and worrying "are we doing it right?",
we can apply science to our *results*, and ask "did it work?" We can work
together as our true, individual selves,
secure in the knowledge that if we go astray, it will not be for long,
because we will see that the patterns are not right, and correct them.

## Caveats

A pattern language can only work when each pattern is
objectively present in or absent from any
given system. Anyone who knows the patterns should be able to walk into a
codebase or a workspace and assess in a few moments whether a given pattern
is present or not. The same applies to
the problem statement of a pattern. To be useful, a pattern must
resolve real forces that are really present within a system. If the
forces addressed by a pattern are vague or subjective, people can get
caught in endless debates about whether the pattern is applicable
to them.

We must also beware of [Goodhart's Law](https://en.wikipedia.org/wiki/Goodhart%27s_law):

> When a measure becomes a target, it ceases to be a good measure.
>
> —Marilyn Strathern, paraphrase of [Goodhart's Law](https://en.wikipedia.org/wiki/Goodhart%27s_law)

**Patterns are a measure, not a target.**
When we make an effort to fill our work with patterns, we miss the point.
The [100 Line File](./100-line-file.md) pattern does not mean
we should arbitrarily chop long files into 100-line chunks just to
satisfy the pattern. It only means that the largest files in a healthy
codebase tend to be about a hundred lines long. As an analogy: if a doctor
is concerned about a patient's high blood pressure, she doesn't correct
the problem by removing blood from the patient. She might prescribe lifestyle
changes that will lead to overall better health, with reduced blood pressure
as one of the indicators of health.

## Documenting New Patterns

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
- Next, a summary paragraph that states what "FAQ" the pattern answers. If you're stuck, fill in the blank:
  "This pattern tells you how to \_\_\_\_\_". For example:
  - _This pattern tells you how to **interview prospective engineers**_
  - _This pattern tells you how to **name directories in a hierarchy**_
  - _This pattern tells you how to **structure tests within a file**_
  - _This pattern tells you how to **extract functions from a larger routine**_
  
  Alternatively, starting with "This pattern tells you *when* to" fits some patterns better.
  - _This pattern tells you **when to add more detail to a test case, and when to split out a new one**_
  - _This pattern tells you **when to allow an object to be mutable**_
  - _This pattern tells you **when to work solo**_
  
  *TODO: I need to validate this format by going through the existing patterns and rewriting them in this style. —benchristel*
  
  Contextualize the pattern within the language by linking to the "larger"
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

For examples of patterns drawn from _A Pattern Language_, see
[patterns-dev](https://patterns-dev.github.io/patterns/clean2/patterns.htm).

---

Support each pattern with [Many High-Quality Examples](./many-high-quality-examples.md).
Give patterns concrete, unique names that can become part of the common vocabulary
of the software profession—compare [Ubiquitous Domain Language](./ubiquitous-domain-language.md).
To be effective, patterns must be shared, so test and refine your patterns with
a [Community of Peers](./community-of-peers.md).
