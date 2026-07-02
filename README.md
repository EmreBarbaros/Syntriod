<div align="center">


# Syntriod

**Orbital solution of binary stars using synthetic template radial velocity curves.**

<img width="640" height="480" alt="ezgif-2e9807fdef2c8e4d" src="https://github.com/user-attachments/assets/75b2b663-09df-46f7-a9a1-8994776976b1" />
</div>

## Overview
The radial velocity solution is the process of determining orbital parameters of binary star systems from their observed radial velocities, via a theoretical Kepler orbit. By phasing the observed velocities with the correct orbital parameters, the system parameters can be determined precisely.

The orbital parameters in question are:
* Orbital period ($P$)
* Time of periastron passage ($T_0$)
* Eccentricity ($e$)
* Argument of periastron ($\omega$)
* Velocity semi-amplitudes of the components ($K_{1,2}$)
* Systemic velocity ($\gamma$)

## The Problem with Classical Methods
In the literature, these parameters are typically determined using MCMC-based radial velocity fitting codes. Among these parameters, the period ($P$) is the most critical for the radial velocity solution of a binary system and requires prior information before the fitting process. Therefore, standard software in the literature often initializes the radial velocity fit using an initial period estimate derived from classical periodograms like Lomb Scargle.

These periodograms are often susceptible to harmonics and aliasing, and they struggle to determine the correct period in cases of sparse sampling. Furthermore, they provide no information regarding the other system parameters.

## Syntriod: A Robust Initial Parameter Estimator for Radial Velocity Curve 
**Syntriod** determines the full set of orbital parameters for a binary system by matching observational data to pre-generated synthetic radial velocity templates, without employing any optimization routines. This process takes only **~5 seconds** and achieves high parameter precision.

This is accomplished through a suite of specialized mathematical algorithms, including alias and harmonic control mechanisms, frequency analysis in both the time and phase domains, and an extensive template library. Consequently, Syntriod can deliver the full set of parameters with high precision, even for systems with as few as **6 data points**.

### Workflow
<img width="6000" height="2400" alt="workflow" src="https://github.com/user-attachments/assets/d13a66e2-e077-475a-a0b8-5cf4fe09ba4f" />

> *Syntriod is neither a standard periodogram nor a traditional radial velocity fitting code; rather, it is a parameter estimation routine. It estimates both the orbital period and the full set of orbital parameters for a binary system with high resolution.*

### Performance & Precision
Syntriod's parameter precision was tested using tens of thousands of synthetic datasets, each consisting of only 6 and 10 random observation points.

<img width="1329" height="1346" alt="image" src="https://github.com/user-attachments/assets/cb6f9a1b-fa96-4245-9ff0-fd875dbd29da" />

---
**For further details, refer to Syntriod's article.**
