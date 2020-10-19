---
title: Piston Force & Speed
description: Calculations for hydraulic and pneumatic piston forces and speeds. 
nav_order:
---

#### Notes & Use

The first section calculates the push force and pull force of a pneumatic/hydraulic piston, with the folowing considerations...

* The cylinder bore and rod have circular cross-sections,
* The rod &Oslash; must not exceed the bore &Oslash;
* The pressure on the opposing face of the piston cup (not the pressuring side) is assumed to be at standard atmospheric pressure

The second part of this calculator calculates values related to the piston speed and displacement, where:

* SCFM (*Standard Cubic Feet per Minute*) units are assumed to apply to pneumatic systems,
* GPM (*Gallons per Minute*) units are assumed to apply to hydraulic systems,
* Time calculations are assumed to have instantaneous acceleration and decelleration,
* $CV_{req}$ calculations are assumed to be of a non-critical pressure drop.

#### Figure


![](/image/piston_diagram.jpg)

#### Terms

$P$ = pressure applied to cylinder, *pounds per square inch*

$D_{bore}$ = Bore diameter, *inches*

$d_{rod}$ = Rod diameter, *inches*

$L_{stroke}$ = linear movement of piston, *inches*

$F_{push}$ = force exerted by piston rod during extension, *lbs force*

$F_{Pull}$ = force exterted by piston rod during retraction, *lbs force*

$f_{gpm}$ = flow supplied to the cylinder, *Gallons per Minute*

$f_{scfm}$ = flow supplied to the cylinder, *Standard Cubic Feet per Minute*

$p_{drop}$ = the expected loss of PSI throughout the system, *psi*

$T$ = Temperature of gas, *&deg;F*

$p_{atm}$ = Atmospheric pressure, *psi*

#### Equations

Calculate the areas of the bore and rod, for use in later calculations...
$$ A = \pi \left( \frac{D_{bore}}{2} \right) ^2 $$
$$ a = \pi \left( \frac{d_{rod}}{2} \right) ^2 $$

Calculate the forces exerted by the cylinder...
$$ F_{push} = PA  $$
$$ F_{pull} = P(A - a)  $$

Calculate the required flow coeficient only if the flow unit is set to *SCFM*...
$$ CV_{required} = 
    \frac
        {60 f_{scfm}}
        {1360}
    \sqrt 
        { \frac
            { G_{air} (T + 460)}
            { p_{drop} (P + p_{atm} - p_{drop})}
        }
$$

Where:

* $G_{air}$ = Specific gravity of fluid (Air = 1)

Calculate the displacement (*inches<sup>3</sup>*)...
$$ V_{push} = L_{stroke} A $$
$$ V_{pull} = L_{stroke} (A-a) $$

Calculate the piston speed (*inches per second*)...

* where flow units = *SCFM*
$$ v_{push} = 
    \frac {f_{scfm}} {A} \times
    \frac {1728}{60} 
$$
$$ v_{pull} =
    \frac {f_{scfm}} {(A-a)} \times
    \frac {1728}{60} 
$$

* where flow units = *GPM*
$$ v_{push} =
    \frac {f_{gpm}} {A} \times
    \frac {231}{60}
$$
$$ v_{pull} =
    \frac {f_{gpm}} {(A-a)}
    \frac {231}{60}
$$

Calculate the time for piston extension (*seconds*)...
$$ t_{push} = \frac {L_{stroke}}{v_{push}} $$

Calculate the time for piston retraction (*seconds*)...
$$ t_{pull} = \frac {L_{stroke}}{v_{pull}} $$

#### Sources

[Engineering Toolbox](http://www.engineeringtoolbox.com/flow-coefficients-d_277.html)