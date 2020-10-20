---
title: 'InSAR robust stacking tool'
date: 2020-10-07
permalink: /posts/2020/10/post1/
tags:
  - C++
  - 
---

This is a InSAR time series analysis tool based on simple stacking with robust least squre (to delete outliers), including phase closure check (unwrapping error) and orbital ramp removal.  

Written with C++. 

Latest version
======
2020-10-16: [Linux binary_release_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EWlg4VhfESxNhU9tKnmjQCkBZYnVpFnxO9cvOjSsTx14WA?e=n0Bx94)


Usages
======
On Linux, simply run:  
./rstacking cfg  

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
- sigma_factor 
  - phase value out of range (median-std\*sigma_factor, median+std\*sigma_factor) will be deleted

3. set processing parameters  
- if_remove_orbit
  - 0: no orbital ramp removal; 1: removel orbital ramp and write out new files  
- orbit_quad_fit_sampling
  - resampling factor when estimating orbit quadratic polynomial 
- if_remove_hgt 
  - if remove elevation dependent signals, which is phase=a+b\*height
- hgt_block_size 
  - window size to estimate elevation dependent signals, in km
- demfile 
  - a dem file which must at least cover the whole ifg 
- demfile_header 
  - a header file for the demfile, the same as rsc above. 
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
2020-10-16： add elevation dependent signal removal.

2020-10-07: published  
