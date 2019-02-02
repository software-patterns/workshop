# hci-language

A [pattern language](https://groupworksdeck.org/pattern-language) for making humanizing computer systems.

Here, "humanizing" refers to the effect that computers should ideally have on people and their relationships with each other.
It does *not* imply "making computers more human-like".

# Why

**Our surroundings have profound effects on our wellbeing.**

Architect Christopher Alexander cites many examples in his book [_A Pattern Language_](http://library.uniteddiversity.coop/Ecological_Building/A_Pattern_Language.pdf).
  - Tall apartment buildings prevent their inhabitants from casually going out or seeing what is going on in the street, leading to significant increases in mental illness. (_A Pattern Language_ p. 115).
  - Rooms with natural light only on one side make it harder to perceive subtle facial expressions due to glare from the window. (p. 748)
  - Local roads that function as shortcuts attract through-traffic and become unpleasant and unsafe. (p. 261)
  
**When spaces are discordant with the physical, social, and psychological needs of their inhabitants, they feel
artificial, mechanical, deathlike.**

Vast parking lots, impersonal apartment blocks, litter-strewn streets with traffic zooming past:
people avoid such spaces, if they can. They don't maintain or care for them.
And their peace of mind is eroded a little each time they are forced into contact with these spaces.
The spaces and the people each take from the other more than they give, and so gradually the whole system destroys itself.

**But it does not have to be this way.**

Alexander lays out a process by which people can create spaces that are _alive_: that is, self-maintaining,
whole, in harmony with the physical, social, and psychological forces that shape the activity there. Key to
the process is the concept of a **pattern**.

**Patterns tell us how to create self-maintaining systems.**

A pattern is a network of relationships among architectural elements that, when
implemented in physical space, helps create living, self-maintaining systems. Alexander's patterns have
titles like "Four-Story Limit", "Light on Two Sides", and "Looped Local Roads". Each one is
a concrete instruction about how to shape a particular type of space. The 253 patterns are
arranged in a sequence from largest (state or county level planning) to smallest
(details of construction and interior decoration).

Patterns do not stand alone.
Each pattern is linked to others: the larger patterns that form the "context" in which it is appropriate or
necessary, and the smaller patterns that are required to make it effective.

**The whole network of interrelated patterns is called a *pattern language***. 

If patterns are like words, a pattern language is like grammar: it tells you how to put the pieces together
to form systems that are fractally self-consistent.

This fractal self-consistency means that pattern languages can extend to all levels
of detail in a system, from the very smallest to the very largest.

Alexander's works are often cited as being concerned with architecture, but I think that's underselling them.
They describe nothing less than a comprehensive vision for human civilization. They are an instruction
manual for creating a more beautiful, more humane world.

**But the advent of personal computers has created new challenges for pattern languages**.

Alexander's work on patterns was done while Unix was just being born. His language says nothing
about how we might begin to integrate computers into the patterns of space and activity that
shape our lives.

**Yet integrate them we must.**

Anecdotally, the language people use when talking about software hints that they conceive of it as an
extension of physical space. People speak of being "on a webpage" or going "to a site"—though of course
it would be more accurate to say the site's data comes to them. The cursor and the viewport are extensions
of the ego: "scroll down" still means "look further down the page", despite Apple's efforts to foist
inverted scrolling conventions on us all.

Yet even if we did not think of computer systems as a new type of space, we would have to
account for them in our pattern languages, because computers have physical and societal effects that
extend beyond the screen and which
[we have yet to fully account for](https://ledger.humanetech.com/).
- In 1996, a software engineering mistake [caused the Ariane 5 rocket to self-destruct](https://www.dreamsongs.com/MobSoftware.html),
resulting in the loss of [$370 million](https://blog.bugsnag.com/bug-day-ariane-5-disaster/) worth of hardware.
- [In 2013, the Healthcare.gov website launched](https://en.wikipedia.org/wiki/HealthCare.gov), on time but tenfold over budget—and didn't work for the vast majority
  of people who tried to access it. By August 2014, the total cost of project had exceeded $1.7 billion; the initial estimate was $93 million.
- [In 2015, the number of distracted-driving accidents surpassed the number of drunk-driving accidents and caused
a third as many deaths](https://www.thezebra.com/insurance-news/4671/drunk-driving-vs-distracted-driving-dangerous/).
- In 2016, [disinformation campaigns on social media](https://www.thedailybeast.com/facebook-now-says-russian-disinfo-reached-150-million-americans) may have swung the U.S. presidential election.

[We cannot look for single "root causes" of failure to address these issues](https://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf). The problems are systemic,
and the solutions must be holistic.

**What we need now is an extended pattern language that accounts for computer systems.**

Such a pattern language will constitute an instruction manual for creating a society where:

- *Computer systems support and sustain the non-computational patterns of society.*
- *Personal computers enhance physical space and activity.*
- *The economic gains of improved communication and computation are equitably distributed.*
- *People have the means to shape and adapt their own software, just as they adapt their own physical space.*
- *Self-consistency and local symmetries arise at every level, even as infinite variety unfolds, by
  the simple fact that the pattern language is shared.*

The result of all of this will be a society with the character of nature: exuberant, diverse, no
two places alike—yet unified, whole, and self-sustaining.

# What

- This repository is a space for giving and receiving feedback on patterns.
- It will never be "finished" or publishable; rather, it is a community resource from which
  the raw materials of publishable works can be mined.
- It is a space where we can let our weirdest and wildest ideas run loose.
  - *but please illustrate your weird ideas with lots of examples; it's hard to talk about ideas without something concrete to point to. —benchristel*
- Our scope includes code, software architecture, user interfaces, team dynamics, and open-source communities.
- Our quest is to seek [the quality without a name](https://onluminousgrounds.wordpress.com/2010/04/24/the-quality-without-a-name-part-one/).

# Who

*I'd like to consider the needs of various groups impacted by computer systems.
Users, nonusers, product owners, programmers, designers, sysadmins.
Whatever we end up writing, we have to make sure programmers are on board with it,
because they ultimately determine what gets built (and they'll likely be a large
part of our audience). But having multiple viewpoints
is vital. One possible goal of this work is to convince programmers that they can 
live harmoniously in the world; that holding themselves to high ethical standards
is not stupid. —benchristel*

# Collaborating

This repository is structured in a way that I hope will encourage
collaborative, piecemeal growth.
- You can add a pattern to the [patterns directory](./patterns)
  by following [these instructions](./patterns/00_PATTERN_TEMPLATE.md).
- You can add links to the [References](./references.md) file.
- If you have feedback on a specific pattern, you can start a discussion, [wiki-style](http://wiki.c2.com/?PatternLanguage),
  in an italicized block within the pattern text itself. Below is an example of this.

*I prefer patterns to be concrete, specific, and grounded in our experiences.
Any positive experience you've had creating or using software is
a potential seed for a pattern. If you've also experienced
the pain of* not *having the pattern in your environment, so much the
better—that's evidence that the pattern actually does something. But you
don't need a lot of evidence to write the pattern. Patterns
can (should?) start out as just hypotheses; over time I'd like to test each
pattern more rigorously and see if it really holds up. —benchristel*

# Further Reading

The following resources help explain what patterns are all about.

- The [metapattern](./patterns/00_PATTERN_TEMPLATE.md).
- [Martin Fowler's "Writing Software Patterns"](https://www.martinfowler.com/articles/writingPatterns.html)
- [_A Pattern Language_, by Christopher Alexander et al.](https://mythstyles.com/products/a-pattern-language-towns-buildings-construction-center-for-environmental). The original pattern language; this one is about physical architecture,
not software. The book is also available [as a PDF](http://library.uniteddiversity.coop/Ecological_Building/A_Pattern_Language.pdf).




