---
title: Yoyo Drum Cable Payout
description: Calculates the payout (in feet), and total number of wraps for a yoyo drum.
weight: 3
---

#### Notes & Use

Calculates the payout (in feet), and total number of wraps for a yoyo drum, with the following considerations...

* the yoyo drum must have a single line per groove,
* the calculation is a simplified method that divides the area of the usuable wraps by the cable diameter.  This method is not exact, but is more than adequate for the purposes of stage machines; it estimates the area of the cable pack, and divides that quantity by the cable diameter.  This method does not take into account any cable elongation.

#### Figure

![](../../image/drum_yoyo_payout.jpg)

#### Terms

$D_{id}$ = Smallest diameter of drum wrap (tread diameter), typically when the yoyo drum is empty. Does not include safety wraps, *inches*

$D_{od}$ = Outer diameter of drum, typically the diameter when the yoyo drum is full, *inches*

$d_{cable}$ = Cable diameter, *inches*

$w_{inner}$ = number of safety wraps on the Tread Diameter

$w_{outer}$ = number of safety wraps on the Outer Diameter.  This ensures the cable will not over-fill the drum and spill over the cheekplates

$L = payout, the length of usable cable that will fit on the yoyo drum, *feet*

$w_{usable}$ = number of usable wraps, does not include safety wraps

#### Equations

Calculate the smallest diameter of the yoyo drum when the safety wraps are included...

$$ D_{Isafe} =
    D_{id} + 2 w_{inner} d_{cable}
$$

Calculate the largest diameter of the yoyo drum when the safety wraps are included...

$$ D_{Osafe} = 
    D_{od} - 2 w_{outer} d_{cable}
$$

Return the payout...
$$ L = \frac
        {   \pi \left( \frac{ D_{Osafe}} {2} \right)^2 -
            \pi \left( \frac{ D_{Isafe}} {2} \right)^2
        }
        {12 d_{cable}}
$$

Return the number of wraps:
$$ w_{usable} = \frac 
        {D_{Osafe} - D_{Isafe}}
        {2 d_{cable}}
$$

#### Sources