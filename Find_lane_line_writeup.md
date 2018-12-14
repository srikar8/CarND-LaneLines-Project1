# Project 1
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

# Finding Lane Lines on the Road

### My Pipeline consisted of 6 steps:

1. Converting  image to grayscale image using the grayscale() function.
2. Applying Gaussian blur on the image using the gaussian_blur() function.
3. Applying canny edge detection for detecting edges using canny() function.
4.  The image is masked to extract the required part and remove unwanted area to find the lane in the image using the region_of_interest() helper function.
5. Hough transform is used to detecting the lines which are in same slope.  draw_lines() function is used to add lines over the lanes in the image and extrapolate them.
6. Final step is to merge modified image and original image to get the result using weighted_img() function.

------

### Output Images with extrapolated lane lines:

![](output_test_images/output_test_image_0.jpg?raw=true)

![](output_test_images/output_test_image_1.jpg?raw=true)

![](output_test_images/output_test_image_2.jpg?raw=true)

![](output_test_images/output_test_image_3.jpg?raw=true)

![](output_test_images/output_test_image_4.jpg?raw=true)

![](output_test_images/output_test_image_5.jpg?raw=true)



------

### Modification of draw_line() helper function:

The draw_lines() function has to be modified to extrapolate/average/connect the lane lines. For drawing lane lines, I divided the image to two half i.e., slope > 0.5 (right lane) and slope<-0.5 (left lane). Stored all the divided lines points in the respective filtered line points list. Calculated the maximum distance , slope and intercept. Using slope and intercept plotted the lane lines.

------

### Potential shortcomings with my current pipeline:

It gives wrong results during turning and if it detects any other line segment other than marked lines the result will be fluctuating. 

------

### Possible improvements:

Improvements to be done to draw the curved lane lines during turnings. Lanes should be detected more efficiently  to avoid detecting other lines on the road.