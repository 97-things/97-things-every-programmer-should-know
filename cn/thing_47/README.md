# Know Your Next Commit

I tapped three programmers on their shoulders and asked what they were doing. "I am refactoring these methods," the first answered. "I am adding some parameters to this web action," the second answered. The third answered, "I am working on this user story."

It might seem that the first two were engrossed in the details of their work while only the third could see the bigger picture, and that the latter had the better focus. However, when I asked when and what they would commit, the picture changed dramatically. The first two where pretty clear over what files would be involved and would be finished within an hour or so. The third programmer answered, "Oh, I guess I will be ready within a few days. I will probably add a few classes and might change those services in some way."

The first two did not lack a vision of the overall goal. They had selected tasks they thought led in a productive direction, and could be finished within a couple of hours. Once they had finished those tasks, they would select a new feature or refactoring to work on. All the code written was thus done with a clear purpose and a limited, achievable goal in mind.

The third programmer had not been able to decompose the problem and was working on all aspects at once. He had no idea of what it would take, basically doing speculative programming, hoping to arrive at some point where he would be able to commit. Most probably the code written at the start of this long session was poorly matched for the solution that came out in the end.

What would the first two programmers do if their tasks took more than two hours? After realizing they had taken on too much, they would most likely throw away their changes, define smaller tasks, and start over. To keep working would have lacked focus and led to speculative code entering the repository. Instead, changes would be thrown away, but the insights kept.

The third programmer might keep on guessing and desperately try to patch together his changes into something that could be committed. After all, you cannot throw away code changes you have done — that would be wasted work, wouldn't it? Unfortunately, not throwing the code away leads to slightly odd code that lacks a clear purpose entering the repository.

At some point even the commit-focused programmers might fail to find something useful they thought could be finished in two hours. Then, they would go directly into speculative mode, playing around with the code and, of course, throwing away the changes whenever some insight led them back on track. Even these seemingly unstructured hacking sessions have purpose: to learn about the code to be able to define a task that would constitute a productive step.

Know your next commit. If you cannot finish, throw away your changes, then define a new task you believe in with the insights you have gained. Do speculative experimentation whenever needed, but do not let yourself slip into speculative mode without noticing. Do not commit guesswork into your repository.

By [Dan Bergh Johnsson](http://programmer.97things.oreilly.com/wiki/index.php/Dan_Bergh_Johnsson)