# Shallow Trees

Hierarchies of all kinds—[people in a team](./community-of-peers.md),
dependencies of a package, and functions in a call graph—should be
shallow and wide.

---

**Deep hierarchies are expensive to traverse.**

If you're looking up a node in a tree, you usually want the tree to be shallow, because this minimizes
the number of nodes you have to examine.

If communications between two nodes in a tree must go through their common ancestor, you likewise want 
the tree to be shallow, to minimize the number of nodes that have to pass along the communication.

If a node in an immutable persistent data structure needs to be changed, a new node must be created for
each of its ancestors. Using a shallow tree structure minimizes memory allocations.

**Shallow hierarchies minimize the cost of change and communication.**

There is a limit, of course, to how shallow a hierarchy can be and still be an effective hierarchy.
Depending on the type of system, branching factors of between 5 and 100 can work well.

In general, if you have a choice between expanding a tree "horizontally" (making new nodes siblings of
existing nodes) and expanding "vertically" (making new nodes children of an existing leaf), choose
horizontal expansion.

## Examples

This pattern manifests in many places:

- Company org charts
- Microservice architectures
- Package dependency graphs
- Function call graphs
- [Persistent data structures](http://wiki.jvmlangsummit.com/images/a/ab/HickeyJVMSummit2009.pdf)
- Directories and files in a project
- Namespacing of code units
- Navigation menus

Its ubiquity makes me think that it just might be 
one of the fundamental properties of [living structure](http://www.natureoforder.com/overview.htm)
in information systems.

---

{References to smaller patterns}
