# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are and act as our constant reference for where to steer the vehicle. The project detects lane lines in images using Python and OpenCV.

Prerequisites 
---

## If you have already installed the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) you should be good to go!   If not, you should install the starter kit to get started on this project. ##

Installation
---

To create an environment for this project use the following command:
```
conda env create -f environment.yml
```

After the environment is created, it needs to be activated with the command:
```

source activate carnd-term1
```

and open the project's notebook P1.ipynb inside jupyter notebook:
```
jupyter notebook P1.ipynb
```

Overview 
---

The pipeline consists of the following steps: 

1. Convert image to gray scale to facilitate edge detection 
2. Apply Gaussian blur to smoothen the image to eliminate noise and unnecessary details from the image
3. Apply canny detection to identify edges in the image 
4. Mask the image so that only the region of interest is processed   
5. Apply hough transforms on the region of interest to detect lane lines
6. Classify lanes lines to left and right lanes.
7. Smoothen the result by averaging the slope and intercept 
8. Extrapolate the left and right line based on the top and bottom points obtained from average slope and intercept values
9. Plot the lines on top of the original image 
