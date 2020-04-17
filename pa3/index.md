---
layout: page
title: "UCSD CSE11 S20 – PA3"
doodle: "/doodle.png"
---

# Programming Assignment 3 – Classes and Conditionals Practice

This programming assignment will help you practice writing classes and
conditionals. You'll also get a chance to do some open-ended exploration of
Java features.

You will upload _several_ Java files for this assignment, detailed below. The
starter code is available here:

[https://github.com/ucsd-cse11-s20/pa3](https://github.com/ucsd-cse11-s20/pa3)

Different assignments in this course have different collaboration policies. On
this assignment, you can collaborate with anyone in the course, including
sharing code. In your submission, give credit to all students and course staff
who helped you with this assignment by noting their name and how you used their
ideas or work. Note that using someone's work without giving credit to them is
a violation of academic integrity.

We've added a file called `CREDITS.txt` for you to write these credits into.

## Drill 1 (auto)

Write three classes as described below. They do not need to have any methods or
constructors. Save them in a file called `Drill1.java`.

- A class named `A` with two fields, `int f1` and `String f2`
- A class named `B` with two fields, `A field1` and `String field2`
- A class named `C` with three fields, `B fieldB`, `A fieldA`, `int field3`

## Drill 2 (auto)

Create a file called `Drill2.java` containing the following class definitions
(you can copy/paste them from here):

```java
class C1 {
  C2 other;
  C1(C2 other) {
    this.other = other;
  }
}

class C2 {
  int x;
  C2(int x) {
    this.x = x;
  }
}
```

Then add a class definition called `Drill2` with the following fields:

- A field named `first` of type `C2` with its `x` field equal to 10
- A field named `second` of type `C1`. It's value should be a reference to a
  `C1` object with its `other` field set to any `C2` object _other than the
  one stored in_ `first` (you can create another `C2` object for this).
- A field named `third` of type `C1`. It's value should be a reference to a
  `C1` object with its `other` field _the same C2 object_ as the one stored in
  the `first` field.

## Drill 3 (auto)

In a file called `Drill3.java`, write a class called `TextTweet` that has two
fields: one field called `contents` of type `String`, and one field called
`likes` of type `int`. Give it a default constructor of two arguments that
initializes those fields. In it, write the following methods:

<div class='sidenote'>Remember that the <a href="https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html#method.summary">Java documentation</a> lists lots of helpful <code>String</code> methods!</div>
- `hasMention` which takes a `String` called `username` and checks if the
  string `@` followed by that username apppears in the Tweet contents,
  returning `true` if it doesn and `false` otherwise.
- `hasLike` which takes no arguments and returns `true` if the tweet has zero
  likes, false otherwise.
- `firstMention` which takes no arguments and returns a `String` containing the
  substring between the _first_ appearance of the `@` character in the
  `contents` and the first space character after that. If there is no space
  after the `@`, or if there's no `@`, the empty string `""` should be
  returned.

<div class='sidenote'>
Twitter has <a
href="https://help.twitter.com/en/using-twitter/mentions-and-replies">some
documentation</a> on replying to Tweets that can help explain the context here.
There are many systems, like email, Piazza, Facebook, and so on that also have
replies as a key feature we might want to model.
</div>
Also in `Drill3.java`, write a class called `ReplyTweet` that has three fields:
one called `replyTo` of type `TextTweet`, one called `contents` of type
`String`, and one called `likes` of type `int`. Give it a default constructor
that initializes these fields. In it, write the following
methods:

- `morePopularReply` which takes no arguments and returns true if this
  ReplyTweet has more likes than the `TextTweet` it is replying to
- `allLikes` which takes no arguments and returns the sum of the likes on this
  ReplyTweet and on the TextTweet it is replying to
- `hasMention` which takes a `String` called `username` and checks if the
  string `@` followed by that username apppears in this `ReplyTweet`'s contents
  **or** in the `TextTweet` that is being replied to.

We highly recommend adding a class to this file called `Drill3` that has any
tests or examples you used to help verify that your methods worked as you
expected.

## Drill 4 (auto)

In a file called `Drill4.java`, write a class `Drill4` with the following
methods. For each, write at least three interesting tests, and include the
expected values.

- `phaseOfWater` which takes an `int` and returns `"vapor"` if the number is
  greater than or equal to 100, `"liquid"` if the number is less than 100 and
  greater than 0, and `"solid"` if the number is less than or equal to 0.
- `maxDifference` which takes three `int`s and returns the largest absolute
  difference between any two of them. For example, `maxDifference` applied to
  `1`, `-1`, and `5` should return `6` because the difference between -1 and
  5 is 6 which is greater than 2 or 4 (the differences between -1 and 1, and
  between 1 and 5).
  <div class='sidenote'>Remember that the <a
  href="https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Math.html#method.summary">Java
  documentation</a> lists lots of helpful methods in the <code>Math</code> class!</div>
- `ringArea`, which takes two `double`s representing the radius of an inner
  circle and an outer circle, and returns the area of the ring between them as
  a `double`.
  Assume both inputs are positive and that the first number is smaller than the
  second. Recall that the area of a circle is πr<sup>2</sup>. You can use
  `Math.PI`, a field conveniently defined for us by Java, as a constant for the
  value of π.

## Open-Ended 1 (manual)

Consider the following statements about Java programs:

- **Statement A**: In Java, two different classes can define a field with the same name and
type.
- **Statement B**: In Java, one class can define two fields with the same name as long as they
have different types.
- **Statement C**: In Java, two different methods in the same class can have the same parameter
name, and arguments passed to one of those methods don't affect the parameter in the other.

<div class='sidenote'>We changed the name of these files after the initial
release to make it easier for the filename to match a class name you might
choose. Don't use the hyphenated names that were here originally (and if you
don't know what that means, you probably can ignore this).</div> For each,
write a small Java program that demonstrates whether it is true or false. Put
them in the files `Open1A.java`, `Open1B.java`, and `Open1C.java`.

To show that a statement is true, write a Java program that matches the
statement, doesn't produce an error when run, and produces some meaningful
output when `./run`. This means you may want to include an `Examples` class
with some instances of the classes you create to demonstrate this.

To show that a statement is false, write a Java program that matches the
statement and produces an error when run, demonstrating that Java programs
cannot do what the property says.

Include both the program and a screenshot of running the program without error
as your submission; the template has space for both of these.

## Open-Ended 2 (manual)

<div class='sidenote'>We changed the name of this file from
<code>Open2.java</code> to <code>ExamplesR.java</code> to make it easier to
have the class name match the file name.</div>
Create a class named `R` that has a field of type `String` and a field of type
`R`. Give it a default constructor that initializes both fields. Put the class
in a file called `ExamplesR.java`. Add an `ExamplesR` class to this file, and
answer the following questions in that file:

1. Construct an example `R` object. Were you able to? Explain your example if
you were able to, and explain why you think it's not possible if you weren't.

2. On Twitter, it's possible to reply to a reply to a Tweet (that's not a typo,
it's a reply to a reply). This is true of many systems, like email, Facebook
comments, Piazza followups, and so on. With the class structure in `Drill3`
with `ReplyTweet` and `TextTweet` (that is, _without_ changing the fields as
described above), could you construct an example of a reply to a reply to a
Tweet? Why or why not?


## Submission

You will submit _all_ of your files to the `pa3` assignment on Gradescope:

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

