# Balanced Contrasts

This pattern tells you how to name things that contrast with one another.

---

**Names often do not stand alone, but form systems in which their parts, or *words*, contrast.
When a contrast forms between a word and the absence of a word, communication suffers.**

For example, I once worked on a system—let's call it `sys-a`—that produced two types of outputs:
"published" outputs, intended for consumption by other systems, and "intermediate" outputs which were fed back into
`sys-a` to produce further outputs. All of the output files lived in one filesystem,
and were bucketed into two overarching directories named `sys-a` and `sys-a-intermediate`.

This led to communication problems. People readily adopted the term "intermediates" to refer to
the files in `sys-a-intermediate`, but it wasn't clear what the files in the `sys-a` directory should be called.
We sometimes called them "published", but that was
confusing because there was a subdirectory `sys-a/published` that contrasted with some other
directories in `sys-a`. We sometimes called them "production", but that was a misnomer too, because
both `sys-a` and `sys-a-intermediates` contained files that were considered "production".

The `sys-a` vs. `sys-a-intermediates` contrast is what I call an *unbalanced contrast*. An unbalanced
contrast is one where a word contrasts with the absence of a word.

Unbalanced contrasts impede communication among the members of a team because one side of the contrast
lacks a codified term that people can easily agree to use. If enough unbalanced contrasts get into a team's
language, their conversations will be mired in a mishmash of malapropisms as they struggle to
fit names to concepts that have none.

**Always create naming contrasts that are balanced.**

Sometimes, this will be painful. You will often, as you evolve a system, need to split one concept into
two, creating a distinction where none previously existed. The path of least resistance here is to
give the existing name to one branch of the distinction and create a new name for the other branch.
But that is a false expediency. The more widely the names are used, the more you will pay (in time lost
to confusing communication) for an unbalanced contrast.

If necessary, use some kind of alias (such as a symbolic link or a wrapper function) to avoid breaking
clients of your system who continue to use the old, contrast-free name. Deprecate the old name and
gradually wean clients off it. Then you can remove the old name.

## Examples

{Examples go here}

---

{References to smaller patterns}
