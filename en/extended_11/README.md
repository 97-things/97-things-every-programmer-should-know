# Continuous Refactoring

Code bases that are not cared for tend to rot. When a line of code is written it captures the information, knowledge, and skill you had at that moment. As you continue to learn and improve, acquiring new knowledge, many lines of code become less and less appropriate with the passage of time. Although your initial solution solved the problem, you discover better ways to do so.

It is clearly wrong to deny the code the chance to grow with knowledge and abilities.

While reading, maintaining, and writing code you begin to spot pathologies, often referred to as _code smells_. Do you notice any of the following?

* Duplication, near and far
* Inconsistent or uninformative names
* Long blocks of code
* Unintelligible boolean expressions
* Long sequences of conditionals
* Working in the intestines of other units (objects, modules)
* Objects exposing their internal state

When you have the opportunity, try deodorizing the smelly code. Don't rush. Just take small steps. In Martin Fowler's _Refactoring_ the steps of the refactorings presented are outlined in great detail, so it's easy to follow. I would suggest doing the steps at least once manually to get a feeling for the preconditions and side effects of each refactoring. Thinking about what you're doing is absolutely necessary when refactoring. A small glitch can become a big deal as it may affect a larger part of the code base than anticipated.

Ask for help if your gut feeling does not guide you in the right direction. Pair with a co-worker for the refactoring session. Two pairs of eyes and sets of experience can have a significant effect — especially if one of these is unclouded by the initial implementation approach.

We often have tools we can call on to help us with automatic refactoring. Many IDEs offer an impressive range of refactorings for a variety of languages. They work on the syntactically sound parse tree of your source code, and can often refactor partially defective or unfinished source code. So there is little excuse for not refactoring.

If you have tests, make sure you keep them running while you are refactoring so that you can easily see if you broke something. If you do not have tests, this may be an opportunity to introduce them for just this reason, and more: The tests give your code an environment to be executed in and validate that the code actually does what is intended, i.e., passes the tests.

When refactoring you often encounter an epiphany at some point. This happens when suddenly all puzzle pieces fall into the place where they belong and the sum of your code is bigger than its parts. From that point it is quite easy to take a leap in the development of your system or its architecture.

Some people say that refactoring is waste in the Lean sense as it doesn't directly contribute to the business value for the customer. Improving the design of the code, however, is not meant for the machine. It is meant for the people who are going to read, understand, maintain, and extend the system. So every minute you invest in refactoring the code to make it more intelligible and comprehensible is time saved for the soul in future that has to deal with it. And the time saved translates to saved costs. When refactoring you learn a lot. I use it quite often as a learning tool when working with unfamiliar codebases. Improving the design also helps spotting bugs and inconsistencies by just seeing them clearly now. Deleting code — a common effect of refactoring — reduces the amount of code that has to be cared for in the future.

By [Michael Hunger](http://programmer.97things.oreilly.com/wiki/index.php/Michael_Hunger)
