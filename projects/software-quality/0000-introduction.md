# Introduction

This is a book for software teams.

It is, very intentionally, a book for *everyone* on the team. Product managers, UX designers,
senior engineers, junior engineers—all can, I hope, learn something from this book. If you don't learn anything,
I hope you at least see some of your own thoughts about software represented here, and can
use this book to more confidently communicate those thoughts to other members of your team.
My hope is that this book becomes a kind of hearth, a gathering-place, in which teams
find shared understanding of the work they do every day.

This book is most suitable for teams that must be agile—those that must rapidly create working
software, and keep it working, in the face of changing requirements. To such teams, the ability
to read, comprehend, and change code quickly and accurately is of paramount importance. While
I will touch on many different aspects of software development, the main focus of this book will
be the process of understanding and improving code.

When your team has to deliver high-quality results early and often, you come to rely on efficient,
accurate communication. For software developers, that invariably means making the code
itself a medium of communication. Documentation and even code comments go out of date quickly, and so have
to be constantly and painstakingly maintained. Code itself, on the other hand, can't lie. It always describes
exactly what the software actually does.

Of course, that does not mean that understanding code is easy. Often, divining "what the software actually
does" from the code requires deep technical knowledge, intuition, and more than a little luck. Many
codebases seem to actively impede understanding. They are "code" in the cryptographer's sense as well
as the programmer's: deliberately obfuscated, impenetrable, arcane.

And yet, a few rare codebases actually do help us understand and change them. When I work with this kind
of code, I feel like the people who came before me have my back; like their work is supporting me instead of
dragging me down. A powerful feeling of community and shared responsibility can arise out of code
like this, a feeling that can enable whole teams to do better work.

But what exactly "better work" means, when it comes to code, is a subject of debate, and opinions
on this point can and do turn good code sour. The thing that intelligible code has, and that obfuscated
code lacks, we call "code quality". In an attempt to grasp and pin down this quality, we invent metrics that
seem to correlate with it, and then we define quality in terms of those metrics.

Such metrics include:
- cyclomatic complexity (how many different execution paths there are through a piece of code)
- test coverage (how much of the code is executed by at least one automated test)
- file length (usually measured in lines of code)
- method or function length (usually measured in lines of code)
- duplication (how many times similar chunks of code appear in the project)

But these metrics capture only the most superficial aspects of quality, and when we focus on optimizing
them, we divert our attention from quality itself. Indeed, the easiest ways to optimize the metrics
actually make code *worse*.

In the following chapters, I hope to elucidate what code quality really is, and how it affects the
collaboration and sense of community within a team. I will try to demonstrate, as concretely as I can,
the way I "see" code and manipulate it in my mind, and how these habits of thought make quality jump to the fore.
I will give you concrete techniques, in the form of patterns, to make the rote labor of coding easier so you
can focus your attention on quality. And finally, I will present a process in which to apply these techniques:
one that is general enough to be used by teams of any size from one to ten people, and flexible enough to
accommodate many different preferences and work styles. The key to the flexibility of the process is the focus
on code and code quality as primary communication mechanisms of the team.
