---
layout: page
title: "UCSD CSE11 S20 – PA3"
doodle: "/doodle.png"
---

# Programming Assignment 3 – Class Practice

<p style="border: 2px dotted red; padding: 1em">
This is a draft
</p>

This programming assignment will help you practice writing classes.

You will upload _several_ Java files for this assignment, detailed below.

## Drill 1

Write three classes as described below. They do not need to have any methods or
constructors. Save them in Drill1.java.

- A class named `A` with two fields, `int f1` and `String f2`
- A class named `B` with two fields, `A field1` and `String field2`
- A class named `C` with three fields, `B fieldB`, `A fieldA`, `int field3`

## Drill 2

Write a file containing the following class definitions:

```
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

## Drill 3






