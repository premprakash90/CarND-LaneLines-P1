# **Finding Lane Lines on the Road** 
---

### Reflection

### 1. The pipeline consisted of the following steps:  

1. Convert image to gray scale to facilitate edge detection. 
2. Apply Gaussian blur to smoothen the image to eliminate noise and unnecessary details from the image.
3. Apply canny detection to identify edges in the image. 
4. Mask the image so that only the region of interest is processed.   
5. Apply hough transforms on the region of interest to detect lane lines.
6. Classify lanes lines to left and right lanes.
7. Smoothen the result by averaging the slope and intercept 
8. Extrapolate the left and right line based on the top and bottom points obtained from average slope and intercept values
9. Plot the lines on top of the image 
 
### 2. Potential Shortcoming 

1. Assumes camera location is fixed. The region masking assumes the position of the camera and image size/format produced by the camera. It will not work for images obtained from a different position/angle/camera type.  
2. The lane detection does not work on images with bad lighting (night time, sunsets, showdows cast on lane lines etc) as gray scale only detects bright or dark spots. 
3. The lane line is assumed to be always straight and does not work on curved roads. 
4. The lane detection will fail if vehicles switching lanes hide the lane lines. 

### 3. Possible improvments 

Using HSV instead of RGB for images. HSV focuses on hue and saturation of images instead of bright or dark pixels which is better at handling images with bad lighting. 
