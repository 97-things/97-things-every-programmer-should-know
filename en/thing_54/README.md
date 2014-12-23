# The Longevity of Interim Solutions

Why do we create interim solutions?

Typically there is some immediate problem to solve. It might be internal to the development team, some tooling that fills a gap in the tool chain. It might be external, visible to end users, such as a workaround that addresses missing functionality.

In most systems and teams you will find some software that is somewhat dis-integrated from the system, that is considered a draft to be changed sometime, that does not follow the standards and guidelines that shaped the rest of the code. Inevitably you will hear developers complaining about these. The reasons for their creation are many and varied, but the key to an interim solution's success is simple: It is useful.

Interim solutions, however, acquire inertia (or momentum, depending on your point of view). Because they are there, ultimately useful and widely accepted, there is no immediate need to do anything else. Whenever a stakeholder has to decide what action adds the most value, there will be many that are ranked higher than proper integration of an interim solution. Why? Because it is there, it works, and it is accepted. The only perceived downside is that it does not follow the chosen standards and guidelines — except for a few niche markets, this is not considered to be a significant force.

So the interim solution remains in place. Forever.

And if problems arise with that interim solution, it is unlikely there will be provision for an update that brings it into line with accepted production quality. What to do? A quick interim update on that interim solution often does the job. And will most likely be well received. It exhibits the same strengths as the initial interim solution... it is just more up to date.

Is this a problem?

The answer depends on your project, and on your personal stake in the production code standards. When the systems contains too many interim solutions, its entropy or internal complexity grows and its maintainability decreases. However, this is probably the wrong question to ask first. Remember that we are talking about a solution. It may not be your preferred solution — it is unlikely to be anyone's preferred solution — but the motivation to rework this solution is weak.

So what can we do if we see a problem?

1. Avoid creating an interim solution in the first place.
- Change the forces that influence the decision of the project manager.
- Leave it as is.

Let's examine these options more closely:

1. Avoidance does not work in most places. There is an actual problem to solve, and the standards have turned out to be too restrictive. You might spend some energy trying to change the standards. An honorable albeit tedious endeavor... and that change will not be effective in time for your problem at hand.
- The forces are rooted in the project culture, which resists volitional change. It could be successful in very small projects — especially if it's just you — and you just happen to clean the mess without asking in advance. It could also be successful if the project is such a mess that it is visibly stalled and some time for cleaning up is commonly accepted.
- The status quo automatically applies if the previous option does not.

You will create many solutions, some of them will be interim, most of them will be useful. The best way to overcome interim solutions is to make them superfluous, to provide a more elegant and useful solution. May you be granted the [serenity](http://en.wikipedia.org/wiki/Serenity_prayer) to accept the things you cannot change, courage to change the things you can, and wisdom to know the difference.

By [Klaus Marquardt](http://programmer.97things.oreilly.com/wiki/index.php/Klaus_Marquardt)