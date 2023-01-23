# Don't Be Cute with Your Test Data

> *It was getting late. I was throwing in some placeholder data to test the page layout I'd been working on.*

> *I appropriated the members of The Clash for the names of users. Company names? Song titles by the Sex Pistols would do. Now I needed some stock ticker symbols — just some four letter words in capital letters.*

> *I used **those** four letter words.*

> *It seemed harmless. Just something to amuse myself, and maybe the other developers the next day before I wired up the real data source.*

> *The following morning, a project manager took some screenshots for a presentation.**

Programming history is littered with these kinds of war stories. Things that developers and designers did "that no one else would see" which unexpectedly became visible.
The leak type can vary but, when it happens, it can be deadly to the person, team, or company responsible. Examples include:

- During a status meeting, a client clicks on an button which is as yet unimplemented. They are told: "Don't click that again, you moron."
- A programmer maintaining a legacy system has been told to add an error dialog, and decides to use the output of existing behind-the-scenes logging to power it. Users are suddenly faced with messages such as "Holy database commit failure, Batman!" when something breaks.
- Someone mixes up the test and live administration interfaces, and does some "funny" data entry. Customers spot a $1m "Bill Gates-shaped personal massager" on sale in your online store.

To appropriate the old saying that "a lie can travel halfway around the world while the truth is putting on its shoes," in this day and age a screw-up can be Dugg, Twittered, and Flibflarbed before anyone in the developer's timezone is awake to do anything about it.

Even your source code isn't necessarily free of scrutiny. In 2004, when a tarball of the Windows 2000 source code made its way onto file sharing networks, some folks merrily grepped through it for profanity, insults, and [other funny content](http://www.kuro5hin.org/story/2004/2/15/71552/7795). (The comment `// TERRIBLE HORRIBLE NO GOOD VERY BAD HACK` has, I will admit, become appropriated by me from time to time since!)

In summary, when writing any text in your code — whether comments, logging, dialogs, or test data — always ask yourself how it will look if it becomes public. It will save some red faces all round.

By [Rod Begbie](http://programmer.97things.oreilly.com/wiki/index.php/Rod_Begbie)