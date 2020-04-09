Part I (20%): Write a program to accomplish the following:

Read the grayscale image called test.jpg
Write your own code to compute a 256-bin gray scale histogram of the image. You cannot use built in histogram functions from any library (e.g. numpy.histogram, scipy.stats.histogram, skimage.exposure.histogram, opencv.calcHist, etc) for this.
Plot the histogram.
Also, call Skimage histogram function to compute a 256-bin histogram for the same image. Plot Skimage histogram side by side with yours to show that they are same/similar.
Part II (30%): Histogram equalization:

Write your own program to perform histogram equalization on the same test.jpg image used in the last part. You need to plot the original image, its histogram, the image after histogram equalization and its histogram. You are not allowed to use the Skimage functions, i.e.,exposure.histogram,exposure.equalize_hist for this part.

Tutorials on histogram equalization:

https://www.youtube.com/watch?v=GWCB3pKi2ko

https://www.tutorialspoint.com/dip/histogram_equalization.htm

https://en.wikipedia.org/wiki/Histogram_equalization

Part III (20%): Histogram comparing:

Write your own program to compare histograms of two images day.jpg and night.jpg. You will need to read both images, convert them to grayscale, compute their histograms and print the Bhattacharyya Coefficient of the two histograms. You can use Skimage histogram function to compute the histograms.
