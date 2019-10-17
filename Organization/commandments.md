---
layout: default
title: Concurrent Programming 1
---

# The 10 coding commandments for concurrent programming

For other classes, you are expected to turn in a report. In this class, your code is the report. As such, your
"report" must meet strict criteria, listed below.

<span class="cli">1.</span>
A comment will indicate the purpose of the class. This comment precedes the class declaration.

<span class="cli">2.</span>
An identifier's name indicates as closely as possible its purpose, with the usual exception
of the standard "loop" or iterative variables: `i` , `j` , and `k` . Identifier names
only use the letters: `a-z` , `A-Z` , `0-9` , and underscore `_`.

<span class="cli">3.</span>
Comments: each variable or constant shall have a comment (indicating why it is declared, for
what purpose, how it will be used) on the same line as the variable declaration, as in the
following examples:

```java
int curpos = 0; // current position in the array that is used
                // to contain all producer messages
Random mix = new Random(); // used to mix up thread execution
```

When possible, a variable is initialized upon declaration as in the above example.

Each process, method, or operation shall contain a comment indicating its purpose, immediately
preceding its declaration, as in the following example:

```java
// Expects up to 4 arguments: #processes, #iterations, bridge_len, max_size
public static void main(String args[]) { /* ... */ }
```

A process, method or operation should not be longer than 50 lines.

<span class="cli">4.</span>
Code shall be consistently indented, no less than 3 spaces, but no more than 8 spaces.
The "tab" character should be avoided to preserve indentation across editors, machines, etc.

<span class="cli">5.</span>
“Magic” numbers shall not appear in the code, apart from obvious uses of 0 (zero) and 1 (one).
An exception is granted when collecting program arguments.

<span class="cli">6.</span>
Constants shall be declared in UPPERCASE letters, to be easily distinguishable from other
identifiers.

<span class="cli">7.</span>
No line shall be longer than 120 characters. Watch out for trailing whitespace.

<span class="cli">8.</span>
Each source file contains the CVS keywords `$Header$` and `$Log$` , so that source files contain the
complete revision history. These lines are included in your file in the following manner (careful, they are case sensitive):

<div>
<div style="width:45%; float: left; margin: 0% 5% 0% 0%">
The first line in your source file is
```java

// $HEADER$

```
</div>
<div style="width:45%; float: left; margin: 0% 0% 0% 5%">
The last lines in your file are
```java
/*
** $Log$
*/
```
</div>
</div>

CVS comments indicate what has changed, and why. You include a description of bugs
(symptoms and fixes) and enhancements. The log is the bulk of your "report". Each file should
be checked in separately when appropriate. The log contains information concerning how you
tested your program – what you specifically tested, which program parameters you used, what
bugs were revealed with your tests.

<span class="cli">9.</span>
Source files assume that all the codes, necessary for compilation, are in the local directory; there
are no import statements of your own code. Each lab is a separate project, located in its
own directory. Within a directory, all source is written in the same programming language.

<span class="cli">10.</span>
Exceptions are not ignored. For each catch statement, there is a message and stack trace
printed (or your comment on why a particular exception can be ignored):

```java
try {
  /* Something... */
}
catch (Exception e) {
  System.err.println("Relevant information goes here");
  e.printStackTrace();
}
```

# Penalties

* Failure to follow any of the above rules results in a penalty of 1/2 point of your lab, regardless of the
working state of your program, for each rule violation. In case of gross negligence, this penalty may be
increased.
* A turned-in program that does not compile for whatever reason is penalised 3 points.
Questions regarding any rule are addressed before you turn in your program.
