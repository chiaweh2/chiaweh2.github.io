---
layout:     post
title:      Spatial scaling the GRACE satellite data
date:       2018-08-24
summary:    Explain the processing steps of GRACE
categories: post
thumbnail:  satellite
tags:
 - science
 - geodesy
 - oceanography
---

The GRACE satellite data has been used for more than a decade to investigate the global-scale mass redistribution since April 2002.
With the Follow-on mission which had recently (5/22/2018) been launched, the extended measurement is truly an important achievement in the field of Earth geodesy, hydrology, and cryosphere.
To make use of this incredible dataset, there are three processing centers that offer all different kinds of GRACE solution.
Each processing center generates the solution based on the range differences observed by the unique twin satellite setting.
This also provide an opportunity for inter-comparison on the processing steps between solutions.

Due to the many processing steps needed, the detected signal in the the GRACE data is smoothed out. Meaning the maximum signal would distributed over a larger area despite the original signal is over a much smaller area. To give you a sense of how a regular GRACE data after many processing applied would look like, the following figure shows this what we called **unscaled** data over the Greenland region. 
![unscale](https://chiaweh2.github.io/figures/regress_gisnoscale.png)

To overcome this smoothing problem in the GRACE data, I use the method describe in my published paper[[Hsu and Velicogna, 2017]](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1002/2017GL074070) to show how big a difference it can be if one did not restore the signal properly. The following figure shows the **scaled** GRACE data over the same area.
![scale](https://chiaweh2.github.ios/figures/regress_gisscale.png)

Notice the large changes in maximum value which makes the color saturated and also the shift of maximum value to a much reasonable region where has the mass loss due to ice melting. 

---

The concept of restoring the lossing signal is to get the spatial information from a synthetic dataset. First we applied the necessary processing steps on the synthetic dataset than we calculate the uni-variate linear regression between the "processed synthetic" and the "original synthetic data" to figure out the necessary scaling from the regression coefficients[[Landerer and Swenson, 2008]](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2011WR011453). This method generates a reasonable hydrological signal. However, the signal variation at different time scales can be dominated by seperate physical processes. A single scaling number in the previous method may only represent the physical processes that dominated the total signal. To improve the estimate in all time scale, we seperated the signal to long-term variation and seasonal variation which we knew the dominated physical processes are different and perform multi-variate linear regression. The multi-variate linear regression provides us seperate scaling factors for each time scale. By also seperate the GRACE data to long-term variation and seasonal variationto, we scale the GRACE signal at each time scale with its corresponding scaling factor.  
