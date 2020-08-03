---
title: 'InSAR SBAS Time Series Tool'
date: 2020-08-02
permalink: /posts/2020/08/post1/
---

This is a InSAR time series analysis tool based on SBAS, including phase closure check (unwrapping error), orbit rampo removal, DEM error estimation and temproal constraint. 

Latest version
======
2020-08-02: [Linux binary_release](https://newcastle-my.sharepoint.com/:u:/g/personal/nyc40_newcastle_ac_uk/EX_Ee085wh1OhcuI-OgxND4BPe5m6autzpK25-ThtWE2eA?e=2fUwGZ)


Usages
======
On Linux, simply run:
./insarts cfg
On windows, run it in cmd:
./insarts cfg 


Update logs
======
2020-08-02: add logarithmic temporal constraint (a+b*log(t-t0))  
  
2020-07-01: published  
