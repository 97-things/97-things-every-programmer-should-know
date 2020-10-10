# Implicit Dependencies Are also Dependencies

Once upon a time a project was developed in two countries. It was a large project with functionality spread across different computers. Each development site became responsible for the software running on one computer, had to fulfill its share of requirements and do its share of testing. The specification of the communication protocol became an early architectural cornerstone.

A few months later, each site declared victory: The software was finished! The integration team took over and plugged everything together. It seemed to work. A bit. Not much though: As soon as the most common scenarios were covered and the more interesting scenarios were tested, the interaction between the computers became unreliable.

Confronted with this finding, both teams held up the interface specification and claimed their software conformed to it. This was found to be true. Both sides declared victory, again. No code was changed, and they developed happily ever after.

The moral is that you have more dependencies than all your attempts for decoupling will let you assume you have.

Software components have dependencies, more so in large projects, even more when you strive to increase your code reuse. But that doesn't mean you have to like them: Dependencies make it hard to change code. Whenever you want to change code others depend on, you will encounter discussion and extra work, and resistance from other developers who would have to invest their time. The counterforces can become especially strong in environments with a lengthy development micro cycle, such as C++ projects or in embedded systems.

Many technical approaches have been adopted to reduce suffering from dependencies. On a detailed level, parameters are passed in a string format, keeping the interface technically unchanged, even though the interpretation of the string's contents changes. Some shift in meaning could be expressed in documentation only; technically the client's software update could happen asynchronously. At a larger scale, component communication replaces direct interface calls by a more anonymous bus where you do not need to contact your service yourself. It just needs to be out there somewhere.

These techniques actually make it harder to spot the underlying implicit dependencies. Let's rephrase the moral a bit: Obfuscated dependencies are still dependencies.

Source-level or binary independence does not relieve you or your team from dependency management. Changing an interface parameter's meaning is the same as changing the interface. You may have removed a technical step such as compilation, but you have not removed the need for redeployment. Plus, you've added opportunities for confusion that will boomerang during development, test, integration, and in the field — returning when you least expect it.

Looking at sound advice from software experts, you hear Fred Brooks talking you into conceptual integrity, Kent Beck urging _once and only once_, and the Pragmatic Programmers advising you to keep it DRY (Don't Repeat Yourself). While these concepts increase the clarity of your code and work against obfuscation, they also increase your technical dependencies — those that you want to keep low.

The moral is really about: Application dependencies are the dependencies that matter.

Regardless of all technical approaches, consider all parts of your software as dependent that you need to touch synchronously, in order to make the system run correctly. Architectural techniques to separate your concerns, all technical dependency management will not give you the whole picture. The implicit application dependencies are what you need to get right to make your software work.

By [Klaus Marquardt](http://programmer.97things.oreilly.com/wiki/index.php/Klaus_Marquardt)
