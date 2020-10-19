---
title: Shockload Forces
description: Calculates the force subjected to a body during a shockload event.
#weight: 
---

#### Notes & Use

Calculates the force subjected to a body during a shockload event for the following cases:

* Distance fallen, by stopping distance
* Distance fallen, by wire rope type and diameter
* Distance fallen, by rope (percentage elongation)

#### By Distance
---

##### Terms:

|Variable|Description|Unit|
|-----|-----|-----|
|$m$ | mass| *pounds*|
|$l_{fall}$ | Falling distance | *in*|
|$d$ | Stopping distance | *in*|
|$F_{shock}$ | Force due to shockload| *lbf*|

##### Equation

$$ F_{shock} = m \\, \left( \frac {l_{fall}}{d} + 1 \right) $$


#### By Wire Rope

##### Terms:

|Variable|Description|Unit|
|-----|-----|-----|
|$m$ | mass| *pounds*|
|$l_{fall}$ | Falling distance| *in*|
|$d_{rope}$ | Diameter of wire rope| *in*|
|$l_{rope}$ | Length of wire rope| *ft*|
|$x$ | Wire rope area factor| *unitless*|
|$E$ | 15,000,000 |*psi*|
|$F_{shock}$ | Force due to shockload| *lbf*|

##### Equations

$$ F_{shock} = \left( 
    1 + \sqrt {
        1+ \frac
        { 2 \\, l_{fall} \\, E \\, x \\, d_{rope}^2}
        { 12 \\, m \\, l_{rope} }
}
\right) $$


##### Wire Rope Area Factors

|Type|Factor|
|------|------|
|7x7 GAC|0.471|
|7x19 GAC|0.472|
|6x19W, fiber core|0.416|
|6x19W, IWRC|0.482|
|6x36WS, fiber core|0.419|
|6x36WS, IWRC|0.485|
|8x19W, fiber core|0.366|
|8x19W, IWRC|0.497|


#### By Percent Rope Elongation

##### Terms:

|Variable|Description|Unit|
|-----|-----|-----|
|$m$ | mass| *pounds*|
|$l_{fall}$ | Falling distance | *in*|
|$l_{rope}$ | length of rope | *ft*|
|$F_{rope}$ | force required to acheive manufacturer's stated rope stretch | *lbf*|
|$y$ | elongation | *percentage*|
|$F_{shock}$ | Force due to shockload| *lbf*|

##### Equations

$$ a =  \frac {0.005 \\, y \\, l_{rope} }{F_{rope}} $$

$$ b = -2 \\, a \\, m $$

$$ c = \frac {-m \\, l_{fall}}{12} $$

$$ F_{shock} = \left( 
    \frac
    { -b + \sqrt 
        {b^2 - (4 \\, a \\, c)}}
    {4 \\, a}
\right) $$

#### Sources

[Understanding shock Loads](http://tdt.usitt.org/GetPDF.aspx?PDF=49-2shockloads). Delbert Hall. TD&T, Vol. 49 No. 2 (spring 2013)