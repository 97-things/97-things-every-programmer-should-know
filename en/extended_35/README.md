# Know When to Fail

Almost all applications have some external resources they cannot do without. For instance, a server-side application that handles a membership list is probably not all that useful without access to wherever the list of members is stored.

When critical resources are not available on startup, the application should print an error message and stop immediately. If the application continues running, there will probably be a very long list of related errors in the log, which will in turn confuse any debugging attempts.

A while back, a consultancy in Norway won a contract for an application worth $500,000. When the customer became dissatisfied and threatened legal action, some more senior developers were told to have a look. They found that most of the customer frustration was caused by a mangled installation, and 80% of the application was missing any attempt at error handling. It was almost impossible to get the application operational without access to the source code because all exceptions were thrown away. After the two most pressing issues were fixed, the customer relationship was saved.

The usual response to complaints about hard-to-track errors is "we will fix them in the next version." Only they won't be fixed. The team will be too busy trying to sort out all of the misleading error reports from whoever tried to make the application work. The boss will notice, and hire more developers. These developers will try to install the application. There are now two plates to be kept spinning and the new developers will probably tell the boss exactly what they think. There is now even less time to formulate what the application needs of its environment. So it won't happen.

The first step towards getting error handling right is to stop the application when its environment is broken. Start agreeing on the environment spec in the first iteration, and make sure that failure to comply with the environment during startup leads to immediate and sudden failure of the application with a sensible error message. The application will now interact with whoever installs it in a nicer way, and there will be some kind of error handling structure to extend further down the line. This initial platform is crucial when the team tries to build some kind of quality around the behavior of the application later on.

The boss will probably not notice the absence of a wave of errors every time someone tries to install the application. The team will. They will be free to create more value instead of mopping up error reports.

Every team should know when to fail.

By [Geir Hedemark](http://programmer.97things.oreilly.com/wiki/index.php/Geir_Hedemark)
