(I) Affine Transformation

Rotation and Scaling are the specialization of affine transformation that can be applied on an Image. In this assignment, you will perform image Rotation and Scaling. You should complete the provided template notebook.

Read this color image

Create a Rotation transformation matrix T_r (90 degrees)

Create a Scale transformation matrix T_s (by two), as shown below, which scales the placement of the points in all directions.

Combine the transformations: The neat thing about affine transformations being essentially linear transformations is that you can combine the transformations and apply them in one step. To demonstrate this you should apply the dot product (matrix multiplication) of the previous two transformation matrices. 

Apply the combined transformations in one step to the spatial domain of the image data. (Do not use any built-in function to apply transformation)

Plot the image after applying the transformation. It should clearly show that the original image has been rotated 90 degrees clockwise and scaled up 2X. However, the result obviously diminished as you can easily see discontinuity in the pixel intensities.

Develop an implementation of nearest neighbour interpolation based on the backwards mapping, using the inverse of the transformation matrix T, of the pixel coordinates in the transformed image to find either the exact match or nearest neighbour in the original image. (You can use any built-in function for nearest-neighbour interpolation such as skimage.transform.warp)

(II)Use skimage-Python to merge two pictures 

In this exercise, you will need to write the code that can perform image stitching. You can complete this code or you can write everything from scratch. Download im1 and im2 for your use. There are a standard procedure and algorithm for image stitching, which can be briefly summarized as the following steps:

Step 1) Detect local features with BRIEF or ORB in the two images I1 and I2.You may use any other feature extractor like SIFT ,SURF.

Step 2) Perform feature matching between I1 and I2, based on (approximate) nearest neighbour search, to generate a set of putative matching feature pairs. Usually, the similarity or distance between two feature descriptors is considered as the metric for matching.

Apply further constraint, either geometrical or non-geometrical, to exclude outliers (wrong matches) and retain inliers (true matches).
Step 3) Compute the homography matrix between I1 and I2 based on the true matches. A homography matrix is a 3-by-3 matrix that defines the transformation between the two images, i.e.,

H12 * [x1, y1, 1]T = w * [x2, y2, 1]T

where (x1, y1) and (x2, y2) are the image coordinates of the matching features in the two images, H12 is the homography matrix and w is a scaler.

Step 4) Perform image stitching based on the homography matrix. Basically, you will need to calculate the new image coordinates for every pixel in I1, with respect to I2 coordinate system. If H12 is calculated correctly, you should expect that after transformation, the features in I1 now have the same coordinates to their correspondences in I2, i.e., they are translated to the matching places.

The resulting stitched image should look similar to this.

Note that step 3) and 4) could be correlated. To decide the inliers, we need a model H to see if the matches fit it. On the other hand, to obtain H, we need sufficient true matches to complete the estimation. This is a chicken-egg problem. Refer to RANSAC if you are interested.
