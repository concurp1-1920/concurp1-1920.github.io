---
layout: default
---

A long, long time ago, in a galaxy far, far away, the inhabitants of the planet Vogon (Vogons) had to meet
with the beings of planet Bezerk (Bezerki) on the moon Magrathea in order to exchange information on the
coming intergalactic summit.

According to the protocol agreed upon by the Bezerkis and the Vogons, a Vogon goes to Magrathea, and
waits to meet 2 Bezerkis to exchange information before leaving the moon; BEzerkis, on the other hand,
meet just 1 Vogon before leaving the moon. Either Bezerkis or Vogons leave Magrathea without meeting
anyone else once they have met the required number of other beings (in fact, they must leave).

Your job is to write a simulation of the interactions between Bezerkis and Vogons. Bezerkis and Vogons
are simulated via processes, and synchronization is provided by Semaphores. Hence, the actions of Bezerkis
and Vogons can be simply modeled as

<div>
<div class="leftCol">
```java
process Bezerki {
  nap(Btime)
  for (iteration) {
    print "Heading for Magrathea"
    meetVogon()
    print "I've met a Vogon"
    print "I'm off to meeting"
  }
}
```
</div>
<div class="rightCol">
</div>
```java
process Vogon {
  nap(Vtime)
  for (iteration) {
    print "Heading for Magrathea"
    meetBezerki()
    print "I've met 2 Bezerkis"
    print "I'm off to meeting"
  }
}
```
</div>

The parameters for this simulation are
```
0) The number of Bezerki processes                                            ( default 43)
1) Bezerki iterations                                                         ( default 37)
2) Number of Vogon processes                                                  ( default 41)
3) Vogon iterations                                                           ( default 17)
4) number of milliseconds a Bezerki process waits before doing its iterations ( default 0)
5) number of milliseconds a Vogon process waits before doing its iterations   ( default 0)
```

Once you're satisfied that your solution works in the general case, take care of terminating your program
properly - in other words, each remaining Vogon and/or Bezerki must finish with the line `Vogon vv has
finished after jj iterations` / `Bezerki bb has finished after kk iterations` respectively ( `vv`
and `bb` are the respective process ids of Vogons and Bezerkis, `jj` and `kk` their remaining iterations.

Note: Your program will be invoked via `jrgo` and/or `jrgox` - make sure you test with these commands. You
must have a class called `Magrathea` in a file called `Magrathea.jr`.
