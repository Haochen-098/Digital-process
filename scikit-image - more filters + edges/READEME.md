Part I : Edges (25%)

Read the gray scale image ex2.jpg. Display the image. Compute gradient of the image (both the horizontal derivative and vertical derivative) by Sobel operators. You can find more details about the Sobel filter in here and here. To compute the derivatives, you can use the functions skimage.filters.sobel_v and skimage.filters.sobel_h. Display the horizontal and vertical direction derivative images. Compute gradient magnitude image by suitably combining the horizontal and the vertical derivative images. Display the gradient magnitude image.



Part II: Canny edge detector (25%)

Read the gray scale image ex2.jpg and display it. Since the fist step in Canny edge detection is Gaussian filtering, to understand the effect of Gaussian filtering, apply Gaussian filtering on the image and show the smoothed image.

Then, study the code provided here for Canny edge detection. Now do the followings:

1. To understand the effect of threshold values, fix sigma = 1.0, use matplotlib.pyplot.subplot to plot the following 4 figures together and see their difference : low threshold = 25; low threshold = 50; high threshold = 150; high threshold = 200.

2. To understand the effect of sigma value, fix low_threshold=50 and high_threshold=150, use matplotlib.pyplot.subplot to plot the following 4 figures together and see their difference : sigma =  1.0; sigma = 1.5; sigma = 2.0; sigma = 2.5.

Observe the figures that you obtained in the two parts above. Explain why threshold/sigma will influence the result in that way? You can provide your answer in a text cell in your notebook.



Part III : Localized blurring (50%)

Read these slides about localized blurring.

Afterwards, write a Python program that does the following:

1. Open gray scale image ex1.jpg.

2. Input a pixel and a sigma value by yourself, for example : x=100,y=100,sigma=50.

3. Blur a localized area around the pixel which you have chosen using Gaussian kernel, show the localized blurred image.

4. Blur a localized area around the pixel which you have chosen using Cauchy kernel, show the localized blurred image.

You can achieve a localized blurring by simple tricks, such as, first bluring the entire image, then adding the blurred and the original image pixel-by-pixel by a suitable weighted combination.

