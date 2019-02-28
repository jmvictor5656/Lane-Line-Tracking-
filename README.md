# **Finding Lane Lines on the Road** 


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

My PipeLine consists of 6 steps:

1. I took only the red part of the image and converted it into binary image.
2. Then I smoothed(blurred) the image.
3. Then, I detect the edges based on mean and standard deviation of image.
4. Then I through away the image part that is not required(masking).
5. Then I detect the left and right line and draw on a blank Image.
6. In the end I combined both raw image and image with lines drawn to get image with red line drawn on Lanes.

And also I am using a class to track the frames as in some frames lines are not detected properly.

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


When there is shaddow in image its hard to detect a Lane, which is causing issue when car passed through that part of road which consists of shadow.


### 3. Suggest possible improvements to your pipeline

1. If its possible to get other image components to detect the `shadow region` or the region with low light intensity then the pipeline can work in any weather condition or in any region.

2. I was trying with `S` part of `HLS` image and with that I combined `R` part of `RGB` image and I seen with `n=5`(number of frames) in my `Line` class and with that It was working good with `optional` video. But with first video it was failing as I was taking pixel values between (100, 255) but when I taken all pixel values between (0, 255),
it worked with both but I was not getting the same result, So I have to check more with that
