# Learn to Use a Real Editor

I'm sorry to break the news to you, but Windows _Notepad_ and, probably, the editor that comes with your IDE are toys. As a professional programmer invest the effort needed to use a real editor effectively. At the risk of starting a religious war let me point you toward _vim_, the modern supercharged incarnation of the Unix _vi_ editor, and _Emacs_, the editor that some compare to an operating system.

Whatever your choice these are examples of tasks you should learn doing in your editing environment.

* Change something on lines matching (or not matching) a specific pattern. Or delete those lines. For instance, delete all empty lines.
* Convert a series of method calls into initialization data.
* Convert data from an HTML table into a series of SQL insert commands.
* Visit one file, copy various useful things into a few separate buffers, and then visit another to place them where needed. This is useful for copying separate interrelated parts of an APIs invocation sequence.
* Accumulate material from various places into a buffer for pasting in another place.
* Edit and re-execute a complex command you entered a few hours ago. Or repeat a complex sequence of commands in various parts of the file you're editing.
* Gather a sequence of named HTML section headings and convert them into a table of contents.
* Change assignments into method invocations.

For many of the above tasks, you need to master the powerful but slightly cryptic language of regular expressions. These are simply a way to express a recipe for a string your editor must match. Here is a cheat sheet with the most common special characters.

.
Match any character

\*
Match the preceding expression any number of times

\^
Match the beginning of the line

$
Match the end of a line

[a-z_]
Match the characters between the brackets (a lowercase letter and the underscore in this case)

[^0-9]
Match any but the characters between the brackets (any non-digit character in this example)

\\<
Match the beginning of a word

\\>
Match the end of a word

\\
Match the following special character literally

The search-and-replace command of any editor worth its salt will allow you to bracket parts of a regular expression and reuse those parts in the replacement string. This by far the most powerful way to construct sophisticated editing commands.

You also want your editor to be running on all the systems you're using, to allow you to touch-type commands on the most common keyboard layouts you use (_vim_ does a pretty good job on this front), to be scriptable using a rich language (_Emacs_ is famous for this), to compile your project and guide you through its errors, to provide syntax highlighting, and, of course, to prepare a decent latte.

By [Diomidis Spinellis](http://programmer.97things.oreilly.com/wiki/index.php/Diomidis_Spinellis)
