# Empirical Software Development

I've been experimenting with an extension of TDD that I call "empirical software development"
(needs a better name). In empirical software development, you proactively refactor ("prefactor") to
"make the change easy, and then make the easy change". At each refactoring step, you do
half the refactoring and run the tests. The resulting failure proves the code you just changed
is covered. Then you complete the refactor, at which point all the tests should go green.
The process of test-driving new functionality works as in TDD.

Here is the empirical software development process as an algorithm:

1. Propose a small change to either the code or the tests.
2. Hypothesize a change to the test output or program output that will result from writing that code.
   Prefer making hypotheses about test output, whenever you can.

   If you do not think your proposed change will alter the output, go back to
   step 1 and propose something else.
   
   If any test is currently failing and your hypothesis is not that the tests
   will pass after your change, go back to step 1 and propose something else.
3. Make the change.
4. Observe the output.
   1. If the output refutes your hypothesis: debug until you understand why. Revert your change
      and go back to step 1.
   2. If the output confirms your hypothesis: keep your change and go back to step 1.

Empirical software development maximizes fast, isolated unit tests and avoids slow tests (it has to,
since your ability to run the tests on every tiny change is predicated on having a fast test suite.)
Rather than automate integration tests, empirical software development prefers manual testing
of integration points and system-level functionality. This helps avoid "flaky test syndrome" and
also ensures the software's continued ease of manual operation.

The potential downsides of not having automated integration tests (e.g. lack of regression coverage)
are minimized by structuring the code so that the unit tests can cover as much functionality as possible.
Any code not covered by automated tests should be "obvious" straightline procedures for which
regression test coverage would have little value.
