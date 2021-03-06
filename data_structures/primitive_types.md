# Primitive Types
## Overview
The table below shows Java's eight primitive types. You will rarely use any but the four in bold.

Integers | Floating Point Numbers | Characters | Booleans
-|-|-|-
byte<br>short<br>**int**<br>long | float<br>**double** | **char** | **boolean**

The numeric types vary in how many bits they allocate for storage; larger types can hold larger numbers but use more memory.

These types are called *primitive* because they aren't made of smaller things. The built-in type String, in contrast, is not primitive because a String is made of characters.
### Literals
A *literal* is a value that is used exactly as it appears in the program.

Type | Examples of Literals
-|-
int | `23` `-100`
double | `3.14159` `1.3e-10`
char | `'a'` `'\n'`
boolean | `true` `false`

There are two cases where literals are of non-primitive types:
- String literals are in quotations marks: `"Hello"`.
- The literal `null` represents a null reference.
### Type Conversion
When a certain type is expected, that type must be used. There are two exceptions:
- When Java can do the conversion without losing information, it will do so. For example, an int can be converted to a double. Thus, when adding `1 + 1.5`, the `+` operator needs its two operands to be of the same type, so Java automatically converts the int `1` into the double `1.0`.
- You can explicitly *cast* one type to another. The expression `(int) 3.9` converts the double `3.9` into the int `3`, truncating the non-integer part.
## Additional Resources
### Online
- Sedgewick and Wayne, *Introduction to Programming in Java* booksite, [Section 1.2](https://introcs.cs.princeton.edu/java/12types/)
- ProTech, [Java Fundamentals Tutorial: Data Types](https://www.protechtraining.com/content/java_fundamentals_tutorial-data_types)
- Wired, [No, 'Gangnam Style' Didn't Break YouTube. We Did the Math](https://www.wired.com/2014/12/gangnam-style-youtube-math/)
- Kotaku, [Why Gandhi Is Such an Asshole in *Civilization*](https://kotaku.com/why-gandhi-is-such-an-asshole-in-civilization-1653818245)
### Print
- Sedgewick and Wayne, *Introduction to Programming in Java*, Section 1.2
- Horstmann, *Core Java, Volume I: Fundamentals, 11th Edition*, Sections 3.3, 3.5.3, and 3.5.4
## Questions
1. :star: How many different boolean values are there?
1. :star: What's the difference between `'x'` and `"x"`?
1. :star::star: What is the maximum value of an int?
1. :star::star: What is the value of `'a' + 1`?
1. :star::star: What does the literal `NaN` mean?
1. :star::star::star: What does the literal `0.3f` mean?
1. :star::star::star: Use Java to print the literal `0615`. How can this surprising result be explained?
## Answers
1. Two: `true` and `false`.
1. `'x'` is a char; `"x"` is a String.
1. ![2 to the 31st power minus 1 = 2147483647](https://latex.codecogs.com/svg.latex?2^{31}-1=2147483647). You should know that it's about two billion; you can look up the exact value if you ever need it.
1. 98, because the char literal `'a'` is converted to the number 97 (its Unicode value). `(char)('a' + 1)` is `b`.
1. `NaN` is the double value *not a number*. It is the result of calculations such as `0.0 / 0.0`.
1. `0.3f` is the number 0.3 represented as a float rather than a double.
1. `0615` is evaluated as 397. An integer literal starting with `0` is read as an octal (base 8) number rather than a decimal number. Similarly, a literal starting with `0x` is read as a hexadecimal (base 16) number.
