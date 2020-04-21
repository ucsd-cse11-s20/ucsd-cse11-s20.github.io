---
layout: page
title: "UCSD CSE11 S20 – PA3"
doodle: "/doodle.png"
---

# Programming Assignment 4 – Interfaces

<p style="border: 2px dotted red; padding: 1em;">
This is a draft, this notice will be removed when the PA is finalized.
</p>

This programming assignment will help you practice writing interfaces and
classes.

You will upload _several_ Java files for this assignment, detailed below.

## Tweets

<div class='sidenote'>A Twitter-specific pattern is writing a <a
href="https://help.twitter.com/en/using-twitter/create-a-thread">“thread”</a>
by replying to one's own Tweets repeatedly.</div>

In a file `Tweets.java`, write an `interface` called `Tweet` with three
methods:

- `public boolean isStartOfThreadBy(String author);`
- `public int totalLikes();`
- `public String unrollThread();`

Then, write two classes:

- `TextTweet`, implements `Tweet` and has three fields:
  - `contents`, a `String`
  - `likes`, an int
  - `author`, a `String`

  This class should implement the methods as follows:
  - `isStartOfThreadBy` should return `true` when the given author is the
  same as the `author` of this `TextTweet`, `false` otherwise.
  - `totalLikes` should return the number of likes on this `TextTweet` object
  - `unrollThread` should return a string in the following format:

    ```
    <author>
    <n> likes
    <content>
    ```

    where `<author>` is replaced by the author's name, `<n>` is replaced by
    the number of likes on the `TextTweet`, and `<content>` is replaced by
    the contents of the Tweet. The string should end in a new line (`"\n"` character).
- `ReplyTweet`, which has four fields:
  - `contents`, a `String`
  - `likes`, an int
  - `author`, a `String`
  - `replyTo`, a `Tweet`

  This class should implement the methods as follows:
  - `isStartOfThreadBy` should return `true` when the given author is the
  same as the `author` of this `ReplyTweet` **and** the `replyTo` tweet is
  also the start of a thread by the same author.
  - `totalLikes` should return the total number of likes on this `ReplyTweet` object
  **plus** the total likes of its `replyTo` Tweet. For example, a thread of tweets that is 4 replies long should sum the likes on all 4 of those tweets.
  - `unrollThread` should return a string in the following format:

    ```
    <replyTo content>
    <author>
    <n> likes
    <content>
    ```

    where the bottom three parts are the same format as in `TextTweet`, and
    the first part is the unrolled version of the `replyTo` `Tweet`.
    Like for `TextTweet`, this should end in a new line character.

You can, but don't have to, use an abstract class to avoid duplicated work as
you see fit. Add constructors as appropriate to initialize the fields on
objects of these classes (whether or not you use an abstract class).

For each method, write at least two tests for it in a class called `Tweets`
using the `Tester` library. A “test” is a use of `checkExpect` that 
checks the results of the method call against an expected value.

Since there are 6 total method implementations, you should have at least 12
tests. Tests are graded manually, your implementation is graded
automatically.

## Numbers

This code will go in the file `ExamplesNumber.java`, any tests in a class called
`ExamplesNumber` that you add to that file.

We saw in our reading that representing fractional numbers like 0.6 with
doubles can be fraught. Some languages and libraries do support exact
fractions, and we can implement classes that act like them in Java. We won't
be able to use the built-in `+` and `*` operators, because these are only
defined for numbers and strings, but we can define methods for the operations
we care about. We can represent numbers with an interface:

```
interface Number {
  int numerator();
  int denominator();
  Number add(Number other);
  Number multiply(Number other);
  String toString();
  double toDouble();
}
```

(We could specify more methods, but for the purposes of this assignment,
these four will be sufficient.)

Your task is to create two classes that implement the interface above. One
should be called `WholeNumber` and represent whole integers (including
negative numbers). The other should be called `Fraction` and represent mixed
numbers.

`WholeNumber` should have:
- A field `int n` and a constructor that takes a single `int`
- An implementation of all the methods above.
  - `numerator` should return the value of `n`
  - `denominator` should return `1`
  - `add` should return a new `Number` that represents adding this whole number to the one provided as an argument. Note that the argument could be either a `Fraction` or a `WholeNumber`
  - `multiply` should return a new `Number` that represents multiplying this whole number to the one provided as an argument. Note that the argument could be either a `Fraction` or a `WholeNumber`
  - `toString` should return the value of `n` as a `String`, so if `n` is `500`, it should return `"500"`
  - `toDouble` should return the value of `n` as a `double`

`Fraction` should have:
- A field `int n` representing the numerator
- A field `int d` representing the denominator
- An implementation of all the methods above:
  - `numerator` should return the value of `n`
  - `denominator` should return the value of `d`
  - `add` should return a new `Number` that represents adding this fraction to the one provided as an argument. Note that the argument could be either a `Fraction` or a `WholeNumber`
  - `multiply` should return a new `Number` that represents multiplying this fraction by the one provided as an argument. Note that the argument could be either a `Fraction` or a `WholeNumber`
  - `toString` should return a `String` in the format `"n/d"` where `n` and `d` are the corresponding fields. So if `n` and `d` were `1` and `2`, this should be `"1/2"`
  - `toDouble` should return the value of `n/d` as a `double`. So if `n` is 1 and `d` is 2, this should return `0.5`

A reminder about arithmetic and fractions:

$$
n = \frac{n}{1}
$$

$$
\frac{n}{d_1} + \frac{m}{d_2} = \frac{d_1m + d_2n}{d_1d_2}
$$

$$
\frac{n}{d_1} \cdot \frac{m}{d_2} = \frac{nm}{d_1d_2}
$$



### Exploration

At the end of the `ExamplesNumber` class in a place marked clearly with a
comment that says `// Exploration`, write code to perform four calculations:

1. The result of `0.1 + 0.2 + 0.3` using built-in `double` arithmetic in Java
2. The result of `0.1 + (0.2 + 0.3)` using built-in `double` arithmetic in Java
3. The result of (1) using your exact fractions, showing the result via `toString()`
4. The result of (1) using your exact fractions, showing the result via `toString()`



## Submission

You will submit _all_ of your files to the `pa4` assignment on Gradescope:

- On the Gradescope upload screen, you can keep clicking “Browse Files” to
  select more than one file for your upload; you can select them one at a time
  or use your operating system's multi-select (Shift-Click usually works) to
  select them all and drag them onto the upload area, or other options that you
  find that work.
- You can also make a zip archive of all of your files and upload them all at
  once if you prefer.

The parts marked `(auto)` will be graded automatically in Gradescope based on
tests we wrote. The parts marked `(manual)` will be graded by the course staff
after the due date. In addition, we may give you feedback on any part of the
code, including automatically graded parts, that we want you to respond to
after grading.

## Extra Challenges (not for credit)

**Challenge** (not required for credit): Many fractions, like $$2/4$$ or
$$27/6$$, are not in their simplest form. Make it so that the constructor for
`Fraction` always creates a fraction object with numerator and denominator in
their most reduced form.

**Challenge** (not required for credit): Implement the `area` method as described above.

**Challenge** (not required for credit): Create a `ReplyTweet` that is a reply
to itself. Do you think this is possible on Twitter?