# Respect the Software Release Process

Presuming that you are writing software for the benefit of others as well as yourself, it has to get into the hands of your "users" somehow. Whether you end up rolling a software installer shipped on a CD or deploying the software on a live web server, this is the important process of creating a _software release_.

The software release process is a critical part of your software development regimen, just as important as design, coding, debugging, and testing. To be effective your release process must be: simple, repeatable, and reliable.

Get it wrong, and you will be storing up some potentially nasty problems for your future self. When you construct a release you must:

* Ensure that you can get the exact same code that built it back again from your source control system. (You do use source control, don't you?) This is the only concrete way to prove which bugs were and were not fixed in that release. Then when you have to fix a critical bug in version 1.02 of a product that's five years old, you can do so.
* Record exactly how it was built (including the compiler optimization settings, target CPU configuration, etc.). These features may have subtly affects how well your code runs, and whether certain bugs manifest.
* Capture the build log for future reference.

The bare outline of a good release process is:

* Agree that it's time to spin a new release. A formal release is treated differently to a developer's test build, and should **never** come from an existing working directory.
* Agree what the "name" of the release is (e.g., "5.06 Beta1" or "1.2 Release Candidate").
* Determine exactly what code will constitute this release. In most formal release processes, you will already be working on a _release branch_ in your source control system, so it's the state of that branch right now.
* Tag the code in source control to record what is going into the release. The tag name must reflect the release name.
* Check out a virgin copy of the entire codebase at that tag. **Never** use an existing checkout. You may have uncommitted local changes that change the build. Always tag _then_ checkout the tag. This will avoid many potential problems.
* Build the software. This step **must not** involve hand-editing any files at all, otherwise you do not have a versioned record of exactly the code you built.
* Ideally, the build should be automated: a single button press or a single script invocation. Checking the mechanics of the build into source control with the code records unambiguously how the code was constructed. Automation reduces the potential for human error in the release process.
* Package the code (create an installer image, CD ISO images, etc.). This step should also be automated for the same reason.
* Always test the newly constructed release. Yes, you tested the code already to ensure it was time to release, but now you should test this "release" version to ensure it is of suitable release quality.
* Construct a set of "Release notes" describing how the release differs from the previous release: the new features and the bugs that have been fixed.
* Store the generated artifacts and the build log for future reference.
* Deploy the release. Perhaps this involves putting the installer on your website and sending out memos or press releases to people who need to know. Update release servers as appropriate.

This is a large topic tied intimately with configuration management, testing procedures, software product management, and the like. If you have any part in releasing a software product you really must understand and respect the sanctity of the software release process.

By [Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)
