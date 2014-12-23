# Know Your IDE

In the 1980s our programming environments were typically nothing better than glorified text editors... if we were lucky. Syntax highlighting, which we take for granted nowadays, was a luxury that certainly was not available to everyone. Pretty printers to format our code nicely were usually external tools that had to be run to correct our spacing. Debuggers were also separate programs run to step through our code, but with a lot of cryptic keystrokes.

During the 1990s companies began to recognize the potential income that they could derive from equipping programmers with better and more useful tools. The Integrated Development Environment (IDE) combined the previous editing features with a compiler, debugger, pretty printer, and other tools. During that time, menus and the mouse also became popular, which meant that developers no longer needed to learn cryptic key combinations to use their editors. They could simply select their command from the menu.

In the 21st century IDEs have become so common place that they are given away for free by companies wishing to gain market share in other areas. The modern IDE is equipped with an amazing array of features. My favorite is automated refactoring, particularly *Extract Method*, where I can select and convert a chunk of code into a method. The refactoring tool will pick up all the parameters that need to be passed into the method, which makes it extremely easy to modify code. My IDE will even detect other chunks of code that could also be replaced by this method and ask me whether I would like to replace them too.

Another amazing feature of modern IDEs is the ability to enforce style rules within a company. For example, in Java, some programmers have started making all parameters final (which, in my opinion, is a waste of time). However, since they have such a style rule, all I would need to do to follow it is set it up in my IDE: I would get a warning for any non-final parameter. Style rules can also be used to find probable bugs, such as comparing autoboxed objects for reference equality, e.g., using `==` on primitive values that are autoboxed into reference objects.

Unfortunately modern IDEs do not require us to invest effort in order to learn how to use them. When I first programmed C on Unix, I had to spend quite a bit of time learning how the vi editor worked, due to its steep learning curve. This time spent up-front paid off handsomely over the years. I am even typing the draft of this article with *vi*. Modern IDEs have a very gradual learning curve, which can have the effect that we never progress beyond the most basic usage of the tool.

My first step in learning an IDE is to memorize the keyboard shortcuts. Since my fingers are on the keyboard when I'm typing my code, pressing *Ctrl+Shift+I* to inline a variable saves breaking the flow, whereas switching to navigate a menu with my mouse interrupts the flow. These interruptions lead to unnecessary context switches, making me much less productive if I try to do everything the lazy way. The same rule also applies to keyboard skills: Learn to touch type, you won't regret the time invested up-front.

Lastly, as programmers we have time proven Unix streaming tools that can help us manipulate our code. For example, if during a code review, I noticed that the programmers had named lots of classes the same, I could find these very easily using the tools *find*, *sed*, *sort*, *uniq*, and *grep*, like this:

```
find . -name "*.java" | sed 's/.*\///' | sort | uniq -c | grep -v "^ *1 " | sort -r
```

We expect a plumber coming to our house to be able to use his blow torch. Let's spend a bit of time to study how to become more effective with our IDE.

by [Heinz Kabutz](http://programmer.97things.oreilly.com/wiki/index.php/Heinz_Kabutz)