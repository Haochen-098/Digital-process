Part1. JPEG encoding (50 %)

In this part, you will implement a JPEG encoder. Download this image as your input. You should complete this notebook that has step by step explanation of what you need to write. For part 1, you should work on JPEG encoder section of the notebook. In the notebook, a Zigzag section is provided which contains two functions for zig-zag and inverse zig-zag scanning of an image.  

Following steps summarize what needs to be done in this part:

step 1) Compute number of blocks

step 2) Pad the image

step 3)  Encode:

divide image into 8-by-8 blocks
write 2D discrete cosine transform function using scipy.fftpack.dct function
apply 2D discrete cosine transform function to each block
reorder DCT coefficients in zig-zag order
reshaped it back to 8-by-8 block
step 4)  Write h, w, block_size and encoded image into text files

Part2. JPEG decoding (50 %)

In this part, you will implement a JPEG decoder. You should work on the JPEG decoder section of the notebook which explains what you need to complete step by step. 
Following steps summarize what needs to be done in this part:

step 5) Read h, w, block_size and encoded image from text files

step 6) 

Get size of the encoded image (H, W) 
Compute number of blocks
step 7)  Decode:

divide encoded image into 8-by-8 blocks
reshape it to one dimensional array (here: 64)
use inverse zig-zag to reorder the array into a block
write 2D inverse discrete cosine transform function usingscipy.fftpack.idctfunction
apply 2D inverse discrete cosine transform function
step 8)  Get the original size (h by w) image from the decoded image

