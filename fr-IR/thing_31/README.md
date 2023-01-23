# Don't Touch that Code!

It has happened to everyone of us at some point. Your code was rolled on to the staging server for system testing and the testing manager writes back that she has hit a problem. Your first reaction is "Quick, let me fix that — I know what's wrong."

In the bigger sense, though, what is wrong is that as a developer you think you should have access to the staging server.

In most web-based development environments the architecture can be broken down like this:

- Local development and unit testing on the developer's machine
- Development server where manual or automated integration testing is done
- Staging server where the QA team and the users do acceptance testing
- Production server

Yes, there are other servers and services sprinkled in there, like source code control and ticketing, but you get the idea. Using this model, a developer — even a senior developer — should never have access beyond the development server. Most development is done on a developer's local machine using their favorite blend of IDEs, virtual machines, and an appropriate amount of black magic sprinkled over it for good luck.

Once checked into SCC, whether automatically or manually, it should be rolled over to the development server where it can be tested and tweaked if necessary to make sure everything works together. From this point on, though, the developer is a spectator to the process.

The staging manager should package and roll the code to the staging server for the QA team. Just like developers should have no need to access anything beyond the development server, the QA team and the users have no need to touch anything on the development server. If it's ready for acceptance testing, cut a release and roll, don't ask the user to "Just look at something real quick" on the development server. Remember, unless you are coding the project by yourself, other people have code there and they may not be ready for the user to see it. The release manager is the only person who should have access to both.

Under no circumstances — ever, at all — should a developer have access to a production server. If there is a problem, your support staff should either fix it or request that you fix it. After it's 
checked into SCC they will roll a patch from there. Some of the biggest programming disasters I've been a part of have taken place because someone \**cough*\*me\**cough\** violated this last rule. If it's broke, production is not the place to fix it.

by [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)