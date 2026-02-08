# Syntriod
\
**Orbital solution of binary stars using synthetic template radial velocity curves.**

The radial velocity solution is the process of determining orbital parameters of binary star systems from their observed radial velocities, via a theoretical Kepler orbit."By phasing the observed velocities with the correct 
orbital parameters, the system parameters can be determined precisely.

![ezgif-6-611aad09f5](https://github.com/user-attachments/assets/a995418a-17a2-407d-a009-2b01a7e7c778)

The orbital parameters in question are the orbital period ($P$), time of periastron passage ($T_0$), eccentricity ($e$), argument of periastron ($\omega$), velocity semi-amplitudes 
of the components ($K_{1,2}$), and the systemic velocity ($\gamma$). In the literature, these parameters are typically determined using MCMC-based radial 
velocity fitting codes. Among these parameters, the period ($P$) is the most critical for the radial velocity solution of a binary system and requires 
prior information before the fitting process. Therefore, standard software in the literature often 
initializes the radial velocity fit using an initial period estimate derived from classical periodograms like Lomb Scargle.

These periodograms are often susceptible to harmonics and aliasing, and they struggle to determine the correct period in cases 
of sparse sampling. Furthermore, they provide no information regarding the other system parameters. **Syntriod** determines the full set of orbital parameters for a binary system by 
matching observational data to pre-generated synthetic radial velocity templates, without employing any optimization routines. This process takes only ~5 seconds and achieves high 
parameter precision.

This is accomplished through a suite of specialized mathematical algorithms, including alias and harmonic control mechanisms, frequency analysis in both the time and phase domains, 
and an extensive template library. Consequently, Syntriod can deliver the full set of parameters with high precision, even for systems with as few as 5 data points.

<img width="1581" height="305" alt="image" src="https://github.com/user-attachments/assets/9d5baf00-f0d1-4f47-96ad-b5525fa4ec8f" />

*Syntriod is neither a standard periodogram nor a traditional radial velocity fitting code; rather, it is a parameter estimation routine. 
It estimates both the orbital period and the full set of orbital parameters for a binary system with high resolution.* 

Syntriod's parameter precision was tested using thousands of synthetic datasets, each consisting of only 5 random observation points.

<img width="1809" height="1809" alt="image" src="https://github.com/user-attachments/assets/1d54d7d4-de10-434c-9089-abfa53d16a58" />


