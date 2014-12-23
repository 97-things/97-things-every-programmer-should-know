# Prefer Domain-Specific Types to Primitive Types

On 23rd September 1999 the $327.6 million Mars Climate Orbiter was lost while entering orbit around Mars due to a software error back on Earth. The error was later called the *metric mix-up*. The ground station software was working in pounds while the spacecraft expected newtons, leading the ground station to underestimate the power of the spacecraft's thrusters by a factor of 4.45.

This is one of many examples of software failures that could have been prevented if stronger and more domain-specific typing had been applied. It is also an example of the rationale behind many features in the Ada language, one of whose primary design goals was to implement embedded safety-critical software. Ada has strong typing with static checking for both primitive types and user-defined types:

```
type Velocity_In_Knots is new Float range 0.0 .. 500.00;

type Distance_In_Nautical_Miles is new Float range 0.0 .. 3000.00;

Velocity: Velocity_In_Knots;

Distance: Distance_In_Nautical_Miles;

Some_Number: Float;

Some_Number:= Distance + Velocity; -- Will be caught by the compiler as a type error.
```

Developers in less demanding domains might also benefit from applying more domain-specific typing, where they might otherwise continue to use the primitive data types offered by the language and its libraries, such as strings and floats. In Java, C++, Python, and other modern languages the abstract data type is known as class. Using classes such as `Velocity_In_Knots` and `Distance_In_Nautical_Miles` adds a lot of value with respect to code quality:

1. The code becomes more readable as it expresses concepts of a domain, not just Float or String.
- The code becomes more testable as the code encapsulates behavior that is easily testable.
- The code facilitates reuse across applications and systems.

The approach is equally valid for users of both statically and dynamically typed languages. The only difference is that developers using statically typed languages get some help from the compiler while those embracing dynamically typed languages are more likely to rely on their unit tests. The style of checking may be different, but the motivation and style of expression is not.

The moral is to start exploring domain-specific types for the purpose of developing quality software.

By [Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)