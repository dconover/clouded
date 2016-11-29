Documentation Driven Development

June 18, 2014
I’m by no means the first to propose this approach: I first heard the phrase
“Readme Driven Development” from Tom Preston-Werner in 2010, and there he
referenced Documentation Driven Development:

It’s important to distinguish Readme Driven Development from Documentation
Driven Development. RDD could be considered a subset or limited version of DDD.

A quick google(v.) gives me various results for “documentation driven development”:

SpliceIt! dedicated a page of their documentation to DDD in 2006 

Dave Lempers
wrote about DDD on a MSDN blog in 2009

Frances Berriman talks about Documentation-Driven Design for APIs for 24ways in
2010 …and that’s just from the first page of results!

So lets be clear: I’m not claiming to have invented anything here; I’m just
distilling the various sources into my own thoughts.

I recently got around to reading The Year Without Pants by Scott Berkun, which
details his actually-more-than-a-year working for Automattic. When he was
describing a general workflow for updating WordPress.com, this caught my
attention:

Write a launch announcement and a support page. Most features are announced to
the world after they go live on WordPress.com . But long before launch, a draft
launch announcement is written. This sounds strange. How can you write an
announcement for something that doesn’t exist? The point is that if you can’t
imagine a compellingly simple explanation for customers, then you don’t really
understand why the feature is worth building. Writing the announcement first is
a forcing function. You’re forced to question if your idea is more exciting for
you as the maker than it will be for your customer. If it is, rethink the idea
or pick a different one.

This reminded me of Tom Preston-Werner’s approach, and set me thinking about
the problem again.

A README file or launch announcement (or release note) are user facing, but
users aren’t our only audience. If writing those things first help us distil
our thoughts about what we are going to deliver to our users, then doing the
same thing for our commit messages or – taking it to the extreme – comments
will help us stay focused too. This can be particularly relevant when fixing
bugs/issues/defects, as you will generally go into them with a clear idea of
what you are going to do to address them.

Of course, just like TDD isn’t always practical – e.g., exploratory spikes – so
too can DDD not always be used. Nor should your documentation be set in stone:
good documentation lives and breathes alongside the code.
