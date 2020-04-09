1. Create a Laplacian-of-Gaussian Volume (25%)

Read this image and convert it to gray scale.
Apply Gaussian filtering using  skimage.filters.gaussian with a suitably chosen sigma.
The output should look like this.
Tip: To show the images use colormap 'jet' (plt.imshow(img,cmap='jet'))
Create a 3 level Laplacian-of-Gaussian (LoG) volume by applying this filter at 3 different scales (sigma values) to the blurred image obtained in step 2.
The LoG filter can be applied using either skimage.filters.gaussian followed by skimage.filters.laplace or using 
scipy.signal.convolve2d with a manually created kernel following the expression given here.

The kernel size k should be computed as .
The 3 sigma values should be chosen to give the best results; using consecutive integers such as 3, 4 and 5 might be a good starting point.
All 3 levels of the volume must be stored in a single  Numpy array where h and w are the height and width of the input image.
The output should look like this.

2. Obtain a rough estimate of blob locations (30%)

1. Detect regional minima within the LoG volume.
As described here, regional minima are defined as "connected components of pixels with a constant intensity value, and whose external boundary pixels all have a higher value".
To perform this so you can either use the scipy functionscipy.ndimage.filters.minimum_filter or implement it yourself, for instance, by adapting the code given here. 
The output of this step will be a binary image of the same size as the LoG volume that contains 1 at locations of the regional minima and 0 everywhere else.
The detected minima depend heavily on the parameters used for defining the region size. For instance, if  the scipy function is used, then its second argument "size" must be chosen carefully.
It should also be noted that the scipy function returns the actual values of the detected minima rather than their locations so additional steps will be needed to convert its output to the required binary image.
2. Collapse this 3D binary image into a single channel image by computing the sum of corresponding pixels in the 3 channels. This can be done using np.sum.
3. Show the locations of all non zero entries in this collapsed array overlaid on the input image as red points.
The locations of non zero entries can be found using np.nonzero while the plotting can be done using plt.scatter.
The output should look like this.

3. Refine the blobs using Otsu thresholding(25%)

1. Apply Otsu thresholding on the blurred image computed in step 2 of part 1 using skimage.filters.threshold_otsu to obtain the optimal threshold for this image (
Before applying otsu thresholding, convert the blurred image to 8-bit unsigned integer format using skimage.img_as_ubyte.
A tutorial on Otsu thresholding can be found here.
2. Remove all minima in the output image of part 2 where pixel values are less than the obtained threshold
3. Show the remaining minima locations overlaid on the input image as red points
The output should look like this.
