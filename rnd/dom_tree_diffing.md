# Problem
The vdom tree currently takes too long to rerender on update when there are many
elements. Taking approximately 100ms per 10k elements on a Ryzen 1700x, 3000mhz
RAM and Chrome v75. This document contains research into more effecient ways to
update the vdom patch algorithms.


# Potential Resources
* [Ideal Hash Trees](https://github.com/papers-we-love/papers-we-love/blob/master/data_structures/ideal-hash-trees.pdf)
Potential alternative dom element storage data structure.

* [Profile of an app that adds / removes 100 nodes at a time](Profile-seed-rerender-100nodes-cum.json)
The profile shows that by the time we reach 10k nodes renders are taking
\>500ms.

* [React faster diff algorithm issue](https://github.com/facebook/react/issues/10703)

* [Dodrio](https://github.com/fitzgen/dodrio)
A rust vdom library that uses "bump allocation" to optimize vdom diffing.
