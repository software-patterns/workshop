## Quality and agile software development

Agile teams must rapidly create working software, and keep
it working, in the face of changing requirements. To such
teams, the ability to read, comprehend, and change code
quickly and accurately is of paramount importance. While I
will touch on many different aspects of software
development, the main focus of this book will be the process
of understanding and improving code.

When your team has to deliver high-quality results early and
often, you come to rely on efficient, accurate
communication. For software developers, that invariably
means making the code itself a medium of communication.
Documentation and even code comments quickly go out of date
unless they're painstakingly maintained. Code, on the other
hand, can't lie. It always describes exactly what the
software actually does. So the most efficient communication
about code happens when the code can simply speak for
itself.

Of course, not all code communicates well. Often, divining
"what the software actually does" from the code requires
deep technical knowledge, intuition, and more than a little
luck. Many codebases seem to actively impede understanding.
They are "code" in the cryptographer's sense as well as the
programmer's: deliberately obfuscated, impenetrable, arcane.

And yet, a few rare codebases actually do help us understand
and change them. When I work with this kind of code, I feel
like the people who came before me have my back; like their
work is supporting me instead of dragging me down. A
powerful feeling of community and shared responsibility can
arise out of code like this, a feeling that can enable whole
teams to do better work.

The thing that these better codebases have—the thing that
generates feelings of community, pride, shared ownership,
and responsibility—we call *code quality*.

But although we can name code quality, and recognize it by
the feeling it creates, it is still not clear to most of us
how to create it.

So, in an attempt to grasp what code quality is, we invent
metrics that seem to correlate with it, and then we define
quality in terms of those metrics.

These metrics include:
- cyclomatic complexity (how many different execution paths
  there are through a piece of code)
- test coverage (how much of the code is executed by at
  least one automated test)
- file length (usually measured in lines of code)
- method or function length (usually measured in lines of
  code)
- duplication (how many times similar chunks of code appear
  in the project)

But these metrics capture only the most superficial aspects
of quality, and when we focus on optimizing them, we divert
our attention from quality itself. Indeed, the easiest ways
to optimize the metrics actually make code *worse*.

In the following chapters, I hope to elucidate what code
quality really is, and how it affects the collaboration and
sense of community within a team. I will try to demonstrate,
as concretely as I can, the way I "see" code and manipulate
it in my mind, and how these habits of thought make quality
jump to the fore. I will give you concrete techniques, in
the form of patterns, to make the rote labor of coding
easier so you can focus your attention on quality. And
finally, I will present a process in which to apply these
techniques: one that is general enough to be used by teams
of any size from one to ten people, and flexible enough to
accommodate many different preferences and work styles. The
key to the flexibility of the process is the focus on code
and code quality as primary communication mechanisms of the
team.
