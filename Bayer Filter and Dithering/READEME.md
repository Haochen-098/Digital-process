(I) BasicBayer (60%):  In this part we reconstruct this RGB color image (this original color image is only for your reference, you will not use it inside your code) given a corresponding Bayer pattern image (your code takes the Bayer pattern as input). The Bayer pattern used is GRBG. In this part, the task is to reconstruct green, red and blue channels from the Bayer pattern image. The reconstruction of channels should be done using these Green, Red, and Blue image masks, where black color has been used for valid entries, and the white for empty entries. These masks together form the Bayer color pattern, viz., GRBG.

You should complete the provided template notebook. Interpolate the empty entries in the reconstructed green, red and blue channels independently of each other. Call the channels IG, IR, andIB respectively. Next, combine these channels into a full RGB color image and display this image. The output has to visually match this RGB color image.

The details about Bayer filter and the reconstruction process are provided in this document. You can also refer to the Wikipedia pages on Bayer filter and demosaicing.  In case you are interested in even more details, here's a nice reference: http://www.site.uottawa.ca/~edubois/lslcd/

As a simple scheme of pixel interpolation, you can follow these rules:

For reconstruction of the green channel IG, note with respect to the pattern Green that the green channel value at location B can be interpolated as:B = (A+C)/2. Similarly, E = (A+I)/2. For interpolating the green channel value at location G, use G = (F+C+H+K)/4, etc.
For reconstruction of the red channel IR, with respect to the pattern Red, use these rules of interpolation: C = (B+D)/2, F = (B+J)/2, G = (B+D+L+J)/4, etc. Note that for the red channel here, the first column and the last row are entirely empty. You need to fill them in by copying the second column and the second last row, respectively.
For reconstruction of the blue channel IB with respect to the pattern Blue, use these rules:F = (E+G)/2,I = (E+M)/2,J = (E+G+O+M)/4, etc. Notice that here the last column and the first row are entirely empty. So, fill them by copying to the second row and the last but one column, respectively.
(II) Floyd-Steinberg dithering (40%): 

Make a notebook that reads  this RGB image and implements a Floyd-Steinberg dithering to change the representation of this image. You should complete the provided template notebook. 

The template notebook

Dynamically calculates an N-colour palette for the given image (in the notebook the variable nColours determines the number of colours in the palette). 
Uses the KMeans clustering algorithm to determine the best colors.
Makes a kd-tree palette from the provided list of colors.
Applies the Floyd-Steinberg method to change the representation of the image.


More details about Dithering techniques can be found in the Wikipedia pages on Dither and Palette.
