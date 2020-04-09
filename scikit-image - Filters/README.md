Part I (25%) Computing linear filters in scikit-image/python.

Read a grayscale image moon.png. 
Filter the grayscale image with the following filters.
Display results.
Create a 3-by-3 matrix and write your own code to implement these filters: (You cannot use any built in functions from any library for this.)
1) Laplacian Filter

2) [0,0,0]
    [0,1,0]
    [0,0,0]

3) [0,0,0]
    [0,0,1]
    [0,0,0]

4) compute Im + (Im - Im * average_filter(mean filter)) #where * is a convolution operation and Im is moon.png.


Part II (15%) Median and Gaussian filters

Read noisy.jpg corrupted with salt and pepper noise.
Apply a median filter to remove the noise.
Apply a Gaussian filter to the same noisy image.
You can use any scikit-image functions you like.
Which filter was more successful?
Part III (40%) An application of filtering in scikit-image: Simple image inpainting.

Write a program in scikit-image/Python to accomplish a simple image inpainting. This example and demo were shown in the lecture.

Use damage_cameraman.png and damage_mask.png.

It is an iterative algorithm. At every iteration, your program (a) blurs the entire damaged image with a Gaussian smoothing filter; then (b) with help of the mask image, restores only the undamaged pixels. Repeat these two steps (a) and (b) a few times until all damaged pixels are infilled.

