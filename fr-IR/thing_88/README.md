# The Unix Tools Are Your Friends

If on my way to exile on a desert island I had to choose between an IDE and the Unix toolchest, I'd pick the Unix tools without a second thought. Here are the reasons why you should become proficient with Unix tools.

First, IDEs target specific languages, while Unix tools can work with anything that appears in textual form. In today's development environment where new languages and notations spring up every year, learning to work in the Unix way is an investment that will pay off time and again.

Furthermore, while IDEs offer just the commands their developers conceived, with Unix tools you can perform any task you can imagine. Think of them as (classic pre-Bionicle) Lego blocks: You create your own commands simply by combining the small but versatile Unix tools. For instance, the following sequence is a text-based implementation of Cunningham's signature analysis — a sequence of each file's semicolons, braces, and quotes, which can reveal a lot about the file's contents.

```
for i in *.java; do 
    echo -n "$i: "
    sed 's/[^"{};]//g' $i | tr -d '\n'
    echo
done
```

In addition, each IDE operation you learn is specific to that given task; for instance, adding a new step in a project's debug build configuration. By contrast, sharpening your Unix tool skills makes you more effective at any task. As an example, I've employed the sed tool used in the preceding command sequence to morph a project's build for cross-compiling on multiple processor architectures.

Unix tools were developed in an age when a multiuser computer had 128kB of RAM. The ingenuity that went into their design means that nowadays they can handle huge data sets extremely efficiently. Most tools work like filters, processing just a single line at the time, meaning that there is no upper limit in the amount of data they can handle. You want to search for the number of edits stored in the half-terabyte English Wikipedia dump? A simple invocation of

```
grep '<revision>' | wc –l 
```

will give you the answer without sweat. If you find a command sequence generally useful, you can easily package it into a shell script, using some uniquely powerful programming constructs, such as piping data into loops and conditionals. Even more impressively, Unix commands executing as pipelines, like the preceding one, will naturally distribute their load among the many processing units of modern multicore CPUs.

The small-is-beautiful provenance and open source implementations of the Unix tools make them ubiquitously available, even on resource-constrained platforms, like my set-top media player or DSL router. Such devices are unlikely to offer a powerful graphical user interface, but they often include the BusyBox application, which provides the most commonly-used tools. And if you are developing on Windows, the Cygwin environment offers you all imaginable Unix tools, both as executables and in source code form.

Finally, if none of the available tools match your needs, it's very easy to extend the world of the Unix tools. Just write a program (in any language you fancy) that plays by a few simple rules: Your program should perform just a single task; it should read data as text lines from its standard input; and it should display its results unadorned by headers and other noise on its standard output. Parameters affecting the tool's operation are given in the command line. Follow these rules and "yours is the Earth and everything that's in it."

By [Diomidis Spinellis](http://programmer.97things.oreilly.com/wiki/index.php/Diomidis_Spinellis)