# Verbose Logging Will Disturb Your Sleep

When I encounter a system that has already been in development or production for a while, the first sign of real trouble is always a dirty log. You know what I'm talking about. When clicking a single link on a normal flow on a web page results in a deluge of messages in the only log that the system provides. Too much logging can be as useless as none at all.

If your systems are like mine, when your job is done someone else's job is just starting. After the system has been developed, it will hopefully live a long and prosperous life serving customers. If you're lucky. How will you know if something goes wrong when the system is in production, and how will you deal with it?

Maybe someone monitors your system for you, or maybe you will monitor it yourself. Either way, the logs will be probably part of the monitoring. If something shows up and you have to be woken up to deal with it, you want to make sure there's a good reason for it. If my system is dying, I want to know. But if there's just a hiccup, I'd rather enjoy my beauty sleep.

For many systems, the first indication that something is wrong is a log message being written to some log. Mostly, this will be the error log. So do yourself a favor: Make sure from day one that if something is logged in the error log, you're willing to have someone call and wake you in the middle of the night about it. If you can simulate load on your system during system testing, looking at a noise-free error log is also a good first indication that your system is reasonably robust. Or an early warning if it's not.

Distributed systems add another level of complexity. You have to decide how to deal with an external dependency failing. If your system is very distributed, this may be a common occurrence. Make sure your logging policy takes this into account.

In general, the best indication that everything is all right is that the messages at a lower priority are ticking along happily. I want about one INFO-level log message for every significant application event.

A cluttered log is an indication that the system will be hard to control once it reaches production. If you don't expect anything to show up in the error log, it will be much easier to know what to do when something does show up.

By [Johannes Brodwall](http://programmer.97things.oreilly.com/wiki/index.php/Johannes_Brodwall)