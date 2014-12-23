# Message Passing Leads to Better Scalability in Parallel Systems

Programmers are taught from the very outset of their study of computing that concurrency — and especially parallelism, a special subset of concurrency — is hard, that only the very best can ever hope to get it right, and even they get it wrong. There is invariably great focus on threads, semaphores, monitors, and how hard it is to get concurrent access to variables to be thread-safe.

True, there are many difficult problems, and they can be very hard to solve. But what is the root of the problem? Shared memory. Almost all the problems of concurrency that people go on and on about relate to the use of shared mutable memory: race conditions, deadlock, livelock, etc. The answer seems obvious: Either forgo concurrency or eschew shared memory!

Forgoing concurrency is almost certainly not an option. Computers have more and more cores on an almost quarterly basis, so harnessing true parallelism becomes more and more important. We can no longer rely on ever increasing processor clock speeds to improve application performance. Only by exploiting parallelism will the performance of applications improve. Obviously, not improving performance is an option, but it is unlikely to be acceptable to users.

So can we eschew shared memory? Definitely.

Instead of using threads and shared memory as our programming model, we can use processes and message passing. Process here just means a protected independent state with executing code, not necessarily an operating system process. Languages such as Erlang (and occam before it) have shown that processes are a very successful mechanism for programming concurrent and parallel systems. Such systems do not have all the synchronization stresses that shared memory, multi-threaded systems have. Moreover there is a formal model — Communicating Sequential Processes (CSP) — that can be applied as part of the engineering of such systems.

We can go further and introduce dataflow systems as a way of computing. In a dataflow system there is no explicitly programmed control flow. Instead a directed graph of operators, connected by data paths, is set up and then data fed into the system. Evaluation is controlled by the readiness of data within the system. Definitely no synchronization problems.

Having said all this, languages such as C, C++, Java, Python, and Groovy are the principal languages of systems development and all of these are presented to programmers as languages for developing shared memory, multi-threaded systems. So what can be done? The answer is to use — or, if they don't exist, create — libraries and frameworks that provide process models and message passing, avoiding all use of shared mutable memory.

All in all, not programming with shared memory, but instead using message passing, is likely to be the most successful way of implementing systems that harness the parallelism that is now endemic in computer hardware. Bizarrely perhaps, although processes predate threads as a unit of concurrency, the future seems to be in using threads to implement processes.

By [Russel Winder](http://programmer.97things.oreilly.com/wiki/index.php/Russel_Winder)