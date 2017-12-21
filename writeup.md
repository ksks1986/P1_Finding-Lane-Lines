# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 

First, I converted the images to grayscale, then I applied the Gaussian filter to the images,  and applied Canny edge detection.
Next, I masked the images to region of interest, then I take Hough transform to the images.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function.
First, the sign of each line's slope /////


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be the false recognition when the car run in the winding road.
And another shortcoming would be the false recognition when the car run in the low contrast road like dark road or almost disappearing line of road.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to apply the preprocessing before using Canny edge detection.
This preprocess makes images into the high contrast images for finding dark load more successfully.
