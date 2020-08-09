---
title: 'Time convention program (GPST, JD, J2000, DOY)'
date: 2017-04-01
permalink: /posts/2017/04/caltime/
tags:
  - C++
---

Time convertion ultility, convert input time system to all kinds of times. Valid between 1 March 1900 and 28 February 2100.

Latest version
======
2017-04-01: [Linux_binary_release_download](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/Edui1ZDqezVKhRfPh1b2rCIBc4XF9BE0BI8uQfWTMNi1Ew?e=bBVzpR)


Usages
======
  [] means optional arguments, *.f means float input/output 

  From calender date        -> caltime date  year month day [hour] [minute] [second.f]  
  From calender day of year -> caltime doy   year doy [second_of_day.f]  
  From J2000 seconds        -> caltime j2000 j2000_second.f  
  From Modified Julian Date -> caltime mjd   mjd_day.f  
  From GPS week             -> caltime week  week_num day_of_week [second_of_day.f]  
  Help info                 -> caltime -help  
  
Formated Output, same for all usages  
  
  Year month day hour minute second.f doy secondofday.f wwww dow mjd.f J200sec.f  

Examples usages:  
  
  From month day to doy  -> "caltime date 2012 12 20 | awk '{print $7}'  "
  From doy to gps week   -> "caltime date 2012 231   | awk '{print $9,$10}'  "
  Read input from stdin  -> "awk '{print $1,$2,$3}' filename | caltime date  "
  Read input from stdin  -> "cat filename | caltime j2000 | awk '{print $12}' " 
  
Reference:  
  
1.GNSS – Global Navigation Satellite Systems, Hofmann-Wellenhof, Bernhard, Lichtenegger, Herbert, Wasle, Elmar  


Update logs
======
2017-04-01: published  
