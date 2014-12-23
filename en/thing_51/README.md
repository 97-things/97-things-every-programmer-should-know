# Learn to Say "Hello, World"

Paul Lee, username leep, more commonly known as Hoppy, had a reputation as the local expert on programming issues. I needed help. I walked across to Hoppy's desk and asked, could he take a look at some code for me?

Sure, said Hoppy, pull up a chair. I took care not to topple the empty cola cans stacked in a pyramid behind him.

What code?

In a function in a file, I said.

So let's take a look at this function. Hoppy moved aside a copy of K&R and slid his keyboard in front of me.

Where's the IDE? Apparently Hoppy had no IDE running, just some editor which I couldn't operate. He grabbed back the keyboard. A few keystrokes later and we had the file open — it was quite a big file — and were looking at the function — it was quite a big function. He paged down to the conditional block I wanted to ask about.

What would this clause actually do if `x` is negative? I asked. Surely it's wrong.

I'd been trying all morning to find a way to force `x` to be negative, but the big function in the big file was part of a big project, and the cycle of recompiling *then* rerunning my experiments was wearing me down. Couldn't an expert like Hoppy just tell me the answer?

Hoppy admitted he wasn't sure. To my surprise, he didn't reach for K&R. Instead, he copied the code block into a new editor buffer, re-indented it, wrapped it up in a function. A short while later he'd coded up a main function that looped forever, prompting the user for input values, passing them to the function, printing out the result. He saved the buffer as a new file, tryit.c. All of this I could have done for myself, though perhaps not as quickly. But his next step was wonderfully simple and, at the time, quite foreign to my way of working:

```
$ cc tryit.c && ./a.out
```

Look! His actual program, conceived just a few minutes earlier, was now up and running. We tried a few values and confirmed my suspicions (so I'd been right about something!) and then he cross-checked the relevant section of K&R. I thanked Hoppy and left, again taking care not to disturb his cola can pyramid.

Back at my own desk, I closed down my IDE. I'd become so used to working on a big project within a big product I'd started to think that was what I should be doing. A general purpose computer can do little tasks too. I opened a text editor and began typing.

```
#include <stdio.h>

int main()
{
    printf("Hello, World\n");
    return 0;
}
```

By [Thomas Guest](http://programmer.97things.oreilly.com/wiki/index.php/Thomas_Guest)