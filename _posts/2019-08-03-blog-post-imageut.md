---
title: 'A collection of binary image editing programs'
date: 2019-08-03
permalink: /posts/2020/08/imageut/
tags:
  - C++
  - InSAR
---

This is a collection of binary image editing programs, including cutting, oversamppling, scaling, etc. Written with C++.  

Latest version
======
2020-08-03:  
[cut_image_download](http://www.gacos.net/pub/share/software/cut_image.zip)   
[oversample_download](http://www.gacos.net/pub/share/software/oversample.zip)  
[binary_scale_download](http://www.gacos.net/pub/share/software/binary_scale.zip)  
[binary_wrap_download](http://www.gacos.net/pub/share/software/binary_wrap.zip)  
[binary_minus_download](http://www.gacos.net/pub/share/software/binary_minus.zip)  
[int2float_download](http://www.gacos.net/pub/share/software/int2float.zip)  

Usages
======
cut_image -> crop images by (minlat, maxlat, minlon, maxlon)   
oversample -> over- or downsample images by redefining the pixel spacing   
binary_scale -> scale images by multiplying a scale factor   
binary_wrap -> wrap images between a predefined threshold (-threshold, threshold)   
binary_minus -> minus two images   
int2float -> convert image with integer values to float values   


Run without arguments to see usages.  
A header.rsc file is needed for most of these programs which is a text file.  
It should contain at least the following information: 

#################
WIDTH   14400  
FILE_LENGTH   10800  
X_FIRST           18.0000000  
Y_FIRST           43.0000000  
X_STEP             0.000277770000000  
Y_STEP            -0.000277770000000     
#################


the width of the binary image  
the length(FILE_LENGTH) of the binary image  
the longitude of the up-left corner pixel of the binary image, in degree (X_FIRST)  
the latitude of the up-left corner pixel of the binary image, in degree (Y_FIRST)  
the pixel spacing along longitude, in degree (X_STEP)  
the pixel spacing along latitude, in degree (Y_STEP)  



Update logs
======
2020-08-03: published  
