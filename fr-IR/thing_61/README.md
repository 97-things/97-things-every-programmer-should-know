# One Binary

I've seen several projects where the build rewrites some part of the code to generate a custom binary for each target environment. This always makes things more complicated than they should be, and introduces a risk that the team may not have consistent versions on each installation. At a minimum it involves building multiple, near-identical copies of the software, each of which then has to be deployed to the right place. It means more moving parts than necessary, which means more opportunities to make a mistake.

I once worked on a team where every property change had to be checked in for a full build cycle, so the testers were left waiting whenever they needed a minor adjustment (did I mention that the build took too long as well?). I also worked on a team where the system administrators insisted on rebuilding from scratch for production (using the same scripts that we did), which meant that we had no proof that the version in production was the one that had been through testing. And so on.

The rule is simple: *Build a single binary that you can identify and promote through all the stages in the release pipeline.* Hold environment-specific details in the environment. This could mean, for example, keeping them in the component container, in a known file, or in the path.

If your team either has a code-mangling build or stores all the target settings with the code, that suggests that no one has thought through the design carefully enough to separate those features which are core to the application and those which are platform-specific. Or it could be worse: The team knows what to do but can't prioritize the effort to make the change.

Of course, there are exceptions: You might be building for targets that have significantly different resource constraints, but that doesn't apply to the majority of us who are writing "database to screen and back again" applications. Alternatively, you might be living with some legacy mess that's too hard to fix right now. In such cases, you have to move incrementally — but start as soon as possible.

And one more thing: Keep the environment information versioned too. There's nothing worse than breaking an environment configuration and not being able to figure out what changed. The environmental information should be versioned separately from the code, since they'll change at different rates and for different reasons. Some teams use distributed version control systems for this (such as bazaar and git), since they make it easier to push changes made in production environments — as inevitably happens — back to the repository.

By [Steve Freeman](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Freeman)