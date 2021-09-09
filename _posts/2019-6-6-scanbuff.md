---
layout: post
title: Scanner vs BufferReader
description: Where's the input?
---



## You must choose 'BufferReader' because it is dumb.
Scanner will parse the file, but BufferedReader will read the file line by line. By parsing, we mean interpreting the given input as tokens such as int, string, decimal, etc.
  
BufferedReader does dumb streaming. It keeps giving back you all characters, which you have to manually inspect if you'd like to match something useful.
  
Scanner is not thread safe, but BufferedReader is synchronized.
  
Scanner has a lot more functionality built into it; it can do all that a BufferedReader can do and at the same level of efficiency as well. However, in addition a Scanner can parse the underlying stream for primitive types and strings using regular expressions. 
  
Last but not the least, BufferedReader has significantly larger buffer memory than Scanner.

## Footnotes
* [Java, The complete reference by Herbert Schildt]



[Java, The complete reference by Herbert Schildt]: https://www.amazon.com/Java-Complete-Reference-Herbert-Schildt/dp/1260440230/ref=dp_ob_image_bk

<!-- vim: set tw=90 sts=-1 sw=4 et spell wrap: -->