# **Finding Lane Lines on the Road**

---

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---
## Color Selection

The following is an example of color selction

<img src="./test_images_output/solidWhiteCurve_hls.jpg" width="250" /> <img src="./test_images_output/solidWhiteRight_hls.jpg" width="250" />
<img src="./test_images_output/solidYellowCurve_hls.jpg" width="250" /> <img src="./test_images_output/solidYellowCurve2_hls.jpg" width="250" />
<img src="./test_images_output/solidYellowLeft_hls.jpg" width="250" /> <img src="./test_images_output/whiteCarLaneSwitch_hls.jpg" width="250" />

The following are images with HSV

<img src="./test_images_output/solidWhiteCurve_hsv.jpg" width="250" /> <img src="./test_images_output/solidWhiteRight_hsv.jpg" width="250" />
<img src="./test_images_output/solidYellowCurve_hsv.jpg" width="250" /> <img src="./test_images_output/solidYellowCurve2_hsv.jpg" width="250" />
<img src="./test_images_output/solidYellowLeft_hsv.jpg" width="250" /> <img src="./test_images_output/whiteCarLaneSwitch_hsv.jpg" width="250" />




## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I ....

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image:

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ...

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
