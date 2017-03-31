# **Finding Lane Lines on the Road** 

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps: 

Pipeline Steps:
1. Read in and grayscale the image, use a flag to show current image
2. Apply Gaussian smoothing and blur grayscaled image with kernel size defined in helper functions
3. Apply Canny Edge detection with the Gaussian smooted image, and low_threshold and high_threshold params
4. Crop region of interest by using canny edge image and calculated vertices. It will mask edges of the image using cv2.fillPoly()
5. Apply Hough transform on masked edge-detected image using parameters defined in helped
6. Extrapolate the line segments and draw lines with plot_lines
7. Combine line image with original image to see how accurate the line annotations are.
![alt text][image1]

Modified the draw_lines function by also adding a `plot_line` helper function to map out full extent of lane.
Seperated line segments by slope to decide which segments are part of the left line vs the right line.


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen in curved lines on high ways, may produce unexpected results.
Another is the weather situation, I wonder how it would perform in rainy, snowy, or hail conditions. 

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to apply some sort of algorithms to improve over time from the amount information it receives. To keep extrapolating until 99.9999999% certainty level and provide more sample data to improve the model.
