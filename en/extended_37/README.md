# Learn the Platform

In these times of _write once, run anywhere_ languages, web frameworks, and virtualization, is the operating system gradually losing its importance for application developers? The answer is _no_. Applications that are easier to develop because of these abstractions may be harder to debug, fix, and optimize because of the very same abstractions.

The operating system is the platform on which you both develop and run your application. Knowing the platform makes you much more effective, whether designing, diagnosing, or optimizing your software. Your application gets developed on a platform, runs on a platform, and halts, hangs, and crashes on a platform, so learning the platform is a key skill in being a good programmer.

Learning the platform includes but does not limit you to knowing the tools present on the platform for development (IDE, build tools, etc.). It also means being familiar with other aspects of the operating system, not all of which may be directly related to development. Familiarity implies being able to answer the following questions:

* What is the underlying architecture of the operating system?
* How does the operating system manage memory?
* How are threads managed in the operating system? What is their life cycle?
* How does the file system work? What are the key file system abstractions? How are files organized?
* What utilities are available that tell you the state of the system and help you see what is happening under the hood?

If you are on Unix or one of its variants, such as Linux, one alternative approach to explore and learn more about the operating system is to install the server programs that come with the distributions and try to get these servers, daemons, and services configured and running. This may include daemons and servers providing remote shells (e.g., telnet, SSH), file transfer services (e.g., FTP), file and print services (e.g., Samba), web, mail, and so on.

Thinking that these tools and this knowledge is the preserve of system administrators, and therefore a no-no for programmers, may hurt you unexpectedly when your application is not the bottleneck or the root of the problem you are trying to solve. You need to get under the hood of the operating system and learn about common protocols like SMTP, HTTP, and FTP, client-server architecture, characteristics of daemons and services, and how to interrogate running processes and diagnose the state of the system. Most of the servers and services mentioned here enable interoperability with other systems in a standardized way, so they tell programmers how to interact with other systems and how a protocol can be used and incorporated in their own applications.

Today, applications are a complex tower of abstractions, so knowing your application is not enough. You also need to know what runs underneath it.

By [Vatsal Avasthi](http://programmer.97things.oreilly.com/wiki/index.php/Vatsal_Avasthi)
