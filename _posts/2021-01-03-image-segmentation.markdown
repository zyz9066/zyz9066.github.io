---
layout: post
title:  "Image Denoising & Segmentation (TBD)"
date:   2021-01-03 11:11:03 -0400
categories: computer vision
---
## Goals
Implement a few simple denoising and segmentation algorithms.

## Denoising
Estimate SNR in the image, and report these values.

```python
from skimage import io
import matplotlib.pyplot as plt

flair = io.imread('flair.png')

plt.imshow(flair, cmap='gray')
plt.show()
```

![](https://zyz9066.github.io/images/516/4/raw.png)

```python
import numpy as np

def SNR(a):
    a = np.asanyarray(a)
    m = a.mean()
    sd = a.std()
    return np.where(sd == 0, 0, m/sd)

print(SNR(flair))
```

```sh
1.1576335871837644
```

Implement denoising techniques, apply them to the image. Show the noisy, denoised, and noisy minus denoised (method noise) image for the algorithm.

### Bilateral filtering (TBD)
```python
def bilateralFilter(image, sigmaS=int(20/2.87), sigmaR=23, sampleS=None, sampleR=None):

    def fftconvolve3D(image, kernel):
        def rfft(array, shape):
            fft = np.fft.rfftn(array, s=shape)
            return fft

        def irfft(array):
            ifft = np.fft.irfftn(array)
            return ifft

        def conv3D(array, kernel, shape):
            conv = irfft(rfft(array, shape)*rfft(kernel, shape))
            return conv

        # fft method
        shape = np.array(image.shape) + np.array(kernel.shape) - 1
        cfft = conv3D(image, kernel, shape)
        row, col, dep = np.array(kernel.shape) // 2

        return cfft[row:-row, col:-col, dep:-dep]

    def interp3D(input_array, indices):
        '''Evaluate the input_array data at the indices given'''

        output = np.empty(indices[0].shape)
        x_indices, y_indices, z_indices = indices[0], indices[1], indices[2]

        x0 = x_indices.astype(np.int32)
        y0 = y_indices.astype(np.int32)
        z0 = z_indices.astype(np.int32)
        x1, y1, z1 = x0 + 1, y0 + 1, z0 + 1

        #Check if xyz1 is beyond array boundary:
        x1[x1==input_array.shape[0]] = x0.max()
        y1[y1==input_array.shape[1]] = y0.max()
        z1[z1==input_array.shape[2]] = z0.max()

        x, y, z = x_indices - x0, y_indices - y0, z_indices - z0
        output = (input_array[x0,y0,z0]*(1-x)*(1-y)*(1-z) +
                     input_array[x1,y0,z0]*x*(1-y)*(1-z) +
                     input_array[x0,y1,z0]*(1-x)*y*(1-z) +
                     input_array[x0,y0,z1]*(1-x)*(1-y)*z +
                     input_array[x1,y0,z1]*x*(1-y)*z +
                     input_array[x0,y1,z1]*(1-x)*y*z +
                     input_array[x1,y1,z0]*x*y*(1-z) +
                     input_array[x1,y1,z1]*x*y*z)

        return output

    height = image.shape[0]
    width = image.shape[1]

    sampleS = int(sigmaS/2.32) if sampleS is None else sampleS
    sampleR = int(sigmaR/2.32) if sampleR is None else sampleR

    imageFlat = image.flatten()

    edgeMin = np.amin(imageFlat)
    edgeMax = np.amax(imageFlat)
    edgeDelta = edgeMax - edgeMin

    derivedS = sigmaS / sampleS
    derivedR = sigmaR / sampleR

    paddingXY = np.round(2 * derivedS + 1)
    paddingZ = np.round(2 * derivedR + 1)

    # allocate 3D grid
    sampleWidth = int(np.round((width - 1) / sampleS) + 1 + 2 * paddingXY)
    sampleHeight = int(np.round((height - 1) / sampleS) + 1 + 2 * paddingXY)
    sampleDepth = int(np.round(edgeDelta / sampleR) + 1 + 2 * paddingZ)

    dataFlat = np.zeros(sampleHeight * sampleWidth * sampleDepth)

    # compute downsampled indices
    (yy, xx) = np.meshgrid(range(width), range(height))

    dimX = np.around(xx / sampleS) + paddingXY
    dimY = np.around(yy / sampleS) + paddingXY
    dimZ = np.around((image - edgeMin) / sampleR) + paddingZ

    # perform scatter
    flatX = dimX.flatten()
    flatY = dimY.flatten()
    flatZ = dimZ.flatten()

    dim = flatZ + flatY * sampleDepth + flatX * sampleWidth * sampleDepth
    dim = np.array(dim, dtype=int)

    dataFlat[dim] = imageFlat

    data = dataFlat.reshape(sampleHeight, sampleWidth, sampleDepth)
    weights = np.array(data, dtype=bool)

    # make gaussian kernel
    kernelDim = derivedS * 2 + 1
    kernelDep = 2 * derivedR * 2 + 1

    halfKernelDim = np.round(kernelDim / 2)
    halfKernelDep = np.round(kernelDep / 2)

    (gridX, gridY, gridZ) = np.meshgrid(range(int(kernelDim)),
                                        range(int(kernelDim)),
                                        range(int(kernelDep)))
    gridX -= int(halfKernelDim)
    gridY -= int(halfKernelDim)
    gridZ -= int(halfKernelDep)

    gridSqr = (gridX**2 + gridY**2) / derivedS**2 + gridZ**2 / derivedR**2
    kernel = np.exp(-0.5 * gridSqr)

    # convolve
    blurData = fftconvolve3D(data, kernel)
    blurWeights = fftconvolve3D(weights, kernel)

    # avoid divide by 0
    blurWeights[blurWeights == 0] = -2
    # divide
    normalBlurData = blurData / blurWeights
    # put 0s where it's undefined
    normalBlurData[blurWeights < -1] = 0

    # upsample without rounding
    dX = xx / sampleS + paddingXY
    dY = yy / sampleS + paddingXY
    dZ = (image - edgeMin) / sampleR + paddingZ

    return interp3D(normalBlurData, (dX, dY, dZ))
```

```python
plt.imshow(flair_filt, cmap='gray')
plt.show()
```

![](https://zyz9066.github.io/images/516/4/bilateral.png)

```python
plt.imshow(flair-flair_filt, cmap='gray')
plt.show()
```

![](https://zyz9066.github.io/images/516/4/bilateralm.png)

### Non-local means (TBD)

### Denoising autoencoder (TBD)
