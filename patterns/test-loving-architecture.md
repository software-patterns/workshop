# Test-loving Architecture

---

**To build steadily on our abilities, step by step—that is the goal of engineering.**

But too often we become mired in intellectual traps of our own making.
The complexity of the systems we build weighs on us until, with a sigh,
we throw the whole mess away and start over.

We cannot rely solely on our feelings to prevent this from happening.
When we start to feel the burden of complexity, it is almost too late
to save the system. Heroic effort is usually required to pull back from
the brink at that point.

Instead, we have to clean up the code as we work, refactoring it for
simplicity and clarity.

But many disciplined engineers shudder at the thought of refactoring this way,
because it means making changes—often drastic changes—to code that is already working.

To mitigate the obvious risks entailed by fixing what "ain't broke", we need to
be able to check our work for mistakes. We need automated tests that we can
run before and after every refactor, to reassure us that we have not
changed the behavior of the code.

But automated tests have their own problems.
[They may actually force the code to be more complicated, to accommodate the
tests](https://dhh.dk//2014/test-induced-design-damage.html).
[They may micromanage how the code does its work, rather than expressing goals and leaving
the implementation to unfold naturally](https://rbcs-us.com/documents/Why-Most-Unit-Testing-is-Waste.pdf).
They may have to be thrown away and rewritten whenever the code changes—what a waste!
And finally, and most distressingly, they may be so slow that no one runs
them while refactoring.
These types of tests do not help us avoid complexity. But they are all too common.

To escape these problems, we must realize this essential truth: code that is designed
to be tested is structured in a fundamentally different way from code that is
merely *designed*. The differences are not incremental or superficial. They are overriding
and pervasive. They permeate every level of detail and every facet of the design.
To test well, we must architect code, from the very beginning, in an entirely different
way from what "traditional" design thinking tells us to do.

The patterns that tell us how to form these designs comprise a *test-loving architecture*.

Thanks to Matt Parker for [the post](https://builttoadapt.io/why-tdd-489fdcdda05e)
that formed the structure of the beginning of this introduction.

**{Solution instructions}**

[Gary Bernhardt: "Test Isolation Is About Avoiding Mocks"](https://www.destroyallsoftware.com/blog/2014/test-isolation-is-about-avoiding-mocks)

## Examples

- Though it fails to achieve 300ms test runs, [Verse](https://github.com/benchristel/verse) exhibits
  a test-loving architecture, in which the core logic of the app is partitioned off from
  side-effecting code, and can therefore be tested without any test doubles.

---

{References to smaller patterns}
