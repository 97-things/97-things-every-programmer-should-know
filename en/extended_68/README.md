# Write Code for Humans not Machines

Programmers spend more their time reading someone else's code than reading or writing their own. This is why it is important that whoever writes the code pays particular attention not only to what it does but also to how it does it. For a compiler, it makes no difference if a variable is called `p` or `pageCounter`, but of course it makes a big difference for the programmer who has to figure out what kind of information that variable contains. That is why it is easier to write code for compilers than for people.

Variable and method names should be chosen carefully so as to leave no doubt about their meaning in the reader's mind. The names should most likely be taken from the objects and actions typical in your domain. If you feel the need to add a comment to clarify their purpose or behavior, it could be the first symptom that you should spend a minute more to find a more self-describing name. A comment on a method is not necessarily bad, but a meaningful name is still the best place to start: The comment will be available only on the method declaration while its name is the only thing you can read wherever that method is used.

Of course, well-chosen names are not the only things you need to make your code readable. Other rules can be applied to improve the code readability:

* _Keep each method as short as possible_: 15 lines of code is a reasonable upper limit that you should be wary of exceeding.

* _Give each method a single responsibility_: If you are trying to give a meaningful name to the method and you find the name contains an <code/>and</code>, there is a good chance that you are breaking this rule.

* _Declare methods with the lowest number of parameters possible_: If you need more than 3 parameters it could be a good idea to do a small refactor by grouping them as properties of a single object.

* _Avoid nested loops or conditions where possible_: You can improve both readability and reusability by putting them in little separated methods.

* _Write comments only when strictly necessary and keep them in sync with the code_: There is nothing more useless than a comment that explains what you can easily read from the code or more confounding than a comment that says something different from what the code actually does.

* _Establish a set of shared coding standards_: Programmers can understand a piece of code faster if they don't encounter unexpected surprises while reading it.

By making your code easily readable by other programmers you are making their job simpler. And this is no bad thing when you consider that the next programmer to read the code could be you.

By [Mario Fusco](http://programmer.97things.oreilly.com/wiki/index.php/Mario_Fusco)
