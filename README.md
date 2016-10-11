# func-specs
A collection of functional specifications for software systems I've dreamed up.
Below is a "worksheet" of sorts for brainstorming for a func spec.

**NOTE**: most of these are incomplete

## Functional Specification Worksheet

In the first iteration of this worksheet, I'm going to borrow heavily from
[Joel Spolsky's blog
post](http://www.joelonsoftware.com/articles/fog0000000035.html), and his
joke-y [WhatTimeIsIt.com func
spec](http://www.joelonsoftware.com/articles/WhatTimeIsIt.html).

Answer the prompts, and follow these guidelines:

1. Be Funny, not Boring
2. Write for human understanding
3. Write as simply as possible
4. Review and reread several times
5. Templates considered harmful

The actual content and layout for each one is individually written, in a way that makes sense for that project.

# Functional Specification Prompts, Grouped By Topic

## Preamble

Who wrote this spec? Who is accountable/responsible for it? Spolsky suggests
that one person should own the spec.

When was this version written? Do you have a versioning scheme? How often does
the spec need to be updated? (It should not be "complete" all at once. Let the
document evolve.)

Who can use this spec? Is in an internal, proprietary document, or is it part
of an open/free software project?

Are there any disclaimers you want to include? Spolsky suggests a disclaimer
for "pure self defense." He also includes statements about how "complete" the
spec is.

## Overview

Can you describe what the project is supposed to do in general, high-level
terms? What is the elevator pitch? Is there a flow chart or other illustration
you could include to help explain how this project works? Anything you mention
here should be explained in more detail in the [Details section](#details).

## Scenarios

Who is going to use your project? What problem does your project solve?
Describe your users, their problems, and your solution helps each user in
particular. Each user can be a subsection.

## Non Goals

Are there any features that you are specifically not going to include? What
features would go to waste in your overall solution?

## Details

Look through your overview and scenarios. Each part of your project gets its
own subsection here. Write about every kind of interaction that a user can have
with the project, and what happens next. Write about every failure scenario you
can think of, and what happens next. Each decision you make needs to be
recorded here. The only question you need to ask yourself here is: can I
describe this in detail without mind-numbing dullness?

## Open Issues

If there are questions that are unanswered, or decisions undecided upon, while
you are writing the spec, write about them here. As you close the issues, move
them from here to the appropriate section, then update the spec.

## Site Notes

Is a particular bit of information only for a specific audience? Make side
notes/bars just for those people. If you are in a large organization, create a
template for notes to each department/subteam/whatever.
