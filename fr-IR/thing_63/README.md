# Own (and Refactor) the Build

It is not uncommon for teams that are otherwise highly disciplined about coding practices to neglect build scripts, either out of a belief that they are merely an unimportant detail or from a fear that they are complex and need to be tended to by the cult of release engineering. Unmaintainable build scripts with duplication and errors cause problems of the same magnitude as those in poorly factored code.

One rationale for why disciplined, skilled developers treat the build as something secondary to their work is that build scripts are often written in a different language than source code. Another is that the build is not really "code." These justifications fly in the face of the reality that most software developers enjoy learning new languages and that the build is what creates executable artifacts for developers and end users to test and run. The code is useless without being built, and the build is what defines the component architecture of the application. The build is an essential part of the development process, and decisions about the build process can make the code and the coding simpler.

Build scripts written using the wrong idioms are difficult to maintain and, more significantly, improve. It is worth spending some time to understand the right way to make a change. Bugs can appear when an application is built with the wrong version of a dependency or when a build-time configuration is wrong.

Traditionally testing has been something that was always left to the "Quality Assurance" team. We now realize that testing as we code is necessary to being able to deliver value predictably. In much the same way, the build process needs to be owned by the development team.

Understanding the build can simplify the entire development lifecycle and reduce costs. A simple-to-execute build allows a new developer to get started quickly and easily. Automating configuration in the build can enable you to get consistent results when multiple people are working on a project, avoiding an "it works for me" conversation. Many build tools allow you to run reports on code quality, letting you to sense potential problems early. By spending time understanding how to make the build yours, you can help yourself and everyone else on your team. You can focus on coding features, benefiting your stakeholders and making work more enjoyable.

Learn enough of your build process to know when and how to make changes. Build scripts are code. They are too important to be left to someone else, if for no other reason than because the application is not complete until it is built. The job of programming is not complete until we have delivered working software.

By [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)