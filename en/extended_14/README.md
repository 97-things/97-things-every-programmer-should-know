# Declarative over Imperative

Writing code is error-prone. Period. But writing imperative code is much more error-prone than writing declarative code. Why? Because imperative code tries to tell the machine what to do step by step, and usually there are lots and lots of steps. In contrast to this, declarative code states what the intent is, and leaves the step by step details to centralized implementations or even to the platform. Just as importantly, declarative code is easier to read, for the exact same reason: Declarative code expresses intent rather than the method for achieving the intent.

Consider the following imperative C# code for parsing an array of command line arguments:

```csharp
public void ParseArguments(string[] args)
{
    if (args.Contains("--help"))
    {
        PrettyPrintHelpTextForArguments();
        return;
    }
    if (args.Length % 2 != 0)
        throw new ArgumentException("Number of arguments must be even"); 
    for (int i = 0; i < args.Length; i += 2)
    {
        switch (args[i])
        {
            case "--inputfile":
                inputfileName = args[i + 1];
                break;
            case "--outputfile":
                outputfileName = args[i + 1];
                break;
            case "--count":
                HandleIntArgument(args[i], args[i + 1], out count);
                break;
            default:
                throw new ArgumentException("Unknown argument");
        }
    }
}
private void PrettyPrintHelpTextForArguments()
{
    Console.WriteLine("Help text explaining the program.");
    Console.WriteLine("\t--inputfile: Some helpful text");
    Console.WriteLine("\t--outputfile: Some helpful text");
    Console.WriteLine("\t--count: Some helpful text");
}
```

To add another recognized argument we have to add a `case` to the `switch`, and then remember to extend the help text printed in response to the `--help` argument. This means that the additional code needed to support another argument is spread out between two methods.

The declarative alternative demonstrates a simple yet powerful lookup-based declarative coding style. The declarative version is split in two: Firstly a declarative part, that declares the recognized arguments:

```csharp
class Argument
{
    public Action<DeclarativeArgParser, string> processArgument;
    public string helpText;
}
private readonly SortedDictionary<string, Argument> arguments = 
  new SortedDictionary<string, Argument>()
  {
      {"--inputfile", 
       new Argument()
       {
           processArgument = (self, a) => self.inputfileName = a, 
           helpText = "some helpful text"
       }
      },
      {"--outputfile",
       new Argument()
       {
           processArgument = (self, a) => self.outputfileName = a, 
           helpText = "some helpful text"
       }
      },
      {"--count",
       new Argument()
       {
           processArgument = 
              (self, a) => HandleIntArgument("count", a, out self.count), 
           helpText = "some helpful text"
       }
      }
  };
```

Secondly an imperative part that parses the arguments:

```csharp
public void ParseArguments(string[] args)
{
    if (args.Contains("--help"))
    {
        PrettyPrintHelpTextFieldsForArguments();
        return;
    }
    if (args.Length % 2 != 0)
        throw new ArgumentException("Number of arguments must be even");
    for (int i = 0; i < args.Length; i += 2)
    {
        var arg = arguments[args[i]];
        if (arg == null) 
            throw new ArgumentException("Unknown argument");
        arg.processArgument(this, args[i + 1]);
    }
}
private void PrettyPrintHelpTextFieldsForArguments() 
{
    Console.WriteLine("Help text explaining the program.");
    foreach (var arg in arguments)
        Console.WriteLine("\t{0}: {1}", arg.Key, arg.Value.helpText);
}
```

This code is similar to the imperative version above, except for the code inside the loop in `ParseArguments`, and the loop in `PrettyPrintHelpTextFieldsForArguments`.

To add another recognized argument a new key and `Argument` pair is simply added to the dictionary initializer in the declarative part. The type `Argument` contains exactly the two fields needed by the second part of the code. If both fields of `Argument` are initialized correctly everything else should just work. This means that the additional code needed to support another argument is localized to one place: The declarative part. The imperative part need not be touched at all. It just works regardless of the number of supported arguments.

At times there are further advantages to declarative style code: The clearer statement of intent sometimes enables underlying platform code to optimize the method of achieving the intended goal. Often this results in better performing, more scalable, or more secure software than would have been achieved using an imperative approach.

All in all prefer declarative code over imperative code.

By [Christian Horsdal](http://programmer.97things.oreilly.com/wiki/index.php/Christian_Horsdal)
