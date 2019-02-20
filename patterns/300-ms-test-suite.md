# 300-millisecond Test Suite

This pattern tells you when to make your test suite faster (by
rearchitecting your code and testing smaller units) and when you
can afford to let it be slower.

A [Test-Loving Architecture](./test-loving-architecture.md) helps us
eliminate the tedium and human fallibility of checking our work manually.
But automated tests are only useful when
programmers run them. Ideally, all the tests run on every change
to the code. For this to be tenable, test runs must be fast.
*I have found that the subjectively optimal
amount of time between editing code and seeing test results is
about 300 milliseconds. —benchristel*

---

**People who practice test-driven development generally do not run their
tests frequently enough.**

*I've paired with many people at various stages of their journey toward
TDD enlightenment. One thing I notice fairly often is that people do not
run the tests right away when they have written the code that makes a test
pass. They will sit and read over the code they just wrote, to make sure
it is correct, before they run the tests.*

*Now, of course people should think about their code. But [cognition
is a scarce resource](http://seriouspony.com/blog/2013/7/24/your-app-makes-me-fat),
and it seems reasonable to believe your thoughts are more likely to reflect reality when you
think in the presence of empirical feedback from your tests. So run the tests first,
and* then *think.*

*Why don't more people work like this?*

*One simple reason is that tests are often slow. When running the tests creates
a noticeable pause in your work, it feels like a waste of time to run the tests and only
then find your mistake. Much better to make sure the code is right before
investing in a test run.*

*Another possible reason (and this is just conjecture) is that people may feel
uncomfortable seeking feedback, even from emotionless automated tests, especially
in a pairing situation. They may fear that if their thoughts about their code are
proven wrong by the tests, it reflects poorly on them. But that is just one way
of seeing the world.*

> John [McCarthy]’s world is a world of ideas, a world in which ideas don’t belong to anyone,
> and when an idea is wrong, just the idea - not the person - is wrong. A world in
> which ideas are like young birds, and we catch them and proudly show them to our friends.
> The bird’s beauty and the hunter’s are distinct.
>
> Some people won’t show you the birds they’ve caught until they are sure,
> certain, positive that they - the birds, or themselves - are gorgeous, or rare,
> or remarkable. When your mind can separate yourself from your bird, you will share it
> sooner, and the beauty of the bird will be sooner enjoyed.
> And what is a bird but for being enjoyed?
>
> —Richard P. Gabriel, ["The Design of Parallel Programming Languages"](http://dreamsongs.net/10ideas.html)

*The anxiety of running tests evaporates if the tests are fast enough to be run
on every change to the code, without any explicit command by the programmer.
If we don't have to remember to run the tests—if the cost of running them
is so small it doesn't matter—if we can dodge the emotional impact of
a test failure because we "weren't finished yet" and it's just the silly
computer running the tests—then before we know it we will have collected
a menagerie of rare and wonderful birds. —benchristel*

**All the tests for a program should be able to run within 300 milliseconds. Set up your
tools to run all the tests every time there is a pause in your typing.**

- Choose a fast test framework. Write your own if you can't find one fast enough; in
  many languages this isn't too hard. A framework you write yourself is likely to be
  simpler, and therefore faster, than anything on the market.
- In statically-compiled languages, compilation often takes far longer than running the tests.
  In interpreted languages, just starting the runtime environment can take more than 300ms.
  Structure your code for incremental compilation (if it is compiled) or hot-swapping of modules
  into the test runtime (if it is dynamic).

*300 milliseconds may seem like an arbitrary target. Elsewhere, Matt Parker has suggested
["instantaneous"](https://builttoadapt.io/four-goals-of-a-good-test-suite-651b3a4cfd33)
as a good runtime to shoot for. For most of us, instantaneous test runs are a distant fantasy, so
aiming for zero does us no harm. But I have actually had some experience with instantaneous
tests, and I'm not convinced they're such a good goal.*

*I built [Verse](https://github.com/benchristel/verse), in part, to see how my development process would change if I had access
to a truly instantaneous test runner—one that would run all my tests, synchronously, every
time I typed a character that resulted in compilable code. So, for a while, I had access to
zero-millisecond test suites for at least some of my work.*

*And you know what? It wasn't that great.*

*Yes, it was fast. But it was also stressful. Verse shows the test output next to the editor,
and seeing it flicker between red and green as I typed was maddening. I felt like I was a
servant to the tests, not the other way around. Every keystroke was fraught with the
threat of the Red Bar.*

*I had to change something, though I didn't know what. Softer colors? An animation?
In the end I decided to try the simplest and most direct thing that could possibly
work: I would only run the tests if there had been no changes to the code for 300 milliseconds.
[Here](https://github.com/benchristel/verse/commit/7d996d496d39e07ca92461060a6b4e16d8c50df9) is the commit.*

*I honestly did not expect this short delay to have much of an impact. But just like that, all the
stress I'd felt with instantaneous tests was gone. I went back and forth a few times just to be sure.*

*I experimented with other amounts of delay, too. YMMV if you type slowly, but for me, 300 milliseconds
just feels right somehow. —benchristel*


## Examples

{Examples go here}

---

Keep your tests small and simple with [Many Small Units](./many-small-units.md).
