# Whole Names

Within a program made of [many small units](./many-small-units.md) in a
[single namespace](./single-namespace), avoid confusion by insisting that
names be *whole*—that is, true to the nature of the thing named, without
underdescribing or overdescribing.

---

**If we design a program from the top down, the interface of each routine will
be determined by the needs of its first caller. It is tempting to name the
routine after what it means, concretely, to the caller.**

The problem with this approach is that the routine often ceases to be intelligible in
isolation.

> When each method represents a fragment of a concept, the solution becomes incomprehensible.
>
> —[Katrina Owen](https://www.sitepoint.com/whats-in-a-name-anti-patterns-to-a-hard-problem/)

**{Solution instructions}**

{Solution description}

## Examples

{Examples go here}

---

{References to smaller patterns}
