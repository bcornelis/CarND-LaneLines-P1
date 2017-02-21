#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[writeup1]: ./writeup/0_writeup_original.jpg "Original"
[writeup2]: ./writeup/1_writeup_gray.jpg "Gray"
[writeup3]: ./writeup/2_writeup_gauss.jpg "Gauss"
[writeup4]: ./writeup/3_writeup_canny.jpg "Canny"
[writeup5]: ./writeup/4_writeup_regionofinterest.jpg "Region of interest"
[writeup6]: ./writeup/5_writeup_hough.jpg "Hough"
[writeup7]: ./writeup/6_writeup_final.jpg "Final"
---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consistd of the following steps:

####1 Load the original image
The sample image used to explain the pipeline is the following one:
![alt text][writeup1]

####2 Move to Gray-scale
Convert the color image to grayscale using the predefined _grayscale_ method. Operating on a grayscale image is important to apply the canny function later on, which will use the gradients of the grayscaled image.
![alt text][writeup2]

####3 Apply gauss filter
A gauss filter will blur the image to get better results in the canny filter
![alt text][writeup3]

####4 Canny filtering
The Canny function generated an image of dots.
![alt text][writeup4]

####5 Region of interest
The dots need to be converted now using the Hough filter to detect the lines. As we don't want to apply this detection on the full image, we'll define a region in the image to which we're sure the hough logic has to be applied. The area outside will be blanked out.
![alt text][writeup5]

####6 Hough filtering
The latest step is the Hough transformation. This transformation detects straight lines in the dots from the canny filter.
![alt text][writeup6]

####7 Final image
Finally, printing the result on the original image gives the following final result:
![alt text][writeup7]

###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
