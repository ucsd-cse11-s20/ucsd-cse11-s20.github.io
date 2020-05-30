---
layout: page
title: "PA9 – UCSD CSE11 S20"
doodle: "/doodle.png"
---

**This is a draft and this notice will be removed when the assignment is
complete.**

# PA9 - More String Manipulation
Due **Thursday**, June 4, 10pm.

In this assignment, you will extend from PA7 and add more string manipulation 
features. 

Different assignments in this course have different collaboration policies.
On this assignment, you cannot share code publicly on Piazza or with anyone
other than the course staff. If you need to share code, ask in a private
Piazza post or in 1-on-1 hours. Still do ask any public code questions about
lecture code, quizzes that are past, or other conceptual questions, just no
code from this PA. You can't get help from anyone but the course staff on
this PA.

On this assignment, we **encourage** you to share publicly and with other
students what you think the expected output should be on particular examples.
For example, you could share a `java StringSearch ...` command you tried out,
and show the results, and check with other students if they agree on the
behavior. This allows you to discuss how the assignment is supposed to work
without sharing any code, and you also might want to share examples you found
interesting!

## Task 1

Since this PA is an extension of PA7, finish PA7 if you haven't already. 
You can submit it to `pa7-resubmit` to check your work.

(Remember that you can earn credit back for doing that, so it's really worth
it to do so!)

Make sure to finish it _before_ going on to task 2.

## Task 2
Starter code here: link TODO. 

You can use the starter code provided, or directly
continue work on your PA7 `StringSearch.java` if it passed PA7 autograder tests. 

Note that you can get a significant amount of credit for just the PA9 tasks (based
on starter code), but getting _full credit_ requires that you get PA7 working.

1. Add the following query option to your PA7 implementation:

    `word=<string>` – matches lines where the given string appears either
    at the beginning of the line followed by a space, the end of the line
    preceded by a space, or somewhere in the middle of the line with spaces on
    either side.

    **Examples**: The query `word=bat` would match these lines:

    - `bat man really should be written as one word`
    - `step up to the bat`
    - `didn't bat an eye`

    It would not match these lines:

    - `battery-powered`
    - `bubble bath`

2. Add the following transform option to your PA7 implementation:

    `range=<number>,<number>` – selects a range of characters from the line
    starting at the first number (inclusive) and ending at the second number
    (exclusive), like `substring`. If the line is too short for the first
    index, the empty string is produced. If the line is too short for the
    second index, the transform should take as many characters as possible.

    **Examples**: The transform `range=4,7` would have the following effects:

    - `hello` → `o`
    - `four` → an empty string
    - `parametric` → `met`

## Task 3

Answer the following questions in the `README` file.

- Around how much code did you **add** in order to add these new features?
Identify the new classes/methods/parts of methods that were added.
- Around how much code did you **change** in order to add these new features?
Identify the code that was there before and after.
- If you made _other_ changes to your program to add these features,
describe those changes as well.


## Submission

Submit your `StringSearch.java` to `pa9` on Gradescope. There will be an 
autograder available while the assignment is out, and we will also give you 
feedback on your code after submission. 

Due to graders' bandwidth and the grading of the two exams, we **do 
not have resubmission** on this PA. 
