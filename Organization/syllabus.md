---
layout: default
title: Concurrent Programming 1
---
<!--
## Instructors

| François Kilchoer                        | Michael Mäder                         | Sylvain Julmy                        |
| ---------------------------------------- | ------------------------------------- | ------------------------------------ |
| Office C10.11                            | Office C10.09                         | Office C10.08                        |
| [mail](mailto:francois.kilchoer@hefr.ch) | [mail](mailto:michael.maeder@hefr.ch) | [mail](mailto:sylvain.julmy@hefr.ch) | -->

## Recommended Books :

* *The JR Programming Language*, by Ronald Olsson and Aaron Keen, ISBN: 1-4020-8085-9
* *Concurrent Programming, Principles and Practice*, by Gregory R. Andrews ISBN: 0-8053-0086-4
* *Principles of Concurrent and Distributed Programming*, by Morchedai Ben-Ari ISBN: 032131283X

## Tentative Plan

| Week | Subject                                                                                                      |
| ---- | ------------------------------------------------------------------------------------------------------------ |
| A1   | Motivation for concurrent programming; critical section problem; introduction to JR                          |
| A2   | Techniques for avoiding interference; Making sure your system is set up                                      |
| A3   | Semaphores: mutual exclusion; Producers and Consumers; first lab description                                 |
| A4   | Barrier synchronization: the technique of passing the baton; Selective mutual exclusion: Readers and Writers |
| A5   | Dining Philosophers; Threads and Semaphores in Java; volatile                                                |
| A6   | Synchronized - Atomic Integer, Locks                                                                         |
| A7   | Sample Exam Questions - lab                                                                                  |
| A8   | <span style="color:red;">Exam</span>                                                                         |
| A9   | Monitors – notation, signaling disciplines – preprocessor with jr                                            |
| A10  | Synchronizing techniques – priority; implementing monitors with semaphores                                   |
| A11  | Lab                                                                                                          |
| A12  | Sleeping Barber Problem - Monitors & Java: pre 1.5 versions                                                  |
| A13  | Lab                                                                                                          |
| A14  | Monitors – the pthread library                                                                               |
| A15  | <span style="color:red;">Exam</span>                                                                         |
| A16  | Lab			                                                                                      |

## Grading

2 Exams during the semester, at least 4 lab programs to turn in. In addition, there is
an oral final exam during the first full week of February. The grade will be computed as follows
(right-click on the formula to zoom):

$$
\frac{\frac{exam_{oral} + \frac{\frac{exam_1 + exam_2}{2} + \frac{\sum^n lab}{n}}{2}}{}}{2}
$$
