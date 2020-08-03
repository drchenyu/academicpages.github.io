---
title: 'Generic Atmospheric Correction Online Service for InSAR (GACOS)'
date: 2017-06-15
permalink: /posts/2017/06/gacos/
---

Access
=====
Access via link [GACOS](http://ceg-research.ncl.ac.uk/v2/gacos/)

Description
======
Welcome to our Generic Atmospheric Correction Online Service for InSAR (GACOS).

GACOS utilises the Iterative Tropospheric Decomposition (ITD) model (Yu et al., 2017) to separate stratified and turbulent signals from tropospheric total delays, and generate high spatial resolution zenith total delay maps to be used for correcting InSAR measurements and other applications. GACOS has the following key features: (i) globally available; (ii) operational in a near real time mode; (iii) easy to implement; and (iv) users to be informed how the model performs and whether the correction is recommended.

Datasets used in GACOS include:
High Resolution ECMWF weather model at 0.125-degree and 6-hour resolutions;
SRTM DEM (90 m, S60-N60);
ASTER GDEM (90 m, N60-N83, S60-S83);
GACOS tropospheric delay maps are given in a grid binary format (4-byte float little endian, name convention YYYYMMDD.ztd). A ReadMe file is provided to demonstrate how to use GACOS tropospheric correction maps. An example MATLAB code is provided to help apply GACOS correction maps and view results instantly.

It is planned soon to also provide tropospheric delay maps from the integration of the ECMWF weather model and GPS-estimated tropospheric delay products from the Nevada Geodetic Laboratory.

Whenever using the GACOS products, please cite the following references:
Yu, C., Li, Z., Penna, N. T., & Crippa, P. (2018). Generic atmospheric correction model for Interferometric Synthetic Aperture Radar observations. Journal of Geophysical Research: Solid Earth, 123. https://doi.org/10.1029/2017JB015305. [link]
Yu, C., Li, Z., and Penna, N. T. (2018), Interferometric synthetic aperture radar atmospheric correction using a GPS-based iterative tropospheric decomposition model, Re­mote Sens. En­v­i­ron., doi:10.​1016/​j.​rse.​2017.​10.​038. [link]
Yu, C., Penna, N. T., and Li, Z. (2017), Generation of real-time mode high-resolution water vapor fields from GPS observations, J. Geophys. Res. Atmos., 122, 2008–2025, doi:10.1002/2016JD025753. [Link]

Acknowledgements:
GACOS is supported by the UK NERC through the Centre for the Observation and Modelling of Earthquakes, Volcanoes and Tectonics (COMET, ref.: come30001) and the LICS project (ref. NE/K010794/1), and the ESA-MOST DRAGON-4 project (ref. 32244). We acknowledge European Centre for Medium-Range Weather Forecasts (ECMWF) for their operational high resolution tropospheric products. We also acknowledge Professor Geoffrey Blewitt and his team at Nevada Geodetic Laboratory, University of Nevada, Reno for sharing their GPS tropospheric delay products.




Update logs
======
2020-08-02: add logarithmic temporal constraint (a+b*log(t-t0))  
  
2020-07-01: published  
