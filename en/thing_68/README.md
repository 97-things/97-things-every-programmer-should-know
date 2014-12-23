# Put Everything Under Version Control

Put everything in all your projects under version control. The resources you need are there: free tools, like Subversion, Git, Mercurial, and CVS; plentiful disk space; cheap and powerful servers; ubiquitous networking; and even project-hosting services. After you've installed the version control software all you need in order to put your work in its repository is to issue the appropriate command in a clean directory containing your code. And there are just two new basic operations to learn: you *commit* your code changes to the repository and you update your working version of the project with the repository's version.

Once your project is under version control you can obviously track its history, see who wrote what code, and refer to a file or project version through a unique identifier. More importantly you can make bold code changes without fear — no more commented-out code just in case you need it in the future, because the old version lives safely in the repository. You can (and should) tag a software release with a symbolic name so that you can easily revisit in the future the exact version of the software your customer runs. You can create branches of parallel development: Most projects have an active development branch and one or more maintenance branches for released versions that are actively supported.

A version-control system minimizes friction between developers. When programmers work on independent software parts these get integrated almost by magic. When they step on each others' toes the system notices and allows them to sort out the conflicts. With some additional setup the system can notify all developers for each committed change, establishing a common understanding of the project's progress.

When you set up your project, don't be stingy: place *all* the project's assets under version control. Apart from the source code, include the documentation, tools, build scripts, test cases, artwork, and even libraries. With the complete project safely tucked into the (regularly backed up) repository the damage of losing your disk or data is minimized. Setting up for development on a new machine involves simply checking out the project from the repository. This simplifies distributing, building, and testing the code on different platforms: On each machine a single update command will ensure that the software is the current version.

Once you've seen the beauty of working with a version control system, following a couple of rules will make you and your team even more effective:

- Commit each logical change in a separate operation. Lumping many changes together in a single commit will make it difficult to disentangle them in the future. This is especially important when you make project-wide refactorings or style changes, which can easily obscure other modifications.
- Accompany each commit with an explanatory message. At a minimum describe succinctly what you've changed, but if you also want to record the change's rationale this is the best place to store it.
- Finally, avoid committing code that will break a project's build, otherwise you'll become unpopular with the project's other developers.

Life under a version control system is too good to ruin it with easily avoidable missteps.

By [Diomidis Spinellis](http://programmer.97things.oreilly.com/wiki/index.php/Diomidis_Spinellis)