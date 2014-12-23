# Use the Right Algorithm and Data Structure

> A big bank with many branch offices complained that the new computers it had bought for the tellers were too slow. This was in the time before everyone used electronic banking and ATMs were not as widespread as they are now. People would visit the bank far more often, and the slow computers were making the people queue up. Consequently, the bank threatened to break its contract with the vendor.

> The vendor sent a performance analysis and tuning specialist to determine the cause of the delays. He soon found one specific program running on the terminal consuming almost all the CPU capacity. Using a profiling tool, he zoomed in on the program and he could see the function that was the culprit. The source code read:

> ```
for (i=0; i<strlen(s); ++i) {
  if (... s[i] ...) ...
}
```

> And string s was, on average, thousands of characters long. The code (written by the bank) was quickly changed, and the bank tellers lived happily ever after....

Shouldn't the programmer have done better than to use code that needlessly scaled quadratically?
Each call to strlen traversed every one of the many thousand characters in the string to find its terminating null character. The string, however, never changed. By determining its length in advance, the programmer could have saved thousands of calls to strlen (and millions of loop executions):

```
n=strlen(s);
for (i=0; i<n; ++i) {
  if (... s[i] ...) ...
}
```

Everyone knows the adage "first make it work, then make it work fast" to avoid the pitfalls of micro-optimization. But the example above would almost make you believe that the programmer followed the Machiavellian adagio "first make it work slowly."

This thoughtlessness is something you may come across more than once. And it is not just a "don't reinvent the wheel" thing. Sometimes novice programmers just start typing away without really thinking and suddenly they have 'invented' bubble sort. They may even be bragging about it.

The other side of choosing the right algorithm is the choice of data structure. It can make a big difference: Using a linked list for a collection of a million items you want to search through — compared to a hashed data structure or a binary tree — will have a big impact on the user's appreciation of your programming.

Programmers should not reinvent the wheel, and should use existing libraries where possible. But to be able to avoid problems like the bank's, they should also be educated about algorithms and how they scale. Is it just the eye candy in modern text editors that make them just as slow as old-school programs like WordStar in the 1980s? Many say reuse in programming is paramount. Above all, however, programmers should know when, what, and how to reuse. To be able to do that they should have knowledge of the problem domain and of algorithms and data structures.

A good programmer should also know when to use an abominable algorithm. For example, if the problem domain dictates there can never be more than five items (like the number of dice in a Yahtzee game), you know that you *always* have to sort at most five items. In that case, bubble sort might actually be the most efficient way to sort the items. Every dog has its day.

So, read some good books — and make sure you understand them. And if you really read Donald Knuth's *the Art of Computer Programming* well, you might even be lucky: Find a mistake by the author and earn one of Don Knuth's hexadecimal dollar ($2.56) checks.

By [JC van Winkel](http://programmer.97things.oreilly.com/wiki/index.php/JC_van_Winkel)