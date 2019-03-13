# The Process of Repair: A Programmer's Manual

Note: I use `LOOSE END` to mark topics that need to be skipped over for brevity, and woven back in in later chapters

## Audience

- junior devs who know one or two programming languages
- what's next, how do I become an awesome programmer?
- can't do much to expand working memory, raw intelligence—those are limited and roughly the same for all humans
- instead, use working memory more efficiently
- higher-level patterns, not just syntax, control flow, data structures, objects
- a "feel" for the work
- conventional wisdom holds that this feeling cannot be taught directly, from a book
- and indeed the core of the feeling can't be taught
- but the "feel for the code" that a master programmer has is backed up by three other practical elements that
  *can* be taught, without which the feeling is impotent.
  - the ability to "see" the code at a higher level, without focusing on surface details like syntax or even the specific
    language
  - a pattern language of common idioms and ways of structuring code that tend to have good properties
  - a process that incorporates feeling quality, seeing code, and shaping patterns, while continuously delivering
    valuable software.
- besides these three practical skills, the ability to perceive the feeling, which I call Quality, to understand
  where it comes from, and how to use it, are paramount.

- a note on mysticism: this book will no doubt seem like the ramblings of a mystic compared to the precise, pointed,
intellectual approach of other books on software.
- But this mystical feeling arises not because I use arcane, vague language, but because my language is so ordinary.
- My goal is not to cover up the way I actually work with a superstructure of intellectualism. Once you have departed
  from being concerned directly with the bytes processed by the machine, raw intellectualism loses its authority.
- the feeling, seeing, patterns, and process could not be thoroughly analyzed without blowing up this book to many
  times its current length. I doubt you'd read such a book.
- and in any case, the process I actually use, and every master of the craft uses, is only sparsely intellectual.
  It proceeds first by direct feeling, seeing, and experimentation, and only later is intellectual analysis brought
  in to shore up the details.
- as I will explain later, this is the process used by every mechanic, every scientist, and every mathematician.
- it is a timeless process.

## Topics

- techniques for thinking about code
- techniques for achieving quality

## TOC

- part 1: feeling quality
- part 2: seeing code
- part 3: shaping patterns
- part 4: the process of repair

## Part 1: Feeling Quality

- the two faces of quality in _ZAMM_
  - a criterion for pre-intellectual sorting of irrelevant facts from relevant ones, good solution paths from bad ones
    - quality of a fact is its ability to rise into intellectual consciousness - mental buoyancy
  - the relationship between subjects and objects, that is often mis-identified as either subjective or objective,
    and is somehow related to goodness (I quite apparently don't understand this one)

- conflicts between existing ideas about quality, how to achieve it
  - context implicit in advice
  - rules become dogma
  - tools, not rules
- **quality is in your mind**, not the code
  - your own **confidence in your code**
    - the **inverse of ignorance**?
      - something works, but you don't know why -> bad quality
      - something doesn't work, and you don't know why -> bad quality
      - "knowing why" doesn't have to be super deep, down-to-the-metal understanding
      - you just have to be able to look at the code and see your intention reflected back at you (and have tests that confirm
        that it really does what you intend)
  - to go fast, you need to trust your code
  - Code Climate can tell you if your code is bad, not if it's good
- quality is evident care
- quality is the external reflection of your own thoughts
- quality is a social mechanism
  - evident care directs attention
    - consistency is important not as an end in itself, but so that unusual/exceptional things look different
  - shared understanding of the code
  - identification of the coder with the code
  - Belonging
    - community supports and affirms individual, individual gives back to and identifies with community
- quality is "a subtle kind of freedom from internal contradictions" (Christopher Alexander)
  - harmony between the mechanism and the activities that happen around it
  - simplicity -> fewer exceptional cases -> exceptions can be handled gracefully
    - "simplicity" that makes more cases exceptional isn't really simple
      - LOOSE END: null object pattern, maybe others
  - filing cabinet drawers that lift out

## Part 2: Seeing Code

- don't fear the closure
  - they're everywhere now. Go, Java, JavaScript, Ruby, Kotlin, Swift, and of course every functional language
  - "objects are just a poor man's closures"
  - *much* easier to reason about if you first learn closures in a language that doesn't have mutable variables

- capabilities of control structures (focused on languages with garbage collection)
  - inputs
    - read parameter (taken for granted, mostly)
    - read variable in outer scope (instance, class, or global)
    - read side effect (time, rng, database, file, network)
  - outputs
    - return value
    - invoke callback
    - modify parameter (special case of invoke callback in OO)
    - modify variable in outer scope (instance, class, or global)
    - output side effect
    - nonlocal exit
    - throw exception (special case of nonlocal exit)
  - you might say "so what? all code does those things!"
  - code shouldn't do all the things, it should do as few as possible, and ideally they should
    be limited to safer things (earlier in the list)
  - function vs. routine vs. procedure

- capabilities of data structures
  - is it mutable?

- 1% of the code needs 99% of the optimization
  - most of the time, performance doesn't matter. A small % of the time, it matters a *lot*.

- the architecture of a CLI
- the architecture of a compiler
- the architecture of a web app
- the architecture of Unix
