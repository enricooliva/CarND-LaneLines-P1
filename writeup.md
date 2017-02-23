# Finding Lane Lines on the Road

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:
1. I converted the images to grayscale
2. I applied a Gaussian smoothing / blurring filter
3. I used a Canny edge detector to representing the edges on a black background
4. I defined a four sided polygon to mask the founded edge
5. I used Hough Line transform to detected the line

In order to draw a single line on the left and right lanes,
I modified the draw_lines() function by 2 operations
1. I divided the lines in two sets: left and right by calculating
the slope of each line
2. I calculated the regression line of each set
3. I draw the resulting regression line exploiting the mask polygon

If you'd like to include images to show how the pipeline works, here is how
to include an image:

![alt text][./example/result1.jpg]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when canny function return
only edge that represent the lane line, we could avoid the calculation of
regression line

Another shortcoming could be when the


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to avoid the Gaussian smoothing that is redundant
