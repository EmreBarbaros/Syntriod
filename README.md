<div align="center">

# Syntriod

**Orbital solution of binary stars using synthetic template radial velocity curves.**

<img width="720" height="540" alt="synt" src="https://github.com/user-attachments/assets/130cf8cf-4d36-485d-8a8b-5c38731828cd" />

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

**Period Retrieval Accuracy: Syntriod vs. Lomb-Scargle**

To evaluate period detection capability under sparse sampling conditions, Syntriod was benchmarked against the classical Lomb-Scargle periodogram using **10,000 synthetic datasets** across varying numbers of observations ($N_{obs}$). 

As illustrated below, Syntriod significantly outperforms Lomb-Scargle in both **Satisfactory Precision (SP)** (solid lines, representing accuracy within a 10% error margin) and **Perfect Precision (PP)** (dashed lines, representing accuracy within a 1% error margin), maintaining exceptional reliability even with extremely limited data points ($N_{obs} \le 6$).

<div align="center">
<img width="695" height="551" alt="image" src="https://github.com/user-attachments/assets/41e3aabf-5414-44fc-80d4-06c9918ba75e" />
</div>

**Full Orbital Parameter Precision**

Beyond period determination, Syntriod's precision across the entire orbital parameter space was rigorously evaluated using tens of thousands of synthetic datasets consisting of only 6 and 10 random observation points.

<img width="1329" height="1346" alt="image" src="https://github.com/user-attachments/assets/cb6f9a1b-fa96-4245-9ff0-fd875dbd29da" />

---
**The source code is currently being organized for release and will be available here within a few days.**

**For further details, refer to the [Syntriod's article](https://iopscience.iop.org/article/10.1088/1538-3873/ae8575).**

Contact & Inquiries: **[ebarbaros054@gmail.com]**
