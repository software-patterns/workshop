# Test-loving Architecture

To reap the benefits of a [300-millisecond test suite](./300-ms-test-suite.md),
programmers must structure code so the tests give them a
high degree of confidence in its correctness. But it is nearly impossible
to do this at a fine-grained level unless the high-level design of
the software—the architecture—supports it.

---

**Almost any code, no matter how it is architected, can be unit-tested,
brute-force, by means of test doubles. But it is hard to be confident
in code that is tested this way.**

{Problem description}

**{Solution instructions}**

[Gary Bernhardt: "Test Isolation Is About Avoiding Mocks"](https://www.destroyallsoftware.com/blog/2014/test-isolation-is-about-avoiding-mocks)

## Examples

- Though it fails to achieve 300ms test runs, [Verse](https://github.com/benchristel/verse) exhibits
  a test-loving architecture, in which the core logic of the app is partitioned off from
  side-effecting code, and can therefore be tested without any test doubles.

---

{References to smaller patterns}
