# List of Code Smells

This is my attempt to assemble a prioritized list of code
smells.

By *prioritized*, I mean that if you are in a situation
where the only way to remove a high-priority smell is to
create a lower-priority smell, you should go ahead and
remove the existing smell. However, you should not remove a
low-priority smell if doing so would create a
higher-priority smell.

Many of these come from [The C2 Wiki](http://wiki.c2.com/?CodeSmell).

# Unprioritized Smells Are Below

## Parallel Concepts (generalization of Parallel Hierarchies)

e.g. User : Product :: UserView : ProductView
e.g. main_pipeline.yml : main_config.yml :: dev_pipeline.yml : dev_config.yml

## Duplication

## Long Method

## Partial Value (opposite of Whole Value)

## Casual Mutation

## Feature Envy

## Multiple Responsibilities

## Deep Call Tree

## Switch on Type

## Unused Parameter

Often in tests we'll pass null for parameters that aren't
used in that case. If a parameter sometimes isn't used, it
hints that the class has too many responsibilities. If the
parameters are cohesive, you can extract an object to hold
them.

## Code Generation

## Similar Names for Different Things

## Different Names for the Same Thing

## Parameter Clump

## Methods With No Messages To Self

methods that don't use any of the instance variables of an
object aren't really methods, are they? They're more like
utility functions and should potentially be extracted as
such.

## Null Values

## Class With No Instance Variables

a class that doesn't store any data isn't really a class, is
it? It's just a container for a collection of
loosely-associated procedures.

## Doc Comments

if no one reads them, they were a waste of time to write.

if people *do* read them, something is wrong with the code
and/or tests.

## Comments that reiterate code

comments that just repeat what the code already says,
without explaining why things are being done a certain way.

## Law of Demeter Violation

## Complex Control Flow

## Imbalanced Abstraction

## Connascence of Value

## Connascence of Position

## God Object
