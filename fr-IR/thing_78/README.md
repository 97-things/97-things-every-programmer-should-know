# Step Back and Automate, Automate, Automate

I worked with programmers who, when asked to produce a count of the lines of code in a module, pasted the files into a word processor and used its "line count" feature. And they did it again next week. And the week after. It was bad.

I worked on a project that had a cumbersome deployment process, involving code signing and moving the result to a server, requiring many mouse clicks. Someone automated it and the script ran hundreds of times during final testing, far more often than anticipated. It was good.

So, why do people do the same task over and over instead of stepping back and taking the time to automate it?

## Common misconception #1: Automation is only for testing.

Sure, test automation is great, but why stop there? Repetitive tasks abound in any project: version control, compiling, building JAR files, documentation generation, deployment, and reporting. For many of these tasks, the script is mightier than the mouse. Executing tedious tasks becomes faster and more reliable.

## Common misconception #2: I have an IDE, so I don't have to automate.

Did you ever have a "But it (checks out|builds|passes tests) on my machine?" argument with your teammates? Modern IDEs have thousands of potential settings, and it is essentially impossible to ensure that all team members have identical configurations. Build automation systems such as Ant or Autotools give you control and repeatability.

## Common misconception #3: I need to learn exotic tools in order to automate.

You can go a long way with a decent shell language (such as bash or PowerShell) and a build automation system. If you need to interact with web sites, use a tool such as iMacros or Selenium.

## Common misconception #4: I can't automate this task because I can't deal with these file formats.

If a part of your process requires Word documents, spreadsheets, or images, it may indeed be challenging to automate it. But is that really necessary? Can you use plain text? Comma-separated values? XML? A tool that generates a drawing from a text file? Often, a slight tweak in the process can yield good results with a dramatic reduction in tediousness.

## Common misconception #5: I don't have the time to figure it out.

You don't have to learn all of bash or Ant to get started. Learn as you go. When you have a task that you think can and should be automated, learn just enough about your tools to do it. And do it early in a project when time is usually easier to find. Once you have been successful, you (and your boss) will see that it makes sense to invest in automation.

By [Cay Horstmann](http://programmer.97things.oreilly.com/wiki/index.php/Cay_Horstmann)
