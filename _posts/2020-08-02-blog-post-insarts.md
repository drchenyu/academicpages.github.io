---
title: 'InSAR SBAS Time Series Tool'
date: 2020-08-02
permalink: /posts/2020/08/post1/
tags:
  - C++
  - 
---

This is a InSAR time series analysis tool based on SBAS, including phase closure check (unwrapping error), orbital ramp removal, DEM error estimation and temproal constraint.  
Written with C++. 

Latest version
======
2020-08-06: [Linux binary_release_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EZfON_nQhfBJpE8GgL46BdsBWysxhcbDZukgczkBuooRoA?e=AQjv0A)


Usages
======
On Linux, simply run:  
./insarts cfg  

Parameters explained
======
1. set filename and foldername  
- resultfolder
  - !!must be created before running!! all results and intermedie files will be stored in this folder  
- headerfile
  - an rsc style header file, must contain "WIDTH,FILE_LENGTH,X_FIRST,Y_FIRST,X_STEP,Y_STEP"  
- filelist
  - a filelist file containing all the filenames of ifgs. !!do not contain pathname, only filenames are allowed!!  
- datafolder
  - path where ifgs are stored  
- baselines
  - a baseline text file define the baseline of each ifg. !!two column text file, first column: filename, second column baseline in meter!!  

2. set predefined parameters  
- ref_row
  - row number, set to 0 to select automatically   
- ref_col
  - col number, set to 0 to select automatically  
- ref_window
  - window size to extract reference point value  
- maxcap
  - maximumn capacity of memory (pixel size), over which the ifg will be divided;  
- wavelength
  - in meter  
- incidence
  - in degree  
- orbit_altitude
  - in meter  

3. set processing parameters  
- if_est_hgt
  - 0: no DEM error is estiamted; 1: to estimate the DEM error, a baseline file is needed then  
- temporal_constraint
  - 0: no constraint; 1: linear; 2: a+b*ln(T-T0);  
- temporal_strength
  - only valid when temporal_constraint=1  
- simple_log_origin
  - origin of simple_log_function T0 (mainshock date),only valid when temporal_constraint=2  
- if_remove_orbit
  - 0: no orbital ramp removal; 1: removel orbital ramp and write out new files  
- orbit_quad_fit_sampling
  - resampling factor when estimating orbit quadratic polynomial  
- if_check_loop_closure
  - 0: no loop closure; 1: check loop closure  
- loop_misclosure_threshod
  - threshod to define a failed loop closure  
- loop_misclosure_ratio_threshod
  - ratio of failed loops among all possible loops, over which there will be a mask  
- minimun_loop_num
  - only check loop closure when there are at least minimun_loop_num loops exist  
- if_allow_unlooped_pixel
  - 0:exlcude those pixels; 1: alow those pixels, unlooped means loop number < minimun_loop_num   
- minimum_temporal_ifg_ratio
  - temporal_ifg_ratio=(valid_ifg_number)/(total_ifg_number), less than which there will be a mask  

Update logs
======
2020-08-06: read reference points from a windowed area. 

2020-08-02: add logarithmic temporal constraint (a+b*log(t-t0))  
  
2020-07-01: published  
