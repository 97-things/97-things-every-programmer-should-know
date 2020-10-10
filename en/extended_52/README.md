# Small!

Look at this code:

```java
private void executeTestPages() throws Exception {
  Map<String, LinkedList<WikiPage>> suiteMap = makeSuiteMap(page, root, getSuiteFilter());
  for (String testSystemName : suiteMap.keySet()) {
    if (response.isHtmlFormat()) {
      suiteFormatter.announceTestSystem(testSystemName);
      addToResponse(suiteFormatter.getTestSystemHeader(testSystemName));
    }
    List<WikiPage> pagesInTestSystem = suiteMap.get(testSystemName);
    startTestSystemAndExecutePages(testSystemName, pagesInTestSystem);
  }
}
```

Your first reaction is probably not positive. Not because the code is that complicated or daunting, but just because you don't necessarily feel like untangling the intent hidden in 11 lines of code with 3 levels of indent. You know you can do it, but it feels like work.

Now look at this function:

```java
private void executeTestPages() throws Exception {
  Map<String, LinkedList<WikiPage>> pagesByTestSystem;
  pagesByTestSystem = makeMapOfPagesByTestSystem(page, root, getSuiteFilter());
  for (String testSystemName : pagesByTestSystem.keySet())
    executePagesInTestSystem(testSystemName, pagesByTestSystem);
}
```

Notice that it doesn't feel so much like work. You can look at it, and grasp the intent without much effort. Not much has changed, I've just cleaned up the code a little. And yet that small change, so easy to do with modern refactoring browsers and a suite of tests, makes the function much easier to read.

The extracted functions are pretty easy to read too:

```java
private void executePagesInTestSystem(String testSystemName,
                                      Map<String, LinkedList<WikiPage>> pagesByTestSystem) throws Exception {
  List<WikiPage> pagesInTestSystem = pagesByTestSystem.get(testSystemName);
  announceTestSystem(testSystemName);
  startTestSystemAndExecutePages(testSystemName, pagesInTestSystem);
}

private void announceTestSystem(String testSystemName) throws Exception {
  if (response.isHtmlFormat()) {
    suiteFormatter.announceTestSystem(testSystemName);
    addToResponse(suiteFormatter.getTestSystemHeader(testSystemName));
  }
}
```

The point is that functions should be _small_. How small? Just a few lines of code with one or two levels of indent.

"You can't be serious!" I hear you say. But serious I am. It is far better to have many small functions than a few large ones.

"But doesn't the proliferation of functions make the code more confusing?"

It certainly does if the proliferated functions are scattered hither and yon with no sense of organization. However, when those small functions gathered together into a well ordered and organized module, then they aren't confusing at all. Large and deeply indented functions are much more confusing that a well organized set of simple little functions.

Think of it this way. When you were young you had a "system" for knowing where all your things were. They were on the floor of your room, or under the bed, or in a pile in your closet. Your mother would yell at you from time to time to clean up your room, but you did your best to thwart her intent because your system worked just fine for you. You knew that tomorrow's socks were right on the floor where you left them last night. The same for your underwear. You knew that your favorite toy was under your bed somewhere. You had a system.

But finally your mother got so frustrated that she forced you to help her (meaning watch her) clean up your room. You watched as she hung clothes up in the closet, and put toys on shelves or in drawers. You watched as she organized your things and put them away. And (sometime in your 30s) you realized that she had a point.

Yes, it's generally better to have a place for everything and put everything in it's place. And that's just what dividing your code into many small functions is. Large functions are just like all the clothes under your bed. Splitting them up into many little functions is like putting all your clothes on hangers and sorting them nicely in your closet. Large functions are a child's way to organize. Small functions are an adult's (or should I say a professional's) way to organize.

By [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)
