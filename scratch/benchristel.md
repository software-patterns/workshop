## 2019-03-06: A first chapter?

Another book of programming "rules", this ain't!

Rules get misinterpreted. They get taken as dogma. When all you have in your head is a rule you can
bend it to torment and bully anyone you work with, and you'll think you're doing them a favor.

And why should programming need rules, in the first place? I ask rhetorically, of course. I think there
are good reasons. Most rules are even worth following, most of the time. But before you can wield them
well, you have to first understand why the rules exist.

It's the same with writing. Rules of grammar, style, punctuation—these can help you clarify a draft, if
you understand what their ultimate purpose is. But if the rules are all you know, your writing will be crap.
It's really the purpose *behind* the rules that matters.

Code is expository writing. That is important to realize. Though written to be interpreted by a machine,
source code's primary purpose is to describe the program's behavior to a human reader and convince
that person that the description is correct. If code didn't need to do these things, high-level languages
wouldn't be so popular, which is why I claim the human interface is actually the primary one.

There is a strange thing that happens in the interface between a human reader and code. Perhaps you see it
already. Perhaps, though, you are so used to reading code that you don't see the strangeness, so I will explain:

When you read code, you do something that is logically impossible, many times per hour.

How often have you looked at a piece of someone else's code and realized that it was likely to be wrong? That is,
that a bug resided in that code, perhaps guarded against somewhere else, but at the very least, latent there?

What logical basis did you have for making that presumption of wrongness? Unless you were comparing the behavior
of the code to some kind of correctness oracle like a reference implementation or formal spec, absolutely none.

> The first question I ask myself when something doesn't seem to be beautiful is why do I think it's not beautiful. And very shortly you discover that there is no reason. - John Cage

In a logical sense, code cannot be right or wrong, any more than the metal in a machine can be right or wrong.
Code simply *is*. It is a material that can be bent into any shape you want, and the rightness or wrongness of the
shapes is only in that "you want" - only in your mind. You can say, well, the code is correct when the program's
behavior is correct. But the rightness or wrongness of the behavior is also only in your mind.

And yet, to say that rightness or wrongness is *only* in *your* mind is to understate the case. Because somehow,
this same rightness or wrongness is in everyone *else's* mind also. How else could people ever agree on whether code
is right or wrong, whether it has a bug or not? Without a formal correctness oracle, they have no logical
basis for agreement. Yet most of the time, even without that formal standard, people agree.

Formal specs can be wrong too, especially when first being written, and people can agree about *that* wrongness
long enough to fix the spec. So you can't solve this "problem" of illogicality by insisting
on formal specs. That's just kicking the can down the road.

It's also impractical to respond to the mystery of what makes code wrong by taking the attitude that there is
no right or wrong. This is, I suppose, the attitude Hamlet might take.

> There is nothing either good or bad, but thinking makes it so. - William Shakespeare, _Hamlet_, Act 2, Scene 2

It's worth recalling that Hamlet is hamming it up, and pretending to be slightly mad, when he says this.
This view, taken to its logical conclusion, turns to either nihilism or extreme skepticism. If we really didn't believe our
own thoughts about what's good and bad, we'd starve or walk off cliffs. If we wrote code without a thought for
what was good or bad, our programs would have so many problems they wouldn't do anything useful.

In the modern world, the correctness of code is linked, however indirectly, to the functioning of
civilization and thus to our individual survival. Good programs reduce toil; they make money. They provide the
means of sustenance. Good programs can also delight us. That, in a way, is sustenance too. It is
a reason to keep going.

We usually don't think through the whole causal chain from bytes on the screen to the effects on civilization
when we read code. Yet we seem to have a knack, finely honed by millions of years of evolution, for
knowing when something will hurt us or help us. This instinct somehow extends to something as abstract and
recent as code.

It is, in a word, our sense of _Quality_ that tells us when code is right or wrong.

It is an aesthetic sense. But the aesthetics of Quality are not vague, personal, whatever-you-like feelings,
nor the diffuse miasma of popular opinion. Quality is as sharp and exact as the blade of a knife.

We seem, all of us, to have lying within ourselves a coherent vision of a better world. This vision is not
individual, but held in common, as evidenced by the agreement among our individual judgements of Quality.

Quality is mysterious, but only in the way water is mysterious to a fish: we can't get away from it, can't remove ourselves
from it, so we can't really see it. But there is nothing mystical about it. Quality is entirely commonplace;
what makes it mysterious is its ordinariness.

The two people who have written the most and the best about this sense of Quality are Robert Pirsig and
Christopher Alexander.

---

If the absence of romantic Quality is squareness (Pirsig), what's the absence of classical Quality? I think
Pirsig mostly fails to unite the two types of Quality he identifies. But if we can unify their opposites, perhaps
that will let us see, as though in a mirror indirectly, what unified Quality is.

Candidates for the opposite of Classical Quality are:
- Phonyness / fakeness? Falseness?
- Bullshit / pretension?

When phonyness and pretension are absent, and squareness is also absent, then something can be said to have both
Classical and Romantic quality. But do these two types of Quality mix and combine to create something new, more
than the sum of both types? I wonder what its name would be.

Perhaps it would not have one. I think perhaps it is what Christopher Alexander calls the Quality Without a Name.

## 2019-03-05: Science and Engineering

```
   Science : Software Engineering
:: Explain : Implement
:: Phenomenon : Behavior
:: Predict : Anticipate
:: Observation : User Story
:: Hypothesis : Code
:: Experiment : Release
```

- People often think that it takes a supremely logical mind to program a computer.
- But the role of logical thinking in programming has been vastly overstated.
- No formal way to transform informal requirements into formal ones
- Once a formal specification is written, code can be proven correct... but how do you know the spec is correct?
- It's important to distinguish formal logic, i.e. deductive reasoning, from the "logic" of inductive reasoning
  (which is never actually logically valid: one cannot reason from examples to general principles) and also from
  the bizarre, emotionless "scientism" (C.S. Lewis's term; there's probably a better one) that many people mistake
  for "thinking logically" because it aims for objectivity. The place of these three concepts in engineering is as follows:
  
  - Formal logic is great, but its uses are limited. As hinted above, arriving at a formal specification, the
    jumping-off point for logic, is the hard part. How exactly one does that, no one knows.
  - Inductive reasoning is important and pragmatic, though not logically sound. It is the means by which we get
    general specifications from specific user stories and bug reports.
  - Scientism has no business existing at all. Its distinguishing feature—a willful disregard for
    the subjective human observer, that very same person whose wellbeing it claims to promote—ought to doom
    it to ridicule. Unfortunately, scientistic views persist, possibly because they can be easily used to
    intimidate people who have not invested in such intellectual weaponry.
    
    As an example, consider the exhortation to "just think logically" when approaching an engineering problem.
    Unless this command is aimed at someone
    poring over a formal specification, it is meaningless on the face of it. One cannot use logic to get a
    formal specification (and code is a formal specification) from an informal one.
    What this really means is "prioritize the things I, a self-styled logical person, think are important",
    or, more bluntly, "be smarter". In either case, it's simply disguised intellectual bullying, not useful advice.

## 2019-03-02: Beauty, Quality, Naru

Why did C.A.'s pattern language "fail" [in Mexicali](https://www.livingneighborhoods.org/ht-0/mexicali.htm)?

I thought I had an answer, but after looking at the photos at the link above, I'm more confused than ever.

I wonder if this is partly because the photos are just snapshots in time. The most "finished" views of the
buildings aren't, really. Perhaps the Quality Without a Name resides in the temporal flow of things and not
in static forms. Certain examples Alexander gives seem to support this interpretation.

The trees along a windblown lake, bending in the wind.

The eroded gully that destroys itself.

The Quality is, or isn't, in each of these places because of the processes that happen there. It doesn't seem
to be purely a property of form.

And yet I can say that some of the photos of the building exteriors don't have the Quality, because no one is yet living
there. As I look at the picture I can see that the space is not yet complete: that more differentiation needs to
occur.

But if the Quality resides in the process, which is in this case the process of building, and if these houses are
being built by their future occupants, how can it be said that they do not have the Quality? Without seeing the
future evolution of the structure, it is impossible for me to judge.

If I see a tree bending in the wind, I can't know how whole, how self-sustaining, the situation is until I know
whether the tree falls or breaks or bends back. The degree of my knowledge is proprotional to the length of time
I spend observing.

There is obviously a kind of halting problem here.

I thought, when I first sat down to write this post, that the Quality Without a Name was just one of a cluster of
properties of form and space, and that by focusing on it to the exclusion of other things in the cluster,
Alexander might have doomed his pattern language method to what he saw as failure.

The other properties I'll term *beauty* and *naru*. The latter could also be termed *genius loci*, but that term
already has a body of context behind it that I think will confuse things. *Naru* is a word I invented long ago, that
refers to the shimmering vision of a place: the dream that captures its whole and pinpoints its essence.

"Beauty" is easy. It's simply "what people like". It could probably be complexified more than that but I see no
reason to do so. It corresponds to Robert Pirsig's "Quality" as described in _Zen and the Art of Motorcycle Maintenance_.

The aspect of the Quality Without a Name that I think is most vital to contrast with these other two concepts is
that of egolessness: freedom from contrivance. The examples Alexander gives highlight this aspect more than others:
a steel mill, blazing in the night; a group of friends strolling along, arms wide, laughing; men throwing sandbags
into a truck, working quickly, abandoning themselves to the work; the pile of beer cans on the deck of a fishing boat;
the decorations carved into a handcrafted bench.

Something can of course be egoless without being beautiful. That is important to recognize. The steel mill and the
pile of beer cans are examples.

Something can also have a strong *naru* without being egoless or beautiful. The tower of Barad-Dûr in the Lord of
the Rings films is a good example. Various pieces of software, such as Hadoop or Rails, fall into this
category. They have a distinctive "flavor" that comes almost entirely from the vision their creators wish to
impose on their development and use, but it is a syrupy, too-sweet flavor.

A *naru* can arise from an egotistical pursuit of beauty. [Verse](https://benchristel.github.io/verse) is a good example.

The hardest pair to reconcile are *naru* and egolessness. These rarely co-occur. When they do, the site of their
convergence reaches into the realm of the eternal.

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
