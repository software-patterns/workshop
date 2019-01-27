# Four-Part Documentation

This pattern tells you how to structure documentation so users of
your software can find the information they need.

It is based on the blog post ["What Nobody Tells You About Documentation"](https://www.divio.com/blog/documentation/)
by Divio's Daniele Procida.

---

**A lot of [software documentation in the real world](https://docs.mongodb.com/manual/introduction/) reads like a list of
features, with instructions on how to use each one and (hopefully) how it
relates to the larger whole.**

The problem is, people who are learning how to use a program do not necessarily
know what feature they need to focus on. Their workflow may span many features that
they need to integrate. They may even be total beginners who do not yet have a workflow
in mind.

The documentation may in fact make an honest effort to accommodate these types of users—by
adorning each feature-centric section with tutorials, how-to-guides, and in-depth
technical explanation. But that only makes things worse. By jumbling everything together like
this, the documentation ends up working well for exactly no one. It becomes very difficult
to find any given piece of information, or to assemble a consistent picture of the whole
from the fragments.

**Divide documentation into four overarching sections: Tutorials, How-to Guides, Explanations,
and Reference.**

Each of these sections accommodates the learner during some phase of their journey from novice
to master.

**Tutorials** are for those who are brand-new to the software. They tell you how to use the
software for a simple, concrete use case. The focus is on learning by doing.

**How-to Guides** are recipes for accomplishing specific goals that crop up frequently in the
real world. Intermediate users will refer often to this section. In many real-world scenarios,
Stack Overflow ends up being the *de facto* repository for how-to guides.

**Explanations** contain technical background: the "how" and "why" of the software. In this section,
people can become more comfortable with the software by understanding its organizing principles.

Finally, the **Reference Section** lists the individual units of action—buttons, menus, commands,
APIs—that even expert users will need to look up from time to time. If all is done well, the
reference section can be utterly precise, clean, and free of embellishment. A few well-placed
[examples](./many-high-quality-examples.md) in this section go a long way.

## Examples

My favorite example of great documentation is the
[Sim City 2000 Manual](https://classicreload.com/sites/default/files/sim-city-2000-manual.pdf).
Though it lacks how-to guides (being a game, it doesn't really have fixed "workflows")
it shows you how you can implement the other three parts of this pattern.

---

Support Four-Part Documentation with a [Ubiquitous Domain Language](./ubiquitous-domain-language.md)
so it is always clear what you are talking about. Infuse all parts of the documentation with
[Many High-Quality Examples](./many-high-quality-examples.md) so that readers are exposed early
and often to the patterns that emerge when they use the software well.
