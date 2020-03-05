---
layout: default
title: Concurrent Programming 2
---

# Lab5 : Zero

You're asked to write a (JR)library that looks for the real zeros of a function given as parameter.  You will have to implement 2 different ways of searching the zeros (e.g. Bisection, Secant, Newton, ...). Your program will take the following command line parameters, whereas the first 4 are mandatory: 


1) The lower limit from which you start the search for zeros (`double`)

2) The upper limit where the search ends (`double`)

3) The number of intervals to be examined in the upper and lower limits (`int`)

4) The "precision" of your zero (`double`)

5) Bitmask, which selects the function to be displayed. The function will be used if the corresponding _bit_ is _on_ (i.e. the value is 1). By **default**, this parameter is set to 127 (`int`).
<br>Function f1=1, f2=2, f3=4, f4=8, f5=16, f6=32, f7=64

6) The format to be used for the display of the results, by **default** `%a` (`string`)


So, for example, your program could be invoked in the following way (intervall -10 .. 10, 200 steps, 0.001 precision of zero, fun1 & fun2, and output format in %1.5e), which would have the result below:

```bash
$ jrgo -10 10 200 0.001 3 %1.5e

fun1: Bisection method
f(5.67187e-01) = 1.22165e-04
fun1: Secant method
f(5.67095e-01) = -1.34445e-04

fun2: Bisection method
f(-2.86719e-01) = 3.27323e-05
f(1.02773e+00) = -4.44069e-04
fun2: Secant method
f(-2.86817e-01) = 1.72750e-04
f(1.02779e+00) = -2.00672e-04
```

**Notes and specifications** :

- One of the public functions of the library is `zero`, which takes in parameter the following elements: 
  - `lower limit`
  - `upper limit`
  - `number of intervals`
  -  `precision`
  -  `search method`
  - `the function for which we would like to find the zeros`
  - `a function provided by your main program that will be called by the library when a zero is detected (call back)`
- The other public functions are the search algorithms that you will have to implement. It is one of these 2 functions that will be the 5th parameter of the `zero` function.
- Your library must be coded in such a way that if you add a function that implements a new search method, this new search method is usable without further modifications to the library!
- All other functions you would need in your library are private.



**Functions to implement** :

fun1: $$xe^{x}-1$$

fun2: $$(x^2 - \sqrt{2})e^{x}+1$$   ([Example](https://www.wolframcloud.com/objects/dcae3828-04a3-4395-ba02-8ef05e2f01fb) )

fun3: $$\sin(\frac{x}{2})+\frac{\cos(\frac{x}{4})}{2}$$

fun4: $$(x^2-\pi^2)(x^2-(\frac{355}{113})^2)-(x^2-(\frac{484}{49}))(x^2-(\sqrt{2}+\sqrt{3})^2)$$

fun5: $$x^5-(\frac{5}{2}+\sqrt{2}+\sqrt{26})x^4+(\frac{5}{2}(\sqrt{2}+\sqrt{26})-11+2\sqrt{13})x^3-(\frac{15}{2}-11(\sqrt{2}+\sqrt{26})+5\sqrt{13})x^2+(\frac{15}{2}(\sqrt{2}+\sqrt{26})-22\sqrt{13})x-15\sqrt{13}$$

fun6: $$\sin(\frac{1}{e^{x^{2}+2x-2}})$$

fun7: $$e^{\sin(x)}-\frac{\sin(x)}{e^{\sin(x)}}-1$$

You are, of course, free to implement other functions to test your program. These "debug" functions are only calculated if their "bit" is "on".

**Functions to implement** :

Your library is called **`ZeroLib`**.  Your main class is called **`ZeroTest`**.  These 2 classes are in **separate files**.  The final version of your code must be in CVS before Friday March 6 2020, 23:59.
