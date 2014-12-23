# A Comment on Comments

In my first programming class in college, my teacher handed out two BASIC coding sheets. On the board, the assignment read "Write a program to input and average 10 bowling scores." Then the teacher left the room. How hard could this be? I don't remember my final solution but I'm sure it had a `FOR/NEXT` loop in it and couldn't have been more than 15 lines long in total. Coding sheets — for you kids reading this, yes, we used to write code out longhand before actually entering it into a computer — allowed for around 70 lines of code each. I was very confused as to why the teacher would have given us two sheets. Since my handwriting has always been atrocious, I used the second one to recopy my code very neatly, hoping to get a couple extra points for style.

Much to my surprise, when I received the assignment back at the start of the next class, I received a barely passing grade. (It was to be an omen to me for the rest of my time in college.) Scrawled across the top of my neatly copied code, "No comments?"

It was not enough that the teacher and I both knew what the program was supposed to do. Part of the point of the assignment was to teach me that my code should explain itself to the next programmer coming behind me. It's a lesson I've not forgotten.

Comments are not evil. They are as necessary to programming as basic branching or looping constructs. Most modern languages have a tool akin to javadoc that will parse properly formatted comments to automatically build an API document. This is a very good start, but not nearly enough. Inside your code should be explanations about what the code is supposed to be doing. Coding by the old adage, "If it was hard to write, it should be hard to read," does a disservice to your client, your employer, your colleagues, and your future self.

On the other hand, you can go too far in your commenting. Make sure that your comments clarify your code but do not obscure it. Sprinkle your code with relevant comments explaining what the code is supposed to accomplish. Your header comments should give any programmer enough information to use your code without having to read it, while your in-line comments should assist the next developer in fixing or extending it.

At one job, I disagreed with a design decision made by those above me. Feeling rather snarky, as young programmers often do, I pasted the text of the email instructing me to use their design into the header comment block of the file. It turns out that managers at this particular shop actually reviewed the code when it was committed. It was my first introduction to the term *career-limiting move*.

by [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)