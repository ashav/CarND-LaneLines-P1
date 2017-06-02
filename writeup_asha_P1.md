# **Finding Lane Lines on the Road**

---

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
---
## Pipeline

The following pipeline has been created.
1. Color Selection

---
## Original Images

<img src="./test_images/solidWhiteCurve.jpg" width="250" /> <img src="./test_images/solidWhiteRight.jpg" width="250" />
<img src="./test_images/solidYellowCurve.jpg" width="250" /> <img src="./test_images/solidYellowCurve2.jpg" width="250" />
<img src="./test_images/solidYellowLeft.jpg" width="250" /> <img src="./test_images/whiteCarLaneSwitch.jpg" width="250" />

---
## Color Selection

### RGB Color Space

The following are the color selection bitmaps for the RGB color space. White color is relatively easy to segment in the RGB domain (e.g. values in range [190,190,190] to [255,255,255]). Yellow is harder in the RGB space (Pure yellow in the RGB space is [255,255,0]). As shown below, white works well, but yellow does not. Also as the RGB color space is additive and does not separate luminance and chrominance, there could be issues as it gets darker. So we explore alternate color spaces.

<img src="./test_images_output/solidWhiteCurve_color_select_rgb.jpg" width="250" /> <img src="./test_images_output/solidWhiteRight_color_select_rgb.jpg" width="250" />
<img src="./test_images_output/solidYellowCurve_color_select_rgb.jpg" width="250" /> <img src="./test_images_output/solidYellowCurve2_color_select_rgb.jpg" width="250" />
<img src="./test_images_output/solidYellowLeft_color_select_rgb.jpg" width="250" /> <img src="./test_images_output/whiteCarLaneSwitch_color_select_rgb.jpg" width="250" />

### HLS Color Space

HSL stands for _hue_, _saturation_ and _luminosity_. More details on HLS and HSV color spaces are here at [Wikipedia](https://en.wikipedia.org/wiki/HSL_and_HSV)

As shown below, both yellow and white lines are clearly visible in the HLS color space.

<img src="./test_images_output/solidWhiteCurve_hls.jpg" width="250" /> <img src="./test_images_output/solidWhiteRight_hls.jpg" width="250" />
<img src="./test_images_output/solidYellowCurve_hls.jpg" width="250" /> <img src="./test_images_output/solidYellowCurve2_hls.jpg" width="250" />
<img src="./test_images_output/solidYellowLeft_hls.jpg" width="250" /> <img src="./test_images_output/whiteCarLaneSwitch_hls.jpg" width="250" />

### HSV Color Space

HSV stands for _hue_, _saturation_ and _value_. Same link as above.

Unlike HSL color space, while yellow is clearly visible, white lines are not as sharp in HSV color space. So between HSL and HSV color space, we select HSL color space to filter yellow shades.  

<img src="./test_images_output/solidWhiteCurve_hsv.jpg" width="250" /> <img src="./test_images_output/solidWhiteRight_hsv.jpg" width="250" />
<img src="./test_images_output/solidYellowCurve_hsv.jpg" width="250" /> <img src="./test_images_output/solidYellowCurve2_hsv.jpg" width="250" />
<img src="./test_images_output/solidYellowLeft_hsv.jpg" width="250" /> <img src="./test_images_output/whiteCarLaneSwitch_hsv.jpg" width="250" />

### HLS Color Selection Bitmaps

Here we use color selection in the HLS color space. For yellow color, we restrict Hue to be in the range 10-40. There is no effect on luminance and we use Saturation between 100 and 255 to not deal with darker shades. For white, we make sure that luminance is high (between 200 and 255) while hue and saturation have no effect.
 
 Compared to RGB color space, HLS does a much better job selecting yellow colors.  We stick to HLS color space going forward.
 
<img src="./test_images_output/solidWhiteCurve_color_select_hls.jpg" width="250" /> <img src="./test_images_output/solidWhiteRight_color_select_hls.jpg" width="250" />
<img src="./test_images_output/solidYellowCurve_color_select_hls.jpg" width="250" /> <img src="./test_images_output/solidYellowCurve2_color_select_hls.jpg" width="250" />
<img src="./test_images_output/solidYellowLeft_color_select_hls.jpg" width="250" /> <img src="./test_images_output/whiteCarLaneSwitch_color_select_hls.jpg" width="250" />



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
