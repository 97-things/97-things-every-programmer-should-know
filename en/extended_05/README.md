# Balance Duplication, Disruption, and Paralysis

> "I thought we had fixed the bug related to strange characters in names."

> "Well, it looks like we only applied the fix to names of organizations, not names of individuals."

If you duplicate code, it's not only effort that you duplicate. You also make the same decision about how to handle a particular aspect of the system in several places. If you learn that the decision was wrong, you might have to search long and hard to find all the places where you need to change. If you miss a place, your system will be inconsistent. Imagine if you remember to check for illegal character in some input fields and forgot to check in others.

A system with a duplicated decision is a system that will eventually become inconsistent.

This is the background for the common programmer credo "Don't Repeat Yourself," as the Pragmatic Programmers say, or "Once and only once," which you will hear from Extreme Programmers. It is important not to duplicate your code. But should you duplicate the code of others?

The larger truth is that we have choice between three evils: duplication, disruption, and paralysis.

* We can duplicate our code, thereby duplicating effort and understanding, and being forced to hunt down bugs twice. If there's only a few people in a team and you work on the same problem, eliminating duplication should almost always be way to go.

* We can share code and affect everyone who shares the code every time we change the code to better fit our needs. If this is a large number of people, this translates into lots of extra work. If you're on a large project, you may have experienced code storms — days where you're unable to get any work done as you're busy chasing the consequences of other people's changes.

* We can keep shared code unchanged, forgoing any improvement. Most code I — and, I expect, you — write is not initially fit for its purpose, so this means leaving bad code to cause more harm.

I expect there is no perfect answer to this dilemma. When the number of people involved is low, we might accept the noise of people changing code that's used by others. As the number of people in a project grows, this becomes increasingly painful for everyone involved. At some time, large projects start experiencing paralysis.

The scary thing about code paralysis is that you might not even notice it. As the impact of changes are being felt by all your co-workers, you start reducing how frequently you improve the code. Gradually, your problem drifts away from what the code supports well, and the interesting logic starts to bleed out of the shared code and into various nooks and crannies of your code, causing the very duplication we set out to cure. Although domain objects are obvious candidates for broad reuse, I find that their reusable parts usually limit themselves to data fields, which means that reused domain objects often end up being very anemic.

If we're not happy with the state of the code when paralysis sets in, it might be that there's really only one option left: To eschew the advice of the masters and duplicate the code.

By [Johannes Brodwall](http://programmer.97things.oreilly.com/wiki/index.php/Johannes_Brodwall)
