---
layout:     post
title:      A Study of the Ooyama’s Moist Convection Model
date:       2012-06-29
summary:    A Study of Time Integration Techniques in Ooyama’s Moist Convection Model
categories: project
thumbnail:  server
tags:
 - science
 - geodesy
 - oceanography
---

The study focuses on exploring the performance of the two spectral methods that are used in the least assumption moist convection model in the atmosphere.
The least assumption moist atmospheric model has the advantage of predicting the thermodynamic variables which other models lack [Ooyama 1990].
Most models use potential temperature or other thermodynamic variables defined for meteorology use.
By predicting the entropy in the model, Ooyama's convection model proposes an unique and much accurate way to represent the thermodynamic state in the convection systems.
Another noteworthy advantage of the model is the combining of hydrostatic and non-hydrostatic simulation.

This study uses Fourier-Chebyshev method and double-Chebyshev method to compares the simulation's stability and efficiency under two classic scenarios.
One scenario is the acoustic wave propagation.
The other scenario is dry air bubble rising with different background environments.  
Both scenarios is using the same filter to deal with the energy accumulation in the model domain.
A sensitivity test of different filters on the simulated result with the double-Chebyshev method is also performed.

While filter can certainly solve the cumulative energy, eddy diffusion term is another physical way to stabilize the simulated result.    
A comparison between applying filter and eddy diffusion under Fourier-Chebyshev method shows the different simulated results.
Crank-Nickolson and Adam-Bashforth method is used in the study to add the eddy diffusion term in the model.
To increase the efficiency of our model, we also propose to use the non-divengent wind in the model.
There are total four different background scenarios applied in the model to show the evolution of rising dry air bubble.

The figure below is showing the entropy evolution of rising dry air bubble under one of the background scenarios with an inversion layer on top of the rising bubble.  
![airbubble](https://chiaweh2.github.io/figures/dry_air.png)
