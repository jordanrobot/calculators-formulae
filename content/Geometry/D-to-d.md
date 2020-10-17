---
title: "D:d Ratio"
description: Calculates the D:d ratios for given pulley and cable sizes.
#weight:
---

#### Notes & Use

Calculates:

* D:d ratios for given pulley and cable sizes
* Adjusted capacity of wire rope due to D:d bend
    - Note: that at a D:d ratio of 10 and less, permanent distortions of the rope will occur. (This is a general rule of thumb, different construction ropes will vary.)

#### Figure

![](../image/pulleys.jpg)

#### Terms

$D_{tread}$ = Tread diameter, *inches*

$D_{cable}$ = Cable diameter, *inches*


#### Equations

Pitch Diameter, *inches*:
$$ D_{pitch} = D_{tread} + D_{cable}$$

D:d ratio, unitless:
$$ D:d = \frac {D_{pitch}} {D_{cable}} $$

Calculate the adjusted tensile strength of wire rope, *percentage*:

$$ F_{T-adjusted} = 1 - \frac {0.5}{\sqrt{D:d}} $$

#### Sources

[Wire Rope](http://catalog.mazzellalifting.com/Indexes/WireRope/Pages133134.aspx). Mazzella Lifting Technologies, pp. 133-134.

[Steel Rope Technical Information](http://www.bridon.com/x/downloads/steel_technical.pdf). Bridon International Ltd, pp 34.