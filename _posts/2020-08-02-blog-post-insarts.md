---
title: 'InSAR SBAS Time Series Tool'
date: 2021-01-06
permalink: /posts/2021/01/post1/
tags:
  - C++
  - 
---

The program is written in C++ enabling multiprocessing through OPENMP. The time series inversion is calculated by a general Gauss-Markov linear model (e.g., weighted least square) by LAPACK and then filtered in the frequency domain by FFTW. The estimation is run on a pixel-by-pixel basis and each pixel can be estimated in parallel, therefore it is expected to run fast when OPENMP is enabled.  

Latest version
====== 
2021-01-06: [Linux binary_release_download](ftp://www.gacos.net/pub/share/software/insarts_20210106.zip)

Capabilities
======
1 Orbital ramp removel (interferogram by interferotram). 

2 Elevation dependent signal removal (interferogram by interferotram). 

3 Looking for a reference point. 

4 Unwrapping error check by phase closures. 

5 Displacement time series inversion, with or without a linear/logarithmic temporal model. 

6 Mean linear velocity estimation by stacking.  

7 Spatial and/or temporal filtering. 

Usages
======
1 Tips to run 
1.1 To run the program, simply type: 
./insarts cfg 
The unit of the output is the same as the input. 

1.2 The interferograms should be stored in a ‘little-endian’ float (4 byte) binary file with the row major order. The filename of interferograms should contain at least two dates (first and second date) and in the format of ‘*YYYYMMDD*YYYYMMDD*’ (separate the two dates with any character(s)). All the input interferograms should be in the same size.

1.3 There are several swithers in the configuration file (highlighted below in green) with which you can turn on/off the correspondent section. 

1.4 In order to find satisfied filter strength (which is sometimes tricky), you can turn off if_remove_orbit, if_remove_eds, if_check_loop_closure and if_inverse_time_series, and then run the program several times with different filtering parameters (the program will load the original time series output of the time series inversion and overwrite any existing filtered results). 

2 The outputs

2.1 Cumulative displacement maps in the same size as the input interferograms. It is named as ‘culmap-date1-date2.disp’ which is the cumulative displacement from date2 to date1.

2.2 ‘linear_mean_velocity’ which is the mean annual displacement (cumulative displacement divided by the time interval).

2.3 ‘least_square_sigma’ which is the mean square root of observation residuals.

2.4 ‘linear_stacking_mean_velocity’, ‘linear_stacking_mean_velocity_residual’ and ‘linear_stacking_mean_velocity_sigma’ when ‘if_stackinbg’ is turned on. These files correspond to the equations in Section 4.3. 

2.5 Filtered cumulative displacement maps named as ‘culmap-date1-date2.disp.filtered’. 

2.6 A phase loop closure mask when ‘if_check_loop_closure’ is turned on. It is in the same size as the input interferograms. (0.0 -> no mask, 1.0-> masked). A phase_closure_std map and a phase_closure_failed_ratio map. 

2.7 filelist_used, filelist_deleted and filelist_statistics, if some ifgs were deleted during the processing.

2.8 baseline_dependent_dem_error map when ‘if_est_hgt’ is turned on. 


Parameters explained
======
A user manual is included in the zip file. 

Update logs
======
2021-01-06: New version released with a detailed user manual. 

2020-10-18: add elevation dependent signal removal 
 
2020-08-06: read reference points from a windowed area. 

2020-08-02: add logarithmic temporal constraint (a+b*log(t-t0))  
  
2020-07-01: published  
