Part 2. Image Fusion with Scikit-Image/Python (35%)

You are given these two images A and B of the same scene but taken with different aperture and exposure settings for the camera. As a result, they show different levels of lighting. Your task is to fuse these images in such a way that the resulting image has good lighting in both the dark indoor and the relatively bright outdoor areas.  However, this should be done in such a way that the overall image still looks natural and believable. 

Fuse these two images with wavelets using Skimage-Python. You need to use this template. Detailed instructions are provided in the code as comments and you only need to modify the function WaveletFusion(C1, C2) and part of the last cell in the code. 

Code execution time is around 10 - 15 seconds so you need to wait a bit to get the output image.

The resulting blended image should look better than any of the individual shots. This image is provided as a general reference to what you should be aiming for.

Part 3. Object detection using Generalized Hough transform (40%)

Hough Transform is a popular technique to detect any shape in an image if you can represent that shape in a mathematical form. It can detect the shape even if it is broken or distorted a little bit. You can read more about Hough transform here and generalized Hough transform here (original paper).

For this part, you need to detect the shape in this reference image within this input image using generalized Hough transform with scikit image. You can learn more about Hough circle transform APIs in scikit from here. The output should be something like this, i.e, you should mark the given reference shape in the input image.

You need to complete this template. 
