Part 1. Implement Minimum Following Watershed Algorithm (40%)
For this part, you need to complete the following two functions in the provided template.

     The function getSmallestNeighborIndex(img, row, col) is given, you'll need to call this function in getRegionalMinima(img) and iterativeMinFollowing(img, markers). You need to finish writing these two functions by yourself.

getRegionalMinima(img) : This function computes the local minima in the given image by comparing each pixel in the image to its 8-connected neighbors and marking it as a local minimum if its value is smaller than all of them.
The output of this function is a 32 bit integral image that contains non-zero labels for all local minima pixels and zero everywhere else.
You cannot use scipy.ndimage.filters.minimum_filter for this part.
This function is used to generate markers for the next function. 
iterativeMinFollowing(img, markers):  This function uses the minimum following algorithm to label the unlabeled pixels in the marker image generated by the previous function.
The steps described in the lecture notes are difficult to implement without recursion so you will instead be implementing an iterative variant of this algorithm that performs multiple passes over the image. In each pass, the entire image is traversed pixel by pixel and following steps are performed for each pixel p :
If p is already labeled (i.e. it has a non zero value), leave it unchanged
Otherwise, find the pixel with the smallest intensity value in the 8 connected neighborhood of p
If the smallest neighbor has a non zero label, mark p with its label; otherwise, leave it unchanged
Move to the next pixel and repeat steps 1 - 3.
Perform steps 1-4 for all pixels in the image while maintaining a count of the number of unlabeled pixels. Print this count after each pass is over.
If the count is zero after a pass, the entire image has been labeled and you are done. Otherwise, perform another pass over the image. This count should decrease in each successive iteration. If it does not, then there must be a bug in either this function or in getRegionalMinima that was used for generating the markers.
This function should return the final labeled image which must also be in 32 bit integral format like the input markers. You should not modify the contents of the markers directly - first make a copy and then write any changes there.

These two functions have been used in both part1 and part2. 
The program reads a 6x5 matrix from lab7_part1.txt which is identical to the one used in the lecture notes and will serve as a test image for your functions. The program prints both the initial markers generated by getRegionalMinima and the final labeled matrix produced by iterativeMinFollowing. Its output should look like this:
test_img:
[[ 10 100  20   2  15]
 [ 75   6  30  11   3]
 [ 19  43  38  45   5]
 [  1  22   0  17 100]
 [ 12   7   5 100  88]
 [ 16  66  59  44  23]]
test_markers:
[[0 0 0 1 0]
 [0 2 0 0 0]
 [0 0 0 0 0]
 [3 0 4 0 0]
 [0 0 0 0 0]
 [0 0 0 0 5]]
test_labels:
[[2 2 1 1 1]
 [2 2 1 1 1]
 [3 4 4 4 1]
 [3 4 4 4 1]
 [3 4 4 4 4]
 [4 4 4 4 5]]


Part 2. Image reconstruct and draw their boundaries (40%)

For this part, you need to add code to the provided template at the indicated locations.

1. Complete the function imreconstruct(marker,mask). This function performs morphological reconstruction of the image marker under the image mask, and returns the reconstruction in imreconstruct. The elements of marker must be less than or equal to the corresponding elements of mask. If the values in marker are greater than corresponding elements in mask, then imreconstruct clips the values to the mask level before starting the procedure. The function imimposemin(marker,mask) is given in the template. This function can revise the image to minimize pixel values in some regions.

2. Use find_contours() to find the contour of img_grad_min_imposed, show the contour. (It should look like this image)
