# The Linker Is not a Magical Program

Depressingly often (happened to me again just before I wrote this), the view many programmers have of the process of going from source code to a statically linked executable in a compiled language is:

1. Edit source code
- Compile source code into object files
- Something magical happens
- Run executable

Step 3 is, of course, the linking step. Why would I say such an outrageous thing? I've been doing tech support for decades, and I get the following questions again and again:

1. The linker says def is defined more than once.
- The linker says abc is an unresolved symbol.
- Why is my executable so large?

Followed by "What do I do now?" usually with the phrases "seems to" and "somehow" mixed in, and an aura of utter bafflement. It's the "seems to" and "somehow" that indicate that the linking process is viewed as a magical process, presumably understandable only by wizards and warlocks. The process of compiling does not elicit these kinds of phrases, implying that programmers generally understand how compilers work, or at least what they do.

A linker is a very stupid, pedestrian, straightforward program. All it does is concatenate together the code and data sections of the object files, connect the references to symbols with their definitions, pull unresolved symbols out of the library, and write out an executable. That's it. No spells! No magic! The tedium in writing a linker is usually all about decoding and generating the usually ridiculously overcomplicated file formats, but that doesn't change the essential nature of a linker.

So let's say the linker is saying def is defined more than once. Many programming languages, such as C, C++, and D, have both declarations and definitions. Declarations normally go into header files, like:

```
extern int iii;
```

which generates an external reference to the symbol `iii`. A definition, on the other hand, actually sets aside storage for the symbol, usually appears in the implementation file, and looks like this:

```
int iii = 3;
```

How many definitions can there be for each symbol? As in the film *Highlander*, there can be only one. So, what if a definition of iii appears in more than one implementation file?

```
// File a.c
int iii = 3;
```

```
// File b.c
double iii(int x) { return 3.7; }
```

The linker will complain about `iii` being multiply defined.

Not only can there be only one, there must be one. If iii only appears as a declaration, but never a definition, the linker will complain about iii being an unresolved symbol.

To determine why an executable is the size it is, take a look at the map file that linkers optionally generate. A map file is nothing more than a list of all the symbols in the executable along with their addresses. This tells you what modules were linked in from the library, and the sizes of each module. Now you can see where the bloat is coming from. Often there will be library modules that you have no idea why were linked in. To figure it out, temporarily remove the suspicious module from the library, and relink. The undefined symbol error then generated will indicate who is referencing that module.

Although it is not always immediately obvious why you get a particular linker message, there is nothing magical about linkers. The mechanics are straightforward; it's the details you have to figure out in each case.

By [Walter Bright](http://creativecommons.org/licenses/by/3.0/us/)