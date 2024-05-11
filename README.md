## 3.4.Conversions

Sometimes a value of one type should be used as a value of another type. Creating a value of one type based on a value of another type is called conversion or casting. 

Of course, it is impossible to change the type of a variable: conversions always involve values. For example, in

```java
int a = 7;
double x = a + 1;
```

the value of the right-hand side in the second line is of type `int` and a `double` is needed to initialize the variable x; however, the compiler will silently convert `int` value to the corresponding `double` value and assign it to x. 

Such conversions, performed automatically by the compiler, are called implicit conversions. 

Generally, they will be performed if they don’t lead to a loss of information. 

Conversion in the opposite direction

```java
double x = 7.7;
int a = x; // WRONG
```

will _not_ be performed; the snippet above wouldn’t be even compiled. 

This is because an `int` occupies four bytes and has no fractional part, while `double`s have fractional part and occupy eight bytes. 

Hence, conversion from `double` to `int` would lead to inevitable loss of information. We can, however, enforce the compiler to perform such conversions (taking the responsibility for possible consequences). 

We do it by specifying, in parentheses, name of the type we want to convert to:

```java
double x = 7.7;
int a = (int)x; // now OK
```
Of course, after conversion, a will be exactly 7, as there is no way for an `int` to have a fractional part.

[Contents](https://github.com/Java-PJATK/00.Contents)

Note also that this conversion does _not_ affect the variable x as such: its type is still `double` and its value is still 7.7.

The exact rules of conversions are more complicated, but general principle is that conversions from “narrow” types to “wider” are performed implicitly (`byte`, `char`, `short`→`int`, `int`,`float`,`long`→`double`, etc.), while conversions in the opposite direction must be explicit.
