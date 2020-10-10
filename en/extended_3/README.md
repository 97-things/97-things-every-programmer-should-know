# Anomalies Should not Be Ignored

Software that runs successfully for extended periods of time needs to be robust. Appropriate testing of long-running software requires that the programmer pay attention to anomalies of every kind and to employ a technique that I call _anomaly testing_. Here, anomalies are defined as unexpected program results or rare errors. This method is based on the belief that anomalies are due to causality rather than to gremlins. Thus, anomalies are indicators that should be sought out rather than ignored, as is typically the case.

Anomaly testing is the process of exposing the anomalies in the system though the following steps:

1. Augmenting your code with logging. Including counts, times, events, and errors.
2. Exercising/loading the software at sustainable levels for extended periods to recognize cadences and expose the anomalies.
3. Evaluating behaviors and anomalies and correcting the system to handle these situations.
4. Then repeat.

The bedrock for success is logging. Logging provides a window into the cadence, or typical run behavior, of your program. Every program has a cadence, whether you pay attention to it or not. Once you learn this cadence you can understand what is normal and what is not. This can be done through logging of important data and events.

Tallies are logged for work that is encountered and successfully processed, as well as for failed work, and other interesting dispositions. Tallies can be calculated by grepping through all of the log files or, more efficiently, they can be tracked and logged directly. Counts need to be tallied and balanced. Counts that don't add up are anomalies to be further investigated. Logged errors need to be investigated, not ignored. Paying attention to these anomalies and not dismissing them is the key to robustness. Anomalies are indicators of errors, misunderstandings, and weaknesses. Rare and intermittent anomalies also need to be isolated and pursued. Once an anomaly is understood the system needs to be corrected. As you learn your programs behavior you need to handle the errors in a graceful manner so they become handled conditions rather than errors.

In order to understand the cadence and expose the anomalies your program needs to be exercised. The goal is to run continuously over long periods of time, exercising the logic of the program. I typically find a lot of idle system time overnight or over the weekend, especially on my own development systems. Thus, to exercise your program you can run it overnight, look at the results, and then make changes for the following night. Exercising as a whole, as in production, provides feedback as to how your program responds. The input stream should be close — if not identical — to the data and events you will encounter in production. There are several techniques to do this, including recording and then playing back data, manufacturing data, or feeding data into another component that then feeds into yours.

This load should also be able to be paced — that is, you need to start out slow and then be able to increase the load to push your system harder. By starting out slow you also get a feel for the cadence. The more robust your program is, the harder it can be pushed. Getting ahead of those rare anomalies builds an understanding of what is required to produce robust software.

By [Keith Gardner](http://programmer.97things.oreilly.com/wiki/index.php/Keith_Gardner)
