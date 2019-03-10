## 2019-03-09: Tools

A possible book title is _Tools_, or maybe _The Code Crafter's Tools_, or _The Process of Repair_.

Dull. Endlessly dull. Dry, dreary, grey and lifeless. A blank gloom that shuts out even despair.

Such is life without what Robert Pirsig, in _Zen and the Art of Motorcycle Maintenance_, calls Quality.

I believe *negative space* is an appropriate architectural metaphor for the absence of Quality.
Negative space is what is left over when something is constructed. It is unshaped space, ignored by both
builders and occupants. The space in between real places. A nowhere-place where no one wants to be.

Negative space creates negative time.
We hurry through parking lots, the deserts of suburban life, to get to the next oasis of positive space.
We commute so we can work. We work so we can eat and shop and pay rent. We eat (or drink Soylent) so we can live.
If we're lucky, we get moments of Quality in between all this negative time, this plumbing of life.

But buildings and cities can be constructed in which there is little to no negative space, and it is
possible too to live so that there is no negative time. Yet in the 21st century United States, this is
becoming harder and harder.

(quote from ZAMM about the "death force" of technology and the Sutherlands running from it)

Technology has been reduced to a mere means in the name of "efficiency". But this is a false efficiency,
because it has stripped technologists of the privilege of caring about what they do (replaced craft and a feel
for the work with schedules, standards, laws), and so drained technology
itself of inherent value. Most of the technological trappings of modern life, for all their ornamentation and
surface veneer, have no more personality or spiritual weight than the door of a public bathroom stall. The web
of technology that holds civilization in place is just dead weight, a parasite that has grown so large that
if it dies, the host dies. And with every passing year, the web spreads and thickens.

At this point, you may feel like rushing to technology's defense with the argument that without technology,
we would have much more poverty and famine and disease than we currently do. That is true. I'm not proposing
that we get rid of modern technology or even reduce it. I am merely pointing out that all the negative space and
time created by Qualityless technology is an appalling and unnecessary waste, a waste that has gone
unreckoned because it is measured not in dollars but in moments of human life.

With time and care, though, the waste can be reversed. That process of reversal is the subject of this book.

Caring is prerequisite for Quality. Quality is what people eventually produce when they care about their work and
about what they are producing. I term a person who cares about what they work on and how they work on it a
*crafter* or *craftsperson*.

But caring alone is not enough to produce Quality directly. When crafting something new, three paths are possible:

- Not caring -> (unobservedly) low Quality work
- Caring -> high Quality work
- Caring -> low Quality work

That is, if you don't care about what you're doing, it is almost impossible to produce work of high Quality.
You can make something that meets requirements, that hits the right benchmarks, through sheer force of will and
toil, but that's not Quality. It's more like quantity—because it's objectively measurable. And anyone who looks
at the result with an eye for Quality will be able to see the difference. They'll be able to see that the work
was not produced by a human mind and heart but by an inhuman force that used the human as a tool.

If you don't care about the work, though, *you* won't notice the low Quality. So though you get no joy from the
work, you don't suffer much, either.

If you do care, you may produce something of high Quality, but that's not guaranteed. You might also produce
something of low Quality, which is the bitterest feeling there is—to care and fail. Since caring and failing is
by far the worst outcome, many people, whose failures lead them to believe they don't have the knack for Quality,
choose the path of not caring.

This is tragic, because, after all, there is no "knack for Quality". It's not something you're born with—or rather,
it's something *everyone* is born with. If you let yourself see the Quality or lack thereof in
your work, you'll see it, guaranteed. The question is, if you see bad Quality there, how do you fix it? The fear
of having no answer to that question is what makes people shut down the part of themselves that cares.

To make Quality, then, you need three things:

- Caring
- The right tools
- Practice

I can't make you care, and I can't make you practice. But I can give you tools, and that's what this book is about.

By "tools", I don't mean fancy computers or fancy software. You don't need those things to make Quality,
though they're nice to have. The real work of programming happens in the mind, not on the screen, so the tools I
describe are mental ones. They comprise two groups:

- Tools for "seeing" code, turning it around in your mind, observing it from every angle.
- Tools for changing code.

The tools for changing are also tools for seeing: as you change code you learn new things about it that you can't
easily see any other way. But before you start changing code, you need to be able to see it at a basic level, so you
know what changes to make. That is the motivation for the division into two groups. The "changing" tools depend on
the "seeing" ones.

**Caring About Caring**

When I was first introduced to the idea of code quality, I thought the way to maximize it was to care about every tiny detail
of my code and working environment. I obsessed over variable names. Whitespace alignment. Tab size. Syntax highlighting.
The fonts my editor used. Comment style. The order of methods in classes. And on and on and on.

But to attend to everything is to attend to nothing. There has to be some notion of priority, of paying attention
to what matters, and letting go of what doesn't matter as much. Caring doesn't mean insistence on perfection.

It *especially* doesn't mean insistence on *externally imposed* standards of perfection. When you mistake the idealized
images in your mind for Quality, you can run into real trouble.

My parents just finished up remodeling their house, and this particular hang-up bit them many times during the process.
The original plan was just to replace the windows and part of the floor, but my mom figured, what the heck, as long
as the construction people are there, why not take the opportunity to replace the doorknobs and hinges, too?

The original knobs were cheap, funky, brass-plated nickel, and they'd started to corrode in places. The ones on the inside of
the bathroom doors, that people touched with damp hands, were in the worst shape. But they turned and latched easily
and the doors swung smoothly, without preferring to "settle" in a particular place when they were open. It's so obvious
that doors and knobs should behave like this that we all took it for granted. Didn't even think of it as a property of the
hardware. It was just a property of *reality*.

At this point you can probably guess the rest of the story. They got the new hardware installed. The knobs were fancy
oil-rubbed bronze from one of those glossy catalogs that are as wide and thick as coffee-table books. But they didn't
latch quite right. On many of the doors, the knobs turned haltingly, as if they had a catch in their throats. Other
doors you had to lean on hard to get them to close. One of the locks didn't work. The hinges creaked. When you opened
one bedroom door, it would inch its way closed again, pulled by gravity.

On my first tour through the house I noticed these things and pointed them out. I thought one door was locked, at first,
I had to twist the knob so hard. "Well, you'll just have to muscle it," my mom said. "It's *quality hardware*. Not like
that *old* crap."

I was stunned. Speechless. In what universe did "quality hardware" mean "doorknob that doesn't turn"?

The problem with holding up Quality as an ideal is that cognitive biases can get us to believe that almost anything
has good Quality. When Quality is just a groovy, unexamined feeling for what's good, these biases can distort
our decision making. This gets especially fraught when we start judging Quality in *people*, since most of us have
subconcious racial and gender biases that affect our judgements when we're not careful. Clearly, some better-defined
value than Quality is necessary.

That's why I focus on *caring*. Though my mom and I don't see eye to eye on the *quality* of the doorknobs she bought,
she readily agrees that the people who installed them did not seem to *care* about the results of their work. She might
also acknowledge that the people assembling the hardware at the factory didn't evidently care about *their* work.
It's this lack of evident care that we were both, in our own way, riled up about.

Now, this lack of caring isn't, I think, usually a personal failing of the would-be craftsperson. Lack of care is
a structural issue: it's baked into our concept of a "job", in which workers are given incentives to spend time at
work and complete tasks. Caring about the work, and trying to improve the system, are often viewed as distractions,
and the internal pain of caring and failing is amplified by the external threat of job loss if one's own sense
of Quality causes schedule slips or other disturbances. Far safer, far better, not to care.

And yet—what a harsh price for peace is one's own sense of caring! To be robbed of the opportunity to care is to
have a piece of one's humanity taken away, because caring and showing others that we care is part of how humans
communicate. Caring and the exchange of Quality binds together communities, families, and friends.

I've made it sound like caring is this warm, fuzzy, emotional thing, but when I say it's a form of communication I
mean that literally, and like other forms of communication, it has hard, practical consequences.
Caring is how people communicate to each other what is important and what is not. We learn, from infancy, which
facts about the universe are important and which are unimportant by observing what the people around us
care about. (quote Pirsig on English vs. Hindi, maybe Rosenfelder on phones vs. phonemes and linguistic development in infants?) 
If we failed to learn to distinguish important from unimportant facts, science and technology would be impossible.
When we don't know what to focus on, empirical methods of obtaining knowledge simply stop working.

(Quote Pirsig on Poincare on the selection of facts that precedes science)

As an example:
I sometimes read code and see things I don't understand, code that has no apparent reason to be the shape that it is.
If the code is messy, if there is no evidence of care, I chalk the inexplicable part up to sloppy coding. But if
I sense from reading the rest of the code that the person who wrote it cared about what they were doing, I'm much more
likely to think of that inexplicable bit as significant, as something crucial that *I* simply don't have the context
to understand. And I, in turn, will be more careful, and dig deeper. I'll research and experiment to find out what's really going
on in that code. I will, in a word, do science on it. And I will take the time to do that because my predecessor's care
has communicated to me the importance of this strange bit of code that I just don't have the background to understand.

The practical impact of caring on software development is why I have hope that, in time, we can heal the wounds that our
present form of Qualityless, technological work has wrought on American society. If my complaint were just that door
hardware were being inexpertly manufactured and installed, I would have little hope of doing anything about it. The
structure of work would not be turned topsy-turvy just so people in doorknob factories could care about what they
produced. It would not be in the interest of the owners of the company to make it happen, and the reason it would
not be in their interest is that doorknob manufacture is not a form of practical communication that impacts
the progress of scientific knowledge. Programming, on the other hand, *is* such a form of communication. The success of
software companies depends on the scientific progress that caring about code enables. It is thus in software that Robert
Pirsig's notion of technological Quality, which has stood acclaimed but mostly dormant for almost half a century, can
finally make its mark.

**Working with People**

Once you and your team have the tools, and have begun making Quality together, you will inevitably discover
differences in how you each think about Quality. People care about different things, so if you have a bunch
of people caring about the code you're writing and the software you're building together, there's bound to
be tension.

The way teams have traditionally resolved this tension is by giving each person their own part of the codebase
to work on. I don't touch your code, and you don't touch mine. We can each pursue our own vision of Quality within
our isolated silos.

There are many problems with this, though, as Kent Beck describes in _Extreme Programming Explained_. One is that
if someone goes on vacation, their section of the code is effectively frozen in time until they return. No one else
knows how to change it, so work that touches that part of the codebase grinds to a halt. The same thing happens,
only worse, when someone leaves the company.

Extreme Programming (XP) tries to remedy this via the practice of shared code ownership. Any member of the team is
empowered to change code anywhere in the codebase, provided they write automated tests to ensure that later changes don't
wreck what they did. This practice allows the team to converge on a set of shared norms, so that if someone leaves
the company, it isn't a catastrophe. Their code looks similar enough to the rest of the codebase that other team members
can jump right in and fill the gap.

Unfortunately, this forced convergence of Quality norms tends to drown out minority voices on the team. If I'm the only
person on my team who cares about security, or the only one who prioritizes readability over performance, my sense of
Quality will suffer when I'm working on shared code. If shared code strays too far from my ideal of Quality, I'll
care about it less and less. And lack of caring produces lower Quality.

I have some theories about how to resolve this dilemma, between individual code silos and shared code ownership.
One idea is for the team to share norms around testing but let people structure production code how they please;
this helps ensure that if one programmer has to work on another's code, at least they have tests as a safety
net. However, people have different opinions about testing too, so I fear this just kicks the can.

Another idea is for the team to share a *pattern language* that is flexible enough to accommodate differing views.
I already have a pattern language in mind that unifies procedural, object-oriented, and functional programming
styles, so I am optimistic that a pattern language could resolve many of the interpersonal tensions around
code Quality. In this approach, the team members must be willing to work with, and respect, patterns that aren't
their preferred ones.

Ultimately, the question of how team members resolve tension boils down to how respect works on the team.
In individually-siloed code, I respect you by not changing your code without consulting you. Under shared code ownership,
I show respect by writing tests to make your job easier when you have to change my code. Under a pattern language
approach, I show respect by working with the patterns you've created in your code, though I may not particularly like
them.

Each of these patterns of respect has analogues in ordinary human society. The individual ownership and pattern-language
approaches are similar to how unrelated people in a community interact in a civil way. The XP approach is a
communitarian style that mirrors how people within a household interact.

What we have here is an apparent tension between two values: the *community good* vs. the *individual good*. The XP
approach is community-biased. The silo approach is individual-biased. The pattern language approach tries to strike
a balance... but does it succeed?

I think the way to unify these two apparently opposed values is with the value of *belonging*. Belonging is a state
in which the individual is supported by the community, feels some form of identification with it, and gives back to
it. The community in turn recognizes individual variation and affords individuals freedom of self-expression.

This is an analytic way of describing belonging. In terms of immediate feeling, belonging is just another form of
caring—but caring about people, instead of work or the products of work.

## 2019-03-07

Efforts to improve code quality often focus on the code as an objective entity. But that misses the point.
Code quality is in your mind.

Have you ever been paralyzed by fear when trying to make a change to code, and then had an expert swoop
in to help you, only to make exactly the changes you were considering but were afraid to make? It's happened
to me many times. In complex C codebases, e.g. the code that looks correct often has subtle things wrong with
it: memory leaks, unintended side effects... you have to have a great deal of faith, both in yourself and in the
people who developed and documented the functions you're calling, to change such code with confidence.
Even when the code is high quality, if you have no basis for *knowing* that it's high quality, it might as
well be low quality.

Re: the logical impossibility of reading code in the last post: the way the deadlock gets broken is via naming.
Names are the foundation of informal reasoning about code: they ground our reading in human metaphors.
If the program doesn't have names (e.g. if it's minified javascript) what do you do to understand it? You find
leaf nodes of the call graph, things with no dependencies, and assume they're correct. Then you rename them after
their actual behavior. Then you find functions that only call named things, and rename them after what they appear
to do, and so work your way up the call graph.

Is Quality in code culturally relative, or universal? I think it's some of both. The difficulty is in separating
the two, in finding the universal elements amid the cultural ones.

E.g. in OOP it's a cultural value to hide data inside objects. In FP the cultural value is the opposite: data
should be exposed and made of simple datastructures. Both of
these cultures adhere to their values with religious certainty, despite the fact that the other culture functions
just fine. So the degree to which data is hidden has nothing, directly, to do with Quality.

I think the universal value underlying both of these cultures is *safety*. In OOP the only way for data to be "safe"
is if it's encapsulated, otherwise anyone can just come along and change it. Because data is mutable, encapsulation
is necessary. In FP, data is immutable, so it's safe to expose it.

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

People are in the habit of thinking of programming as a rational, straightforward process, one in which truths are
objective and externally imposed. The program is either right or it isn't. It has a bug, or it doesn't.

My first task in this essay is to break you of this habit of thinking. Programming isn't a purely rational process,
any more than writing is a purely rational process. No program is objectively correct or incorrect. That is,
although statements about a program can be true or untrue, the program itself cannot be.

There is a strange thing that happens in the interface between a human reader and code. Perhaps you see it
already. Perhaps, though, you are so used to reading code that you don't see the strangeness, so I will explain:

Code does two things when you read it: it *describes* and it *persuades*. It describes what the program
is supposed to do, and it persuades you, via its structure, that the logic of the program has been expressed
correctly to the machine.

Unfortunately, each of these processes, describing and persuading, is founded on the other. They are locked in
a deadly embrace, and there is no way to untangle them.

- Describing depends on persuading. You can't understand what the program is *supposed* to do by reading the code;
  you can only find out what the
  program actually *does*. Unless you know the code is correct, you have no rational way of divining the *intended*
  behavior of the program from the code.
- Persuading depends on describing. You have no rational way of knowing the code is correct until you know what
  the program is intended to do and can compare the code to that intention.

There is clearly a bootstrapping problem here. And yet, it causes you no trouble. You can look at code, figure
out the intent behind it, and even identify bugs.

Thus, when you read code, you do something that is logically impossible, many times per hour.

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

It is, in a word, our sense of _Quality_ that tells us when code is right or wrong, safe or dangerous.

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
