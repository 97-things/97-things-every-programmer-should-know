# Put the Mouse Down and Step Away from the Keyboard

You've been focused for hours on some gnarly problem and there's no solution in sight. So you get up to stretch your legs, or to hit the vending machines, and on the way back the answer suddenly becomes obvious.

Does this scenario sound familiar? Ever wonder why it happens? The trick is that while you're coding, the logical part of your brain is active and the creative side is shut out. It can't present anything to you until the logical side takes a break.

Here's a real-life example: I was cleaning up some legacy code and ran into an 'interesting' method. It was designed to verify that a string contained a valid time using the format *hh:mm:ss xx*, where *hh* represents the hour, *mm* represents minutes, *ss* represents seconds, and *xx* is either *AM* or *PM*.

The method used the following code to convert two characters (representing the hour) into a number, and verify it was within the proper range:

```
try {
    Integer.parseInt(time.substring(0, 2));
} catch (Exception x) {
    return false;
}

if (Integer.parseInt(time.substring(0, 2)) > 12) {
    return false;
}
```

The same code appeared twice more, with appropriate changes to the character offset and upper limit, to test the minutes and seconds. The method ended with these lines to check for AM and PM:

```
if (!time.substring(9, 11).equals("AM") &
    !time.substring(9, 11).equals("PM")) {
    return false;
}
```

If none of this series of comparisons failed, returning false, the method returned true.

If the preceding code seems wordy and difficult to follow, don't worry. I thought so too — which meant I'd found something worth cleaning up. I refactored it and wrote a few unit tests, just to make sure it still worked.

When I finished, I felt pleased with the results. The new version was easy to read, half the size, and more accurate because the original code tested only the upper boundary for the hours, minutes, and seconds.

While getting ready for work the next day, an idea popped in my head: Why not validate the string using a regular expression? After a few minutes typing, I had a working implementation in just one line of code. Here it is:

```
public static boolean validateTime(String time) {
    return time.matches("(0[1-9]|1[0-2]):[0-5][0-9]:[0-5][0-9] ([AP]M)");
}
```

The point of this story is not that I eventually replaced over thirty lines of code with just one. The point is that until I got away from the computer, I thought my first attempt was the best solution to the problem.

So the next time you hit a nasty problem, do yourself a favor. Once you really understand the problem go do something involving the creative side of your brain — sketch out the problem, listen to some music, or just take a walk outside. Sometimes the best thing you can do to solve a problem is to put the mouse down and step away from the keyboard.

By [BurkHufnagel](http://programmer.97things.oreilly.com/wiki/index.php/BurkHufnagel)