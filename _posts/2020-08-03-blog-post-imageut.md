---
title: 'A collection of binary image editing programs'
date: 2020-08-04
permalink: /posts/2020/08/imageut/
tags:
  - C++
  - InSAR
---

This is a collection of binary image editing programs, including cutting, oversamppling, scaling, etc. Written with C++.  

Latest version
======
2020-08-03:  
[cut_image_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EfSBg52wfItJv5SvJcGmL6IB1enSLMz4bdVWyDMvTvkw-Q?e=BzygbX)   
[oversample_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EZ3J7hFYndlBlN7laF67f-gBbKGnJSsk9nEXktXuYI72CQ?e=rudMnn)  
[binary_scale_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EQ850CPiPNlBoWwQYHbL3CsB08FoYj14zgVMqlTOQ3Ge1Q?e=ZiIOhE)  
[binary_wrap_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EXCHyScXaWRAmalZlKUCWPQBRCgD3c3yA-j1-8AuEgIg3Q?e=U4efBm)  

Usages
======
run without arguments to see usages.  
A header.rsc file is needed for most of these programs which is a text file.  
It should contain at least the following information: 
 
WIDTH   14400  
FILE_LENGTH   10800  
X_FIRST           18.0000000  
Y_FIRST           43.0000000  
X_STEP             0.000277770000000  
Y_STEP            -0.000277770000000  
  
the width of the binary image  
the length(FILE_LENGTH) of the binary image  
the longitude of the up-left corner pixel of the binary image, in degree (X_FIRST)  
the latitude of the up-left corner pixel of the binary image, in degree (Y_FIRST)  
the pixel spacing along longitude, in degree (X_STEP)  
the pixel spacing along latitude, in degree (Y_STEP)  



Update logs
======
2020-08-03: published  
