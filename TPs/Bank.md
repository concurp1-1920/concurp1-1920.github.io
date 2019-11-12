---
layout: default
title: Concurrent Programming 1
---

# TP 3 : The Swiss Bank

Nowadays, some inhabitants of Switzerland are all sharing a unique bank account.
Each person can make payments and withdrawals. The current balance is the sum of
the payments minus the sum of the withdrawals; the balance must not become negative.

You have to create a monitor who manages this bank. Two operations are visible
in order to make payments and withdrawal, which correspond to the interface
visible by the users. Hence the actions of the bank can be simply modelled as

```java
process person(( many )) {
  print "Start person xyz"
  for (iteration) {
    if(deposit probability) {
      balance = monitor.deposit(x);
      print "After a deposit of " + x + ", the balance is " + balance;
    }
    else {
      balance = monitor.withdraw(x);
      print "After a withdrawal of " + y + ", the balance is " + balance;
    }
  }
  print "Person xyz finished after iteration loops"
}
```

Note that it is the person’s process who prints the balance, but the bank can do it too.

Similarly to the previous Tps, all the arguments are optional,
and are in the following order on the command line.

```
0) Initial balance                                     ( default 101)
1) Maximal withdrawal                                  ( default 43)
2) Maximal payments                                    ( default 37)
3) Withdrawal probability                              ( default 0.41)
4) Number of persons processes                         ( default 17)
5) Number of iterations per processes                  ( default 29)
6) Fairness of the Bank, models by “NF” present or not ( default true)
```

**Specifications** :
- If the bank is fair, then processes can't go ahead and pass any process waiting for the balance to be high enough.
- Since a conditional variable represent a waiting queue of processes, you should **not** represent such a queue by any other classes or structures who implement a waiting queue.
- All critical sections are encapsulated inside a monitor.
- You are not allowed to use **busy waiting**.
- You should use the **signal and continue** signalling method. You have to detect
  deadlock if there are some. In this case, you have to terminate the processes
  properly and **they should print their number of successful iteration**.
- Your program will be invoked via `jrgo` and `jrgox` -  make sure you test with
  these commands. You must have a class called Bank in a file called Bank.jr

**Examples of invocation** :
- `jrgo 100 10 10 0.0 10 10`
- `jrgo 101 43 37 0.41 17 29`
- `jrgo 101 43 37 0.41 17 29 NF`
- `jrgo 1000 100 0 1.0 10 1`

The date and time of submission via **CVS** is :
- For the class **I1a** : 16.12.2019 at 8:00.
- For the classes **I1b** and **I1d** : 18.12.2019 at 8:00.
