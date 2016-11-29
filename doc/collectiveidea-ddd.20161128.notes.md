


```
On Documentation-Driven Development

Putting a bit more emphasis on your README

April 21, 2014
I love designing and developing APIs. In building a great API, the design and
development processes demand equal attention. The problem is that popular
development approaches don’t emphasize the design process. You may be familiar
with the concepts of test-driven development (wiki) and behavior-driven
development (wiki), but let’s talk about the lesser-known concept of
“documentation-driven development” (no wiki).
```

```bash
The README

It all starts with the README. Your README is your code’s most important work
of documentation. It has the ability to give a high level view of your code,
communicating its overarching purpose. That purpose is much more difficult to
communicate via code comments.

Tom Preston-Werner, co-founder of GitHub, wrote a fantastic blog post about the
merits of readme-driven development. This approach is your best bet for 90% of
projects.
```


```bash

So, what projects make up the other 10%?

APIs

Designing an API is a special case because you’re often designing for unknowns.
You might not know:

what types of clients will consume the API or their individual preferences the
flow that any given consumer will take through your API endpoints
which information will be most valuable to the consumer
With all of these unknowns, the best thing you can do for yourself and your
consumers is to write your documentation first, as visibly as possible. The
goal is to gather insight and recommendations from your consumers early and
throughout the design process, turning your unknowns into knowns. Changes are
easier and faster to make in documentation than they are in code.
```

"Changes are easier and faster to make in documentation than they are in code."

an example workflow: 
```bash
The workflow is:

Write or update documentation
Write a failing test according to that documentation (red)
Write code to pass the failing test (green)
Refactor
```

```bash
Our Experience

At Collective Idea, documentation-driven development has been wonderful for
writing APIs. We’ve seen several benefits:
```

```bash
Velocity

Oftentimes, we will write an API for a dedicated consumer such as an iOS app.
Writing documentation first provides a space in which server and client teams
can collaborate. The documentation also gives the client team something to work
from before the server team has even implemented the documented endpoints. This
prevents rework and parallelizes the efforts of the server and client teams.
```
work can be parallelized more easily when their exists documentation that 
people outside the project can follow.


```bash
Consistency

Accurate and up-to-date documentation is important for an API, especially a
public API. When writing or updating documentation is a required first step of
your development process, you ensure your documentation is always consistent
with your code.
```


```bash
Transparency

Documentation-driven development elevates writing documentation to the same
level of importance as writing code. As a result, documentation changes are
also included in the peer review process. This gives the reviewer insight into
the “why” behind a set of code changes. Code review is much more effective when
the reviewer has this understanding of purpose.
```
