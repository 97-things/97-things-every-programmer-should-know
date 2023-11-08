# Who Will Test the Tests Themselves?

The Roman poet Juvenal posed the question in one of his satires: _Quis custodiet ipsos custodes?_ (Who will guard the guards themselves?) When we're writing tests, we should ask the question to our selves too: Who (or what) will test the tests we're writing? In practice, the third law of Test-Driven Development (TDD) — you can't write more production code than is sufficient to pass the currently failing unit test — isn't as easy to follow as it may seem.

Let's consider a simple case: finding the largest element in an array of integers. We can start with a simple unit test, like this:

```ruby
def test_return_single_element
    assert_equal(1, max([1]))
end
```

Then we write a method doing just that:

```ruby
def max(array)
    return array.first
end
```

The next unit test could be that in an array with two integers, say `[1, 2]`, the method should return the larger one, in this case `2`. At this point many programmers will go and implement the complete method, maybe like this:

```ruby
def max(array)
    result = array.first
    array.each do | element |
               if (element > result)
                  result = element
               end
    end
    return result
end
```

In fact, if we run a tool that measures the code coverage, it will indicate test coverage is 100%. But does this mean that we're done?

If we don't consider the cases of `null` arguments or empty arrays for a moment, our method is complete and correct. But if we run a mutation tester against our source code using these two unit tests only, we will find out something is wrong. Indeed, if we remove the condition of the `if` statement (by setting it to `true`, for instance), the two unit tests will still run fine. What happened?

Well, we broke the third law of TDD. We shouldn't have implemented the complete method yet, but first changed the body of the method to `return array.last`, then written a third unit test using `[2, 1]` as test data, and only then programmed the whole method. We were, however, too eager to start programming, and probably already had the third unit test running in our head. That's also why we were so surprised that all the unit tests were still running fine, even though the implementation obviously was incomplete.

What can we do to avoid situations like this? As is so often the case in our profession, the computer can help. There exist special tools, such as the already mentioned mutation testers, that can go through our source code, make small changes, and then check back whether all our unit tests are still running fine. If we meticulously followed the TDD laws, then for every change the mutation tester makes in our source code we should find that at least one unit test fails. If it doesn't, we've done something wrong — or, rather, too much.

Use mutation testers with caution, though. If used blindly and excessively, mutation testing can quickly become very time consuming, thereby losing its value. Use it primarily on the most important parts of your code, and remove false positives through continuous configuration. But make sure you don't remove the interesting mutations it generates, in particular those you don't understand, the ones you believe would never break any of your unit tests. They are the interesting ones: They will reveal where you've done more than one thing at a time, and teach you how to slow down and start writing better unit tests.

By [Filip van Laenen](http://programmer.97things.oreilly.com/wiki/index.php/Filip_van_Laenen)
