---
layout: post
title: String vs. StringBuffer vs. StringBuilder
---


## Story
String Class in Java creates an immutable sequence of characters, the ​StringBuilder​ class provides an alternative to String Class, as it creates a mutable sequence of characters. The function of StringBuilder is very much similar to the StringBufferclass, as both of them provide an alternative to String Class by making a mutable sequence of characters. However the StringBuilder class differs from the StringBufferclass on the basis of synchronization. The StringBuilder class provides no guarantee of synchronization whereas the StringBuffer class does.

## Mutability Difference
String is immutable, if you try to alter their values, another object gets created, whereas StringBuffer and StringBuilder are mutable so they can change their values.

## Thread-Safety Difference:
The difference between StringBuffer and StringBuilder is that StringBuffer is thread-safe. So when the application needs to be run in a single thread only, then it is better to use StringBuilder. StringBuilder is more efficient than StringBuffer.

## Situations
- If your string is not going to change use a String class because a String object is immutable.
- If your string can change (example: lots of logic and operations in the construction of the string) and will only be accessed from a single thread, using a StringBuilder is good enough.
- If your string can change, and will be accessed from multiple threads, use a StringBufferbecause StringBuffer is synchronous so you have thread-safety.

<!-- vim: set tw=90 sts=-1 sw=4 et spell wrap: -->
