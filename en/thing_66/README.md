# Prevent Errors

Error messages are the most critical interactions between the user and the rest of the system. They happen when communication between the user and the system is near breaking point.

It is easy to think of an error as being caused by a wrong input from the user. But people make mistakes in predictable, systematic ways. So it is possible to 'debug' the communication between the user and the rest of the system just as you would between other system components.

For instance, say you want the user to enter a date within an allowed range. Rather than letting the user enter any date, it is better to offer a device such as a list or calendar showing only the allowed dates. This eliminates any chance of the user entering a date outside of the range.

Formatting errors are another common problem. For instance, if a user is presented with a Date text field and enters an unambiguous date such as "July 29, 2012" it is unreasonable to reject it simply because it is not in a preferred format (such as "DD/MM/YYYY"). It is worse still to reject "29 / 07 / 2012" because it contains extra spaces — this kind of problem is particularly hard for users to understand as the date appears to be in the desired format.

This error occurs because it is easier to reject the date than parse the three or four most common date formats. These kind of petty errors lead to user frustration, which in turn lead to additional errors as the user loses concentration. Instead, respect users' preference to enter information, not data.

Another way of avoiding formatting errors is to offer cues — for instance, with a label within the field showing the desired format ("DD/MM/YYYY"). Another cue might be to divide the field into three text boxes of two, two, and four characters.

Cues are different from instructions: Cues tend to be hints; instructions are verbose. Cues occur at the point of interaction; instructions appear before the point of interaction. Cues provide context; instructions dictate use.

In general, instructions are ineffective at preventing error. Users tend to assume that interfaces will work in line with their past experience ("Surely everyone knows what 'July 29, 2012' means?"). So instructions go unread. Cues nudge users away from errors.

Another way of avoiding errors is to offer defaults. For instance, users typically enter values that correspond to *today*, *tomorrow*, *my birthday*, *my deadline*, or *the date I entered last time I used this form*. Depending on context, one of these is likely to be a good choice as a smart default.

Whatever the cause, systems should be tolerant of errors. You can do this by providing multiple levels of *undo* to all actions — and in particular actions which have the potential to destroy or amend users' data.

Logging and analyzing *undo* actions can also highlight where the interface is drawing users into unconscious errors, such as persistently clicking on the 'wrong' button. These errors are often caused by misleading cues or interaction sequences that you can redesign to prevent further error.

Whichever approach you take, most errors are systematic — the result of misunderstandings between the user and the software. Understanding how users think, interpret information, make decisions, and input data will help you debug the interactions between your software and your users.

by [Giles Colborne](http://programmer.97things.oreilly.com/wiki/index.php/Giles_Colborne)