---
layout: page
title: "PA9 – UCSD CSE11 S20"
doodle: "../doodle.jpeg"
---

**This is a draft and this notice will be removed when the assignment is
*complete.**

Due **Thursday**, June 4, 10pm.

## Task 1

Finish PA7 if you haven't already. You can submit it to `pa7-resubmit` to
check your work.

(Remember that you can earn credit back for doing that, so it's really worth
it to do so!)

Make sure to finish it _before_ going on to task 2.

## Task 2

Add the following query option to your PA7 implementation:

- `word=<string>` – should match lines where the given string appears either
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

Add the following transform option to your PA7 implementation:

- `range=<number>,<number>` – selects a range of characters from the line
starting at the first number (inclusive) and ending at the second number
(exclusive), like `substring`. If the line is too short for the first index,
the empty string is produced. If the line is too short for the second index,
the transform should take as many characters as possible.

    **Examples**: The transform `range=4, 7` would have the following effects:

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