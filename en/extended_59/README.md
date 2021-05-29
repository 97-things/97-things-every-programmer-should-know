# There Is No Such Thing as Self-Documenting Code

Source code that does not contain comments is sometimes said to be "self-documenting." In reality, there is no such thing. All programs require comments.

In an ideal development environment, coding standards and code reviews create a culture that enforces good commenting practices (and usually high-quality code as well). For less-than-ideal environments, where the programmer sets his or her own commenting standards, the following guidelines are suggested.

### Comment to supplement the source code.

Source code is written not only to be processed by the compiler, but also to communicate to other programmers. Comments should add value by supplementing the reader's understanding of the code. Avoid cluttering the code with redundant information, as in the following example, where the comment communicates nothing beyond what the programming statement specifies:
```
// Add offset to index
index += offset;
```

Change the comment so that it explains how the instruction helps to accomplish the larger task at hand. Or, change the names of the variables to make the operation more clear, so that a comment is not needed.

### Comment to explain the unusual.

Sometimes, an unusual coding construct is needed to implement an algorithm or to optimize for time or space constraints. In these cases, comments can be quite valuable. For example, if a function processes an array from highest index to lowest, when all of the other functions process the same array in the opposite order, then provide a comment to explain why the function requires a different approach.

### Comment to document hardware/software interactions.

The closer an application is to controlling underlying hardware, the more comments generally are needed to make the program understandable. Source code for device drivers or embedded applications benefits from comments that describe hardware interactions, such as special timing or sequencing requirements. Some hardware-related source code may contain memory-mapped structures with cryptic bit-field names that are defined by the integrated circuit manufacturer; comments help to clarify these identifiers. Sometimes, a section of code is written to work around a hardware problem. A comment indicating the problem and referencing relevant hardware errata is useful, especially when the hardware problem is fixed and the maintenance programmers want to figure out which instructions can be simplified or removed.

### Comment with maintenance in mind.

Balance the added value of each comment with its maintenance cost. Remember that every comment becomes part of the source code that must be maintained. When comments do not add to the reader's understanding, they are a useless burden. When comments contradict the source code, they create confusion for future programmers. Is the code correct and the comment wrong? Or, does the comment reflect the intent of the programmer, and the code contain a bug that was not exposed during testing?

In summary, self-documenting source code is a worthy, yet unattainable goal. Strive for it by coding with clarity, but recognize that you can never fully achieve it. Add comments to enhance the understanding of your code, while not commenting what is obvious from reading the code itself. Just be mindful that what is obvious to you, when you are deep in the details of writing the program, may not be obvious to someone else. Provide comments to indicate the things that another programmer would want to know when reading your code for the first time. The programmers who inherit your code will appreciate it.

By [Carroll Robinson](http://programmer.97things.oreilly.com/wiki/index.php/Carroll_Robinson)
