# 300-millisecond Test Suite

[Automated tests](./automated-tests.md) are only useful when
programmers run them. Ideally, all the tests run on every change
to the code. For this to be tenable, test runs must be fast.
We have found that the subjectively optimal
amount of time between editing code and seeing test results is
about 300 milliseconds.

---

**{Problem Statement}**

{Problem description}

**{Solution instructions}**

- Choose a fast test framework. Write your own if you can't find one fast enough; in
  many languages this isn't too hard. A framework you write yourself is likely to be
  simpler, and therefore faster, than anything on the market.
- In statically-compiled languages, compilation often takes far longer than running the tests.
  In interpreted languages, just starting the runtime environment can take more than 300ms.
  Structure your code for incremental compilation (if it is compiled) or hot-swapping of modules
  into the test runtime (if it is dynamic).

Why 300ms? Why not strive for even faster tests?
- Tests that take less than 100ms to run feel instantaneous.
But this instantaneous feedback feels oppressive, like the computer
is not giving you time to finish your thought. In fact, when tests
take very short amounts of time to run, the programmer's
peace of mind is best served if an artificial delay is inserted
before displaying the test results. See [this commit](https://github.com/benchristel/verse/commit/7d996d496d39e07ca92461060a6b4e16d8c50df9).

## Examples

{Examples go here}

---

In order for the tests to remain both fast and intelligible, the code being tested
should have a [Test-loving Architecture](./test-loving-architecture.md)
