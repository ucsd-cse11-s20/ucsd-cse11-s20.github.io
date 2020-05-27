---
layout: page
title: "PA8 – UCSD CSE11 S20"
doodle: "./doodle.jpeg"
---

# Comparators, Lists, and Exceptions Practice

Due: 10pm on Wednesday, May 27.

In this assignment you'll learn about an important built-in Java interface,
practice with Java lists, and work on understanding how to `throw`
exceptions.

On this assignment, you can share **ideas for tests** with other students in
the course and on Piazza, but you cannot share code with anyone other than
the course staff. If you want to share information about tests, describe them
or use shorthand notation like “try passing in the list `{1, 2, 3}` and you
should expect X as an answer” rather than writing out Java code for it.

Submission checklist:

- In `CompareLists.java`, submitted to the `pa8` assignment:
  - `[ ]` Implementations of `Comparator` classes
  - `[ ]` Sufficient tests for each `Comparator` class you wrote
  - `[ ]` Implementations of array/`List` methods
  - `[ ]` Sufficient tests for each method
- `[ ]` PDF submission of memory diagram for exception, submitted to the
`pa8-stacktrace` assignment

Starter code is available here (includes relevant imports):

[https://github.com/ucsd-cse11-s20/pa8-starter](https://github.com/ucsd-cse11-s20/pa8-starter)

## FAQ
1. **Q: "Where should I write my list comparison tests?"**
- The 18 test cases (and potentially more) should all go in `CompareLists.java`. Make sure to also take a look at the tips and tricks section of the writeup for a convenient way to create Lists in Java!

2. **Q: "Can we use the `Comparator` class for testing?"**
- Yes you can use the class for testing. However, these tests do not count towards the 18 mandatory test cases for the list comparison. 

3. **Q: "Can we assume that at least one element is always in the list?"**
- No. The writeup only states that there will not be null elements in the list. This could be a good test to write to check behavior!

4. **Q: "Are the lists `{1,2, 2, 3, 4}` and `{}` in order?"**
- Yes to both. Repeated elements still means the list is in order and an empty list also considered ordered.

5. **Q: "I'm trying to write tests but Java won't let me do: `newArrayList.add("Hello world");`**
- This is because within a class only field declarations are allowed. To successfully call the add method you can use a braced blocked like in: https://github.com/ucsd-cse11-s20/13-Filter-Array-Creation/blob/master/ArrayUpdateCreation.java#L34 Alternatively, look in the tips and tricks sections on how to create and fill List objects in one line!

6. **Q: What type should the methods in the `XXXCompare` classes return? Some are not explicitly said in the description.**
- You can follow the example of `class CompareDoubles` provided right before the Comparator section. 

7. **Q: I have completed the `Comparator` section of the PA and a single method for List Methods. I want to submit to gradescope but my code is not compiling.**
- Prior to submitting to gradescope, make sure that you have all of the **method signatures** in List Methods. (It is ok to have an incorrect implementation, for example simply return null, because this is solely to get the code to compile)

8. **Q: I am getting "method XXX in class CompareLists cannot be applied to given types" from the autograder but it seemed to be working fine locally.**
- You can double-check your method signature - does it have the correct return type and correct order of parameters as specified in the writeup? 

9. **Q: I am getting an error when I am using `checkExpect` for exception tests.**
- There was a typo in the writeup. It should be `checkException` method instead.


## Comparators and Lists

The
[Comparator](https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Comparator.html)
interface in Java describes operations that compare two values of the same
type. A `Comparator`'s `compare` method should return a negative number if
the first argument is less than the second, 0 if they are equal, and a
positive number if the first argument is greater than the second.

For example, a `Comparator` that compares two `Double`s we could write as:

```
class CompareDoubles implements Comparator<Double> {
  public int compare(Double n, Double m) {
    if(n > m) { return 1; }
    else if(m > n) { return -1; }
    else { return 0; }
  }
}
```

All of your code will go into a single file `CompareLists.java`.

### Comparators

First, write the following implementations of the `Comparator` interface. You
can write them all in the file `CompareLists.java`.

<div class='sidenote'>Hint: not all classes need constructors.</div>
1. Write a class `PointCompare` that implements `Comparator<Point>`
that compares points by the following process
    - If the first point's `y` coordinate is smaller than the other point's
    `y` coordinate, it is smaller; if `y` is greater, it's greater.
    - If the `y` coordinates are the same, if the first point's `x`
    coordinate is smaller, it is smaller, if greater, the first point is
    greater.
    - If the points have the same coordinates, return `0`
2. Write a class `PointDistanceCompare` that implements `Comparator<Point>`
for `Point`s that compares the points' distance from `(0, 0)`. If the first
point's distance is closer to 0, it's smaller, if the distances are equal,
the points are equal, and if the distance is further from 0, the point is
larger.
3. <div class='sidenote'>Remember the method <a href="https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/String.html#compareTo(java.lang.String)">compareTo</a>.</div>
Write a class `StringCompare` that implements `Comparator<String>` that uses the
`compareTo` method on strings for comparison and returns the result of
`compareTo` directly.
4. Write a class `StringLengthCompare` that implements `Comparator<String>` that compares `String`s
by length, where shorter strings are “smaller”.
4. Write a class `BooleanCompare` that implements `Comparator<Boolean>` where
`true` is greater than `false`.

Write at least four `checkExpect` tests for each `Comparator`'s `compare`
method to demonstrate that they work correctly (so at least 20 tests total).

### List Methods

In this part of the assignment, you'll write several generic `List`
methods that make use of the `Comparator` interface. Write these all in a
class named `CompareLists` in `CompareLists.java`.

<div class='sidenote'>Hint: write and test one method at a time!</div>
1. Write a generic method `minimum` that takes a `List<E>` and a
`Comparator<E>` and returns the _smallest_ element in the list according the
comparator, or `null` if the list is empty. Assume there are no `null`
elements in the list.
1. Write an overload of the generic method `minimum` that takes an `E[]` (an
array of `E`) and a `Comparator<E>` and returns the _smallest_ element in the
array according the comparator, or `null` if the array is empty. Assume there
are no `null` elements in the array.
2. Write a generic method `greaterThan` that takes a `List<E>`, a
`Comparator<E>`, and an element `E`, and returns a _new_ `List<E>`
containing just the elements that are _larger_ than the given element
according to the given comparator. Assume there are no `null` elements in the
array.
4. Write a generic method `inOrder` that takes a `List<E>` and a
`Comparator<E>` and returns `true` if the elements in the array list are in
increasing order according to the comparator, and `false` otherwise. If any
of the elements in the list are `null`, throw an `IllegalArgumentException`
with a message that says `"null value in list"`.
4. Write an overload of the generic method `inOrder` that takes an `E[]` (an
array of `E`) and a `Comparator<E>` and returns `true` if the elements in the
array list are in increasing order according to the comparator, and `false`
otherwise. If any of the elements in the list are `null`, throw an
`IllegalArgumentException` with a message that says `"null value in array"`.
3. Write a generic method `merge` that takes a `Comparator<E>` and two
`List<E>`, each of which is in _increasing order_ according to the given
comparator. It should return a _new_ `List<E>` containing all the
elements from both lists in increasing order. If any of the elements in
either list are `null`, throw an `IllegalArgumentException` with a message
that says `"null value in first list"` if it came from the first one, and
`"null value in second list"` if it came from the second one.

Write at least this many tests:

<div class='sidenote'>You can the documentation on how to <a
href="https://course.ccs.neu.edu/cs2510/tester-doc.html#%28part._.Exception_testing%29">test
exceptions here</a>. Testing exceptions is always a little weird-looking
because we need to test for the thrown value, which acts differently than a
normal return value by design! You may find it useful to first write and test
the methods <i>without</i> any exceptions, and then go back and add the
required error cases.</div>
- For each of these six methods, write a `checkExpect` test for three of the
comparators you wrote in the first part (so you should write 18 total tests
for this task). You should write _more_ than this to be confident that your
methods work correctly, but this amount will make sure you have some basic
coverage.
- Make sure that across these tests you use all the comparators
you wrote at least once
- For each method that has throwing an exception in its description, at least
one of the tests should throw an exception, and you should test for it. Tests
for exceptions look like this:

    ```
    t.checkExceptioin(new IllegalArgumentException("message goes here"),
                  this, "inOrder", aTestList)
    ```

    The constructed exception is the expected exception value. The `this`,
    `"inOrder"`, and `aTestList` describe a method call like
    `this.inOrder(aTestList)` in a way that the tester library can call the
    method while checking for the required exception.

### Exceptions and The Stack

Choose one of your methods that throws an exception. Make a method call that
triggers the exception so that the exception you wrote gets reported at the
command line and you can see the stack trace.

Take a screen shot of the stack trace.

<div class='sidenote'>You can draw it in a tool like Google Slides, or by
hand and take a picture, or any other tool you like as long as it's
clear.</div>
Draw a picture of the stack and heap at the time the exception was thrown.
You can use the style from class/the notes with boxes for method calls and
objects/arrays/lists. Put your drawing in the document.

Then, include screenshots of the methods and method calls from your code that
are reported in the stack trace.

You can use this document as a template:

[Stack trace template doc](https://docs.google.com/document/d/1Uxcih8SvaX7WhNKtzNlOUEqdVQrSc_YxzdetKH86Uaw/edit#)

### Submission

Submit your code to `pa8`, and submit your stack trace diagram and
screenshots as a PDF to `pa8-stacktrace`.

### Tips and Tricks

<div class='sidenote'>This is similar to our uses of interfaces vs.
particular implementations of Region or Query!</div>

1. All of the methods are specified to use the type `List`. `List` is an
interface in Java that specifies a number of methods implemented by different
classes, though the most commonly used is `ArrayList`. So you can use `new
ArrayList` when you need to construct a new list in the body of a method, but
use the `List` type for the parameters and return types.

2. Constructing `List`s by using `new ArrayList` and then repeated calls to
the `add` method can be annoying. Instead, you can use this pattern to create
lists in one line:

    ```
    List<String> abc = Arrays.asList("a", "b", "c");
    ```

    This can make writing test data much more pleasant.

3. Leave time to think through `merge`, which takes some careful thought, and
test it thoroughly to make sure you've tried it with lists of different
lengths and contents.

## Just for Fun

Check out the Java documentation on <a
href="https://docs.oracle.com/javase/specs/jls/se13/html/jls-15.html#jls-15.13">Method
References</a> and the <a
href="https://drive.google.com/open?id=1IrjAIZ3RwDxDMVzf3wZ9GRLj-bGFPuBA">video
in this course on lambda expressions</a> for ways to create `Comparator`s
with less code!
