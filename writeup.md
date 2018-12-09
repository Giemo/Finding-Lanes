# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale. After that I blurred the image to get rid of unwanted noise in the image. Then I used canny to detect the edges of the blurred image. Afterwards I create a region of interest, which consists of a polygon with four points. Next I used the detected edges to calculate the Hough lines, which reflect the lanes on the road.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function. Therefor I calculated the slope of the edges, because a negative slope refers to the left lane and a positive slope refers to a right lane. After that I calculated the dot product for all the left lines and right lines respectively, to draw them on the image.



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the car enters a curve. Depending on the curvature the region of interest may not be sufficient to detect the right lane markings.

Another problem is the abscence of lane markings. If there are no lane markings the edge detection doesn't occur.

A third shortcoming could be that there are too many lanes (due to a construction or something similar). In this case the slope be highly fluctuating which inevitably results in a worse detection of lanes.



### 3. Suggest possible improvements to your pipeline

A possible improvement would be to make the region of interest adaptable. Widening the region of interest further down the road if no sufficient lane is found might be a good solution for the curvature problem. 

