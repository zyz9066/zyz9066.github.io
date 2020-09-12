---
layout: post
title:  "MRI Image Viewer"
date:   2020-09-11 11:11:03 -0400
categories: medical imaging
---
All these images were taken from [*OpenNeuro*](https://openneuro.org). Use the [*nibabel*](https://nipy.org/nibabel/) libraries to load images from disk. Here we use *Python* and *Numpy* libraries. There 5 separate modalities of 3D MRI images as follows:
1. T1-weighted (t1.nii)
2. T2-weighted (t2.nii)
3. Susceptibility-weighted (swi.nii)
4. Time of flight angiogram (tof.nii)
5. Blood oxygen level dependent (bold.nii)

*.nii* is a medical imaging format (*nifti* format).

## Python viewer
Create a [`viewer`](https://github.com/zyz9066/Image-Analysis/blob/48d6d0cdce670ab350e02d3567d50826a870dcab/Python%20viewer%20and%20MRI%20modalites%20FFT/CS516A1.py#L356)
