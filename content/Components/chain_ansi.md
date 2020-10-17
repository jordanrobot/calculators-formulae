---
title: ANSI Chain Calcs
weight: 1
---

#### Notes & Use

A collection of lookups and calculations for ANSI standard roller chains.

All ANSI reference values are from manufacturers' catalogues.

#### Calculations

##### Length

The chains' length conversion between inches and pitches is calculated by the folling formula:

$$ L = P \times p $$

where:

* $L$ = chain length, *inches*
* $P$ = chain length, *pitches*
* $p$ = chain pitch distance, determined from ANSI values

##### Weight

The weight of the chain is calculated as...

$$ W =\frac {L \times w}{12} $$

where:

$W$ = weight of length of chain, *lbs*

$w$ = weight of chain, determined from ANSI values, *lbs per foot*

$L$ = length of chain, *inches*

##### Elongation


Elongation of the chain is determined as follows...

$$ l = \frac {L}{12} \times \frac {T}{k_{elongation}} $$

where:

$l$ = elongation of chain length due to stretch, *inches*

$L$ = length of chain, *inches*

$T$ = chain tension, *lbf*

$k_{elongation}$ = a stretch factor.  Interpolated from a data from Tsubaki.  This value is determined by the selected chain size. 

##### Center to Center

Calculate the center distance of the two shafts when the chain's pitch length is given...

* Only applicable to two-sprocket systems.

$$ C_{dist} = 
\frac {p}{8} \times 
    \left(2P - N - n \right) +
    \sqrt{
        \left(2P - N - n \right)^2 -
        \frac {8}{\pi^2} \times
        (N - n)^2
    }
$$

where:

$C_{dist}$ = Center-to-center distance of shafts, *inches*

$P$ = chain length, *pitches*

$p$ = chain pitch distance, determined from ANSI values

$N$ = number of teeth on larger sprocket

$n$ = number of teeth on smaller sprocket

Calculate the pitch length of a chain when the ceter-to-center distance of the two shafts are given...

$$  P =
    2 \frac {C_{dist}}{p} +
    \frac {N+n}{2} +
    \frac {(\frac {N-n}{2 \pi})^2}{ \frac {C_{dist}}{p}}
$$

##### Sprocket Properties

Calculates properties for a sprocket of user selected size and tooth number...

$$ D_{p} = p \times sin \, t_{no} $$
$$ D_{o} = 
    p \times
    \left(
        0.6 + \frac {1}{tan \, t_{no}}
    \right)
$$
$$ t_{width} = 0.93 c_{width} - 0.006 $$

where:

$p$ = chain pitch distance, determined from ANSI values

$t_{no}$ = number of sprocket teeth

$t_{width}$ = width of sprocket teeth

$D_{p}$ = pitch diameter, *inches*

$D_{o}$ = outside diameter, *inches*

#### Sources

* [Martin Sprocket and Gear, Inc.](http://www.martinsprocket.com/)
* [The Complete Guide to Chain](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&sqi=2&ved=0CDYQFjAB&url=http%3A%2F%2Ftsubaki.ca%2Fpdf%2Flibrary%2Fthe_Complete_guide_to_chain.pdf&ei=IDPOUs23H-iysQTR-IGgDA&usg=AFQjCNFWliiEgppS2iq6WkGIxkFA8yk6gA&sig2=QmdCHxY8d3SxVsX9lVH-5A&bvm=bv.59026428,d.cWc), U.S. Tsubaki.
* [Diamond Chain](http://www.diamondchain.com/)
* [Misumi USA](http://us.misumi-ec.com/), Chain Design
