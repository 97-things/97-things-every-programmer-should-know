# Make the Invisible More Visible

Many aspects of invisibility are rightly lauded as software principles to uphold. Our terminology is rich in invisibility metaphors — mechanism transparency and information hiding, to name but two. Software and the process of developing it can be, to paraphrase Douglas Adams, *mostly invisible*:

- Source code has no innate presence, no innate behavior, and doesn't obey the laws of physics. It's visible when you load it into an editor, but close the editor and it's gone. Think about it too long and, like the tree falling down with no one to hear it, you start to wonder if it exists at all.
- A running application has presence and behavior, but reveals nothing of the source code it was built from. Google's home page is pleasingly minimal; the goings on behind it are surely substantial.
- If you're 90% done and endlessly stuck trying to debug your way through the last 10% then you're not 90% done, are you? Fixing bugs is not making progress. You aren't paid to debug. Debugging is waste. It's good to make waste more visible so you can see it for what it is and start thinking about trying not to create it in the first place.
- If your project is apparently on track and one week later it's six months late you have problems, the biggest of which is probably not that it's six months late, but the invisibility force fields powerful enough to hide six months of lateness! Lack of visible progress is synonymous with lack of progress.

Invisibility can be dangerous. You think more clearly when you have something concrete to tie your thinking to. You manage things better when you can see them and see them constantly changing:

- Writing unit tests provides evidence about how easy the code unit is to unit test. It helps reveal the presence (or absence) of developmental qualities you'd like the code to exhibit; qualities such as low coupling and high cohesion.
- Running unit tests provides evidence about the code's behavior. It helps reveal the presence (or absence) of runtime of qualities you'd like the application to exhibit; qualities such as robustness and correctness.
- Using bulletin boards and cards makes progress visible and concrete. Tasks can be seen as *Not Started*, *In Progress*, or *Done* without reference to a hidden project management tool and without having to chase programmers for fictional status reports.
- Doing incremental development increases the visibility of development progress (or lack of it) by increasing the frequency of development evidence. Completion of releasable software reveals reality; estimates do not.

It's best to develop software with plenty of regular visible evidence. Visibility gives confidence that progress is genuine and not an illusion, deliberate and not unintentional, repeatable and not accidental.

By [Jon Jagger](http://programmer.97things.oreilly.com/wiki/index.php/Jon_Jagger)