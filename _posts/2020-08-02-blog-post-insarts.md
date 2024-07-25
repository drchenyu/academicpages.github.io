---
title: 'InSAR SBAS Time Series Tool'
date: 2021-01-06
permalink: /posts/2021/01/post1/
tags:
  - C++
  - 
---

The program is written in C++ enabling multiprocessing through OPENMP. The time series inversion is calculated by a general Gauss-Markov linear model (e.g., weighted least square) and then filtered in the frequency domain by FFTW. The estimation is run on a pixel-by-pixel basis and each pixel can be estimated in parallel, therefore it is expected to run fast when OPENMP is enabled.  

Latest version
====== 
2024-07-25: [Linux binary_release_download](http://www.gacos.net/pub/share/software/insarts_20240725.zip)

Capabilities
======
- Orbital ramp removel (interferogram by interferotram). 

- Elevation dependent signal removal (interferogram by interferotram). 

- Looking for a reference point. 

- Unwrapping error check by phase closures. 

- Displacement time series inversion, with or without a linear/logarithmic temporal model. 

- Mean linear velocity estimation by stacking.  

- Spatial and/or temporal filtering. 

Usages
======
- Tips to run 
  - To run the program, simply type:  

    >./insarts cfg 

    - The unit of the output is the same as the input. 

  - The interferograms should be stored in a ‘little-endian’ float (4 byte) binary file with the row major order. The filename of interferograms should contain at least two dates (first and second date) and in the format of ‘*YYYYMMDD*YYYYMMDD*’ (separate the two dates with any character(s)). All the input interferograms should be in the same size.

  - There are several swithers in the configuration file (highlighted below in green) with which you can turn on/off the correspondent section. 

  - In order to find satisfied filter strength (which is sometimes tricky), you can turn off if_remove_orbit, if_remove_eds, if_check_loop_closure and if_inverse_time_series, and then run the program several times with different filtering parameters (the program will load the original time series output of the time series inversion and overwrite any existing filtered results). 

- The outputs

  - Cumulative displacement maps in the same size as the input interferograms. It is named as ‘culmap-date1-date2.disp’ which is the cumulative displacement from date2 to date1.

  - ‘linear_mean_velocity’ which is the mean annual displacement (cumulative displacement divided by the time interval).

  - ‘least_square_sigma’ which is the mean square root of observation residuals.

  - ‘linear_stacking_mean_velocity’, ‘linear_stacking_mean_velocity_residual’ and ‘linear_stacking_mean_velocity_sigma’ when ‘if_stackinbg’ is turned on. These files correspond to the equations in Section 4.3. 

  - Filtered cumulative displacement maps named as ‘culmap-date1-date2.disp.filtered’. 

  - A phase loop closure mask when ‘if_check_loop_closure’ is turned on. It is in the same size as the input interferograms. (0.0 -> no mask, 1.0-> masked). A phase_closure_std map and a phase_closure_failed_ratio map. 

  - filelist_used, filelist_deleted and filelist_statistics, if some ifgs were deleted during the processing.

  - baseline_dependent_dem_error map when ‘if_est_hgt’ is turned on. 


Parameters explained
======
A user manual is included in the zip file. 

Update logs
======
2021-01-28: LAPACK removed as it goes to endless loop occasionally on some machine. 

2021-01-28: New reference point select method implemented, the default method now =2.

2021-01-06: New version released with a detailed user manual. 

2020-10-18: add elevation dependent signal removal 
 
2020-08-06: read reference points from a windowed area. 

2020-08-02: add logarithmic temporal constraint (a+b*log(t-t0))  
  
2020-07-01: published  
