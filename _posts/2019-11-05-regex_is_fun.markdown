---
layout: post
title:      "Regex is fun"
date:       2019-11-05 11:46:35 -0500
permalink:  regex_is_fun
---


Regular Expression or Regex is a tool that you can use to search for a specific pattern within any text.  It can be used in almost any programming language.  I put together a little cheat sheet for myself here.

Here's a basic list below:

* [abc.]	 It includes only one of specified characters i.e. ‘a’, ‘b’, ‘c’, or ‘.’
* [a-j]      It includes all the characters from a to j.
* [a-z]   	It includes all lowercase characters from a to z.
* [^az]	   It includes all characters except a and z.
* \w	       It includes all characters like [a-z, A-Z, 0-9]
* \d	       It matches for the digits like [0-9]
* [ab][^cde]	It matches that the characters a and b should not be followed by c, d and e.
* \s	        It matches for [\f\t\n\r] i.e form feed, tab, newline and carriage return.


More extensive list:

**Anchors**
^     Start of string, or start of line in multi-line pattern
\A   Start of string
$     End of string, or end of line in multi-line pattern
\Z    End of string
\b    Word boundary
\B    Not word boundary
\<    Start of word
\>    End of word

**Quantifiers**
*      0 or more
{3}   Exactly 3
+     1 or more
{3,}  3 or more
?      0 or 1
{3,5}   3, 4 or 5
(Add a ? to a quantifier to make it ungreedy.)

**Groups and Ranges**
.      Any character except new line (\n)
(a|b)   a or b
(...)      Group
(?:...)    Passive (non-c­apt­uring) group
[abc]   Range (a or b or c)
[^abc]    Not (a or b or c)
[a-q]     Lower case letter from a to q
[A-Q]    Upper case letter from A to Q
[0-7]     Digit from 0 to 7
\x         Group/­sub­pattern number "­x"
(Ranges are inclusive).

**Pattern Modifiers**
g      Global match
i *     Case-insensitive
m *   Multiple lines
s *    Treat string as single line
x *    Allow comments and whitespace in pattern
e *    Evaluate replac­ement
U *    Ungreedy pattern
(*PCRE modifier)

**String Replacement**
$n    nth non-passive group
$2    "­xyz­" in /^(abc­(xy­z))$/
$1    "­xyz­" in /^(?:a­bc)­(xyz)$/
$`     Before matched string
$'      After matched string
$+    Last matched string
$&    Entire matched string
Some regex implem­ent­ations use \ instead of $.

**Character Classes**
\c    Control character
\s    White space
\S    Not white space
\d     Digit
\D    Not digit
\w    Word
\W   Not word
\x     Hexade­cimal digit
\O    Octal digit

**POSIX**
[:upper:]   Upper case letters
[:lower:]     Lower case letters
[:alpha:]    All letters
[:alnum:]   Digits and letters
[:digit:]     Digits
[:xdigit:]    Hexadecimal digits
[:punct:]    Punctuation
[:blank:]    Space and tab
[:space:]  Blank characters
[:cntrl:]     Control characters
[:graph:]  Printed characters
[:print:]    Printed characters and spaces
[:word:]   Digits, letters and underscore


**Assertions**
?=   Lookahead assertion
?!     Negative lookahead
?<=     Lookbehind assertion
?!= or ?<!     Negative lookbehind
?>    Once-only Subexp­ression
?()    Condition [if then]
?()|   Condition [if then else]
?#   Comment


**Escape Sequences**
\    Escape following character
\Q    Begin literal sequence
\E    End literal sequence

"Escaping" is a way of treating characters which have a special meaning in regular expressions literally, rather than as special characters.

**Common Metacharacters**
^
[
.
$
{
*
(
\
+
)
|
?
<
>
The escape character is usually \

**Special Characters**
\n    New line
\r     Carriage return
\t     Tab
\v    Vertical tab
\f     Form feed
\xxx     Octal character xxx
\xhh    Hex character hh
