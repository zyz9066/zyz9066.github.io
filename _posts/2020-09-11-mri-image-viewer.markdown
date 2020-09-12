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
Create a [`viewer`](https://github.com/zyz9066/Image-Analysis/blob/48d6d0cdce670ab350e02d3567d50826a870dcab/Python%20viewer%20and%20MRI%20modalites%20FFT/CS516A1.py#L356) function in *Python* that displays a slice from a 3D image and allows for scrolling through the images slices using keypad or mouse wheel. A call to `viewer(t1_data, index=250, view='coronal')` produce the following image:

![](https://zyz9066.github.io/images/516/1/coronal250.png)

`t1_data` is a 3D *numpy* array with the z-slices in the $$3^\text{rd}$$ dimension (most images are structured this way). We can rotate the mouse wheel, or press the 'up' or 'down' arrow keys, the image will change to a different slice. Here uses of the *Matplotlib*.

Add histogram equalization option `histeq`, call `viewer(t1_data, index=250, view='coronal', histeq=True)` will produce a histogram-equalized image in the viewer, instead of the raw image.

![](https://zyz9066.github.io/images/516/1/coronal250eq.png)

Add an option to display all viewers simultaneously in the same plot using sub-plots. When place the mouse over one of the subplots and rotate the mouse wheel, only the selected subplot slice will change. `viewer(t1_data, index=250, view='all')`:

![](https://zyz9066.github.io/images/516/1/subplots.png)

We can also see the need for histogram equalization in sagittal/coronal view (blood vessels are too bright relative to the rest of the tissue). Also add different colormaps and intensity limits options, `viewer(t1_data, index=250, view='axial', cmap='gray')`:

![](https://zyz9066.github.io/images/516/1/gray.png)

`viewer(t1_data, index=250, view='axial', cmap='jet')`

![](https://zyz9066.github.io/images/516/1/jet.png)

`viewer(t1_data, index=250, view='axial', cmap='hot')`

![](https://zyz9066.github.io/images/516/1/hot.png)

`viewer(t1_data, index=250, view='axial', vmin=20, vmax=60)`

![](https://zyz9066.github.io/images/516/1/limits.png)

`viewer(t1_data, index=250, view='axial', aspect='auto')`

![](https://zyz9066.github.io/images/516/1/auto.png)
