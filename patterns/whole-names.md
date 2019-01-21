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

Here is an example of a name that is *not* whole: `fancy_roundup` in Python's [`node.c`](http://svn.python.org/projects/python/branches/py3k/Parser/node.c):

```
static int
fancy_roundup(int n)
{
    /* Round up to the closest power of 2 >= n. */
    int result = 256;
    assert(n > 128);
    while (result < n) {
        result <<= 1;
        if (result <= 0)
            return -1;
    }
    return result;
}
```

I first saw this code used as an example in Anjana Vakil's talk ["Programming Across Paradigms"](https://www.youtube.com/watch?v=Pg3UeB-5FdA).

The name and the implementation are tightly coupled to the context in which `fancy_roundup`
is used. Though the algorithm could easily be made to work for any `n`, it refuses to operate
on any `n` less than or equal to 128. If not for the `assert` and `result = 256`, the function could simply be
renamed to something like `closest_power_of_2_above(n)` or `power_of_2_at_least(n)`. But the
restriction expressed by the `assert` is preventing the function and its name from being whole.

This unwholeness may have some advantages. If we know that `n` is always going to be greater than 128,
it's a waste of time to go through 8 extra loop iterations on every call to get `result` up to 256.
But it does mean that this algorithm cannot be used outside its current context without [repair](https://patterns-dev.github.io/patterns/newpat/newpat104/newpat104.htm#pat104).

However, performance and generality could both be achieved by changing the assertion to a conditional:

```
static int
power_of_2_above(int n)
{
    int result = n > 128 ? 256 : 1;
    while (result < n) {
        result <<= 1;
        if (result <= 0)
            return -1;
    }
    return result;
}
```

**Name functions after what they do or what they return, not how they are used. Ask
yourself "if I could see only this function, would the names make sense?"**

{Solution description}

## Examples

{Examples go here}

---

{References to smaller patterns}
