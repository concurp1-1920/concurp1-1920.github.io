---
layout: default
title: Concurrent Programming 1
---

# TP 4 : The Swiss Bank Java

Nowadays, some inhabitants of Switzerland are all sharing a unique bank account.
Each person can make payments and withdrawals. The current balance is the sum of
the payments minus the sum of the withdrawals; the balance must **not** become negative.

You have to create a monitor who manages this bank. Two operations are visible
in order to make payments and withdrawal, which correspond to the interface
visible by the users. Hence the actions of the bank can be simply modeled as

```java
process person(( many )) {
  print "Start person xyz"
  for (iteration) {
    if(withdrawal probability) {
      balance = monitor.deposit(x);
      print "After a deposit of " + x + ", the balance is " + balance;
    } else {
      balance = monitor.withdraw(y);
      print "After a withdrawal of " + y + ", the balance is " + balance;
    }
  }
  print "Person xyz finished after iteration loops"
}
```

Note that, here, it is the person’s process who prints the balance, but the bank can do it too.

Similarly to the previous TPs, all the arguments are **optional**,
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
- The amount of money a person withdraws or deposits in the bank is a random number between `1` and `maxWithdrawal` and
  `maxDeposit` respectively.
- If the bank is fair, then processes can't go ahead and pass any process waiting for the balance to be high enough.
- Since a conditional variable represent a waiting queue of processes, you should **not** represent such a queue by any other classes or structures who implement a waiting queue.
- All critical sections are encapsulated **inside a monitor**.
- You are not allowed to use **busy waiting**.
- Java monitors support the **signal and continue** signaling method.
- You have to detect  deadlock if there are some. In this case, you have to terminate the processes properly and **they should print their number of successful iteration**.

Note: Your program will be invoked via `java` - make sure you test with these commands. You
must have a class called `Bank` in a file called `Bank.java`.


**Examples of invocation** :
- `java Bank`
- `java Bank 0`
- `java Bank 101 43 1`
- `java Bank 100 10 10 0.0 10 10`
- `java Bank 101 43 37 0.41 17 29`
- `java Bank 101 43 37 0.41 17 29 NF`
- `java Bank 1000 100 1 1.0 10 1`

The date and time of submission via **CVS** is :
- For the class **I2a** : 24.01.2020 at 8:00.
- For the classes **I2b** and **I2d** : 22.01.2020 at 8:00.
