---
title: Motions
description: Calculates for various dynamic/motion values, and the resultant forces.
#weight:
---

#### Notes & Use

Calculates for various motion-related values:

* time
* max velocity
* acceleration
* deceleration
* distance

Motion profiles are assumed to be trapezoidal in nature, with constant accel, decel, and max speed.

The following calculation order is observed...

1. Changing any value (except Time) will recalculate the Time value
2. The Accel & Decel values (f/s<sup>2</sup>) will remain constant unless the Accel/Decel Distance values are edited.
3. The Top Speed value will remain constant unless the Time value is edited.

##### Forces

The "Forces" dropdown calculates the force required to move a load given the motion values determined above.  Several cases are provided:

* Horizontal moves, in which the load is moved without any sort of lift
* Counter-weight assist moves (CWA), in which the load is lifted via an equally loaded counterweight system.
* Dead Haul, Lift on Acceleration: in which the load is lifted without any means of counterweight.  Acceleration occurs while the load is ascending.
* Dead Haul, Lower on Acceleration: in which the load is lifted without any means of counterweight.  Acceleration occurs while the load is decending.

A friction coefficient input is provided as well.

##### Power

The "Power" dropdown calculates an estimated power requirement based on the motion values and force values above.

#### Terms

$D$ = Total distance of move, *ft*

$D_{a}$ = Accel distance, *ft*

$D_{d}$ = Decel distance, *ft*

$T$ = Total time of move, *second*

$T_{a}$ = Accel time, *second*

$T_{d}$ = Decel time, *second*

$a$ = Acceleration, *ft / sec<sup>2</sup>*

$d$ = Deceleration, *ft / sec<sup>2</sup>*

$v$ = Max speed, *ft per sec*

#### Motion Equations:

Accel Distance:
$$ D_{a} = \frac {a \\, T_{a}^2} {2} $$

Decel Distance:
$$ D_{d} = \frac {d \\, T_{d}^2} {2} $$

Total Time of move:
$$ T = \left( \frac {v}{a} \right) +
       \left( \frac {v}{d} \right) +
       \left( 
        \frac { D - \left( D_{a} + D_{d} \right)}
              {v}
       \right)
$$

#### Forces Equations

$m$ = Mass of moved load, *lbm*

$F_{a}$ = Force required to accelerate, *lbf*

$F_{d}$ = Force required to decelerate, *lbf*

$\mu$ = Coefficient of friction, *unitless*

For Horizonal & CWA movement:
$$ F_{a} = \frac {m}{32.2} \\, a + (m \mu) $$
$$ F_{d} = \frac {m}{32.2} \\, d + (m \mu) $$

Lift on acceleration:
$$ F_{a} = m + \left( \frac {m}{32.2} \\, a \right) + (m \mu)$$
$$ F_{d} = m - \left( \frac {m}{32.2} \\, d \right) + (m \mu)$$

Lower on Acceleration:
$$ F_{a} = m - \left( \frac {m}{32.2} \\, a \right) + (m \mu)$$
$$ F_{d} = m + \left( \frac {m}{32.2} \\, d \right) + (m \mu)$$

#### Power Equations

$P_{hp}$ = power, *hp*

$P_{kW}$ = power, *kW*

&eta; = System efficiency, *percentage*

$$ F = \left|F_{a}\right| \vee \left|F_{d}\right| $$
$$ P_{hp} = \frac {F \\, v}{550 \eta} $$

$$ P_{kW} = 0.7457 P_{hp} $$