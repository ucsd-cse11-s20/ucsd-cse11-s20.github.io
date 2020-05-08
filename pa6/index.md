---
layout: page
title: "UCSD CSE11 S20 – PA6"
doodle: "./doodle.jpeg"
---

# PA6 -- Programming Workflow

<p style="border: 2px dotted red; padding: 1em;">
This is a draft, this notice will be removed when the PA is finalized.
</p>


This PA will give you an opportunity to reflect on how you work through
programs.

You will also submit a survey (required) about your experience in the course.

## Task

Make a copy of this Google Doc (link). You will fill it in as you work.

<div class='sidenote'>If your living/working situation doesn't afford you 90
minutes of uninterrupted time, feel free to break up the timed chunks. Do
your best to do something like 25 minutes with 5 minutes of notes three
times and follow the spirit of the assignment.</div>
Set aside 90 continuous uninterrupted minutes for this task.

You will write programs:

- In a file called `AveragePositives.java`, write a class with a `main`
method that expects all the command-line arguments to be appropriate inputs
to `Double.parseDouble`. It should print the average (mean) of the
command-line arguments that, when parsed as doubles, are strictly greater
than 0. If there are no numbers in the array that are greater than 0, it
should produce 0.

  Try out at least _six_ different uses of `AveragePositives` at the command
  line with different lists of numbers that convince you it works for all of
  the important cases.

- In a file called `PairSelect.java`, add a class `Pair` with fields `a` and
`b` of type `int`. In a class called `PairSelect`, write a method `getAs`
that takes an array of `Pair` and returns an array of `int` that contains the
`a` field of all the `Pair`s in the array given as an argument. Write at
least 4 `checkExpect` tests for it to cover interesting cases.

- In a file called `LongStrings.java`, write a method called `longStrings`
that takes an array of `String` and an integer `n` and produces an array of
`String` that are just the strings in the array that have length `n` or
greater. Write 4 `checkExpect` tests for it to cover interesting cases.

- Copy the `Point` class from the [regions
code](https://github.com/ucsd-cse11-s20/08-Abstract-Classes) in lecture into
a new file called `ClosestPoints.java`. Write a class called `ClosestPoints`
with a `main` method that expects to get six command line arguments,
representing the x and y coordinates of three points. For example:

    ```
    $ java ClosestPoints 0 0 3 4 3 900
    ```

    Would represent the points (0, 0), (3, 4), and (3, 900). Your program
    should print out the pair of points that are closest to one another out
    of the three points, using the format below:

    ```
    $ java ClosestPoints 0 0 3 4 3 900
    The closest points are (0, 0) and (3, 4) at distance 5.0
    ```

Set a timer for 25 minutes – work on these tasks for that much time. Then,
take a screenshot or copy/paste your code and the output of the most recent
time you did `./run`. Put that output into the Google Doc at the 25 minute
mark, and write down 2-3 sentences about your thought process at this point –
don't spend more than 5 minutes on the notes. Also note if you got distracted
(you don't have to tell us how) by another browser tab, your phone, etc
during that 25 minutes. Just say yes/no and how many minutes you think you
were distracted for.

Set another 25 minute timer and work for another 25 minutes, then repeat
taking notes. Then do this one more time, for a total of 3 25-minute sessions
each followed by note-taking.

If you don't finish the task, still stop after 90 minutes and put the notes
in place (it's not expected that you must finish in 90 minutes!). If you
finish early, note the time you finished.

## Reflection

After you're done with the 90 minutes, reflect on the following:

- Where did you spend the most time? You might have different descriptions,
some I can think of that I spend a lot of time on are below; you might have
others.
  - Thinking about a particular part of the program
  - Understanding an error message
  - Figuring out why a particular test wasn't working
  - Typing
- What could you do to reduce the time taken in the future?
- How did this process compare to how you usually complete PAs?
- Overall, what did you learn from this experience about your programming
workflow, if anything?

## Finishing

You must still finish these programs as part of the assignment. There is no
autograder for them released while the assignment is out; we will grade them
manually after the deadline. Come ask for help in tutor hours if you need
help finishing them, but we think the assignment will be most effective if
you do the 90 minutes first.

## Submission

Export your notes document as a PDF using Google Docs (under the File menu).
You'll hand it in under the `pa6-notes` assignment on Gradescope.

You'll hand in the four `.java` files to the `pa6-code` assignment on
Gradescope.

## Challenges and Extra Practice

If you want more practice or an extra challenge, try writing the programs
below. These are not for credit, but feel free to ask us about them on
Piazza if you found them interesting!

- Make `ClosestPoints` work for any number of points input on the command
line.
- Write a method `zip` that takes two arrays of `int` that have the same
length and produces an array of `Pair` where the `Pair`'s `a` and `b` fields
are the values in the corresponding index in the first and second provided
`int` array.
- Write a method `unzip` that takes an array of `Pair` and returns two
arrays, one containing the `a` elements and one containing the `b` elements.
Decide how to represent the return value yourself.
