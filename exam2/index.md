---
layout: page
title: "UCSD CSE11 S20 – Take Home Exam 2"
doodle: "/doodle.png"
---

# Exam 2

This page details a **take-home exam** that you will complete over the next
few days. You can't communicate with anyone about the content of the
assignment until you receive your grade. The course staff will not give
debugging advice or answer questions about the problems. If you have
technical trouble creating a screencast (detailed below) feel free to reach
out for assistance.

You **can** make use of any course notes, online resources, Java tools, and
so on to complete the exam.

You will complete the programming tasks 1 and 2 in the file `ArrayExamples.java` in the `ArrayExamples` class. Task 3 should be implemented by adding to the file `ExamplesSearch.java`. You should submit both files `ArrayExamples.java` and `ExamplesSearch.java` to the `exam2` Gradescope assignment.

You will also submit a **video screencast** of yourself presenting a portion of it to this [Google Form](https://forms.gle/rqVp7JGDP1gt5TxH6).

Submission checklist (see long descriptions below for full details):

- `[ ]` `findSecond` method in the `ArrayExamples` class
- `[ ]` `findNth` method in the `ArrayExamples` class
- `[ ]` A comment describing the `mystery` method in `ArrayExamples`
- `[ ]` A test for the `mystery` method in `ArrayExamples` that threw an exception in the original implementation of that method
- `[ ]` Modified the `mystery` method to not throw exceptions
- `[ ]` `AllQuery` class
- `[ ]` Constructed three instances of `AllQuery` with specified array lengths
- `[ ]` Six tests using these constructed `AllQuery` objects
- `[ ]` Screencast
  - Show ID
  - Trace evaluation of the `AllQuery` test


Your submission will be graded **after** the deadline. The Gradescope upload
will just check to make sure that there aren't any errors reported by Java
when we try to run your programs, not whether tests succeeded or failed. You
should test thoroughly yourself to make sure your program works as expected.

## Tasks

Download this starter code:

[https://github.com/ucsd-cse11-s20/exam2](https://github.com/ucsd-cse11-s20/exam2)

(The `ExamplesSearch` class is identical to the start code from Exam 1)

You should **not** change any of the existing methods or classes except for the `mystery` method, and adding to `ArrayExamples` and `ExamplesSearch`. Don't change `ImageQuery` or the other query classes, just add new ones as described below.


### Task 1

1. Add a **method** to the `ArrayExamples` class called `findSecond` that takes a `String[]` and a `String` and returns the _index of the second time_ that string appears in the array, or `-1` if it appears in the array 1 or 0 times. For example, for the array input `{"a", "b", "a", "a"}` and

   - the string input `"a"`, it should produce 2.
   - the string input `"b"`, it should produce -1.
   - the string input `"c"`, it should produce -1.

2. Add another method to the `ArrayExamples` class called `findNth` that takes a `String[]`, a `String`, and an `int` `n`. It should behave the same as `findSecond`, but look for the _index of the `n`th time_ the string appears in the array. For example, for the array input `{"a", "b", "a", "a"}`

   - the string input `"a"`, and int `2`, it should produce 2.
   - the string input `"a"`, and int `3`, it should produce 3.
   - the string input `"a"`, and int `4`, it should produce -1.
   - the string input `"b"`, and int `2`, it should produce -1.
   - the string input `"c"`, and int `2`, it should produce -1.

You can assume that all inputs to both of these methods are not `null`, and `n` is always greater than 0. You are not required to write tests for these methods, though as always we encourage you to do so.

### Task 2

1. Consider the `mystery` method in the `ArrayExamples` class. Write a comment above this method describing what it does in a *single* English sentence.
2. Write a test for `mystery` which calls it with an input **other than** `null` for `nums` which causes an exception when run. Write this test as a field named `taskTwoTest` in `ArrayExamples`.
3. Change the `mystery` method so that **no inputs** can cause an exception to be thrown, and the method instead returns an empty array for the inputs that caused exceptions on the original version. Note that you must _modify_ this method, not write a new method. You may only use Java constructs we have learned in this class, and you must ensure that mystery's behavior does not change on valid inputs. You can always go back to the web page for the starter code to see the original version if you make edits and want to see the original again.

### Task 3

1. In the file `ExamplesSearch.java`, add a new class called `AllQuery` implementing `ImageQuery`. It should have a field of type `ImageQuery[]` and a corresponding constructor to initialize that field. Its `matches` method should return `true` when _all_ of the queries in the list match the given image. If the query array is empty, `matches` should return `true` for any `ImageData`.

2. Create three `AllQuery`s with arrays of size 1, 3 and 5, each containing different queries. Demonstrate using each query's `matches` method on at least two different `ImageData` inputs, once returning `true` and once returning `false`. So at least 6 tests in total. (You can and should write _more_ tests than this to ensure that the class works as you expect, but this is what we'll check for).

### Task 4 – Video

You will record a short video of no more than 5 minutes. Include:

- Your face and your student ID for a few seconds at the beginning. You don't
  have to be on camera the whole time, though it's fine if you are. Just a
  brief confirmation that it's you creating the video/doing the work attached
  to the work itself is what we want.
- For the `AllQuery` with array of size 3 that you created in [Task 3](#task-3):

  Run the `ExamplesSearch` program and show the output corresponding to a method call for this example. Then, starting from the line in your code with the call to the `matches` method, indicate each line of code that runs in your program while evaluating that method call. You can scoll to and click the lines to highlight them, or otherwise indicate each one. You should indicate them in the order that **Java will evaluate them** (this might be different than the order they appear in the file).

An example of what your video should look like when doing this kind of
explanation is here:

[https://drive.google.com/open?id=1E-TcVXSg9BI4MnWoVU9_BbcRJsu8ZhCf](https://drive.google.com/open?id=1E-TcVXSg9BI4MnWoVU9_BbcRJsu8ZhCf)

PA5 has a tutorial for creating a screencast like this
[https://ucsd-cse11-s20.github.io/pa5/](https://ucsd-cse11-s20.github.io/pa5/).
