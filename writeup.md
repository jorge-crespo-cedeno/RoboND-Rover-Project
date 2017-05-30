## Project: Search and Sample Return
### Writeup Template: You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---


**The goals / steps of this project are the following:**  

**Notebook Analysis**  

* In [6] of the Notebook, I added two functions: `below_color_thresh()` and `in_between_color_threshs()`, to detect obstacles and rocks, respectively. In the former, I return a binary image when RGB is less than the threshold. For the latter, I check that RGB is between a bottom and a top thresholds. For ground pixels, I changed the default threshold to (157, 142, 131), to improve fidelity in the autonomous mode.
* In [9], the cell for the `process_image()` function, I defined the source and destination for the perspective transform. These values where obtained in the pre-processing steps. Then, I used the previouly defined functions:
- `perspective_transform()`
- `color_thresh()`
- `below_color_thresh()`
- `in_between_color_thresh()`
Each of them has been previouly described.
* Then, I transformed to rover coordinates the images obtained in `color_thresh()`-ground-, `below_color_thresh()`-obstacles-, `in_between_color_thresh()`-yellow rocks-.
* Afterwards, the rover coordinates were transformed to world coordinates using the rover position in the world, obtained from the Databucked (defined in [8]).
* The video output is included in the submission and here:
[![Watch the video](./calibration_images/example_rock1.jpg)](./output/test_mapping.mp4)

**Autonomous Navigation / Mapping**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook). 
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands. 
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  

[//]: # (Image References)

[image1]: ./misc/rover_image.jpg
[image2]: ./calibration_images/example_grid1.jpg
[image3]: ./calibration_images/example_rock1.jpg 

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

You're reading it!

### Notebook Analysis
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.
Here is an example of how to include an image in your writeup.

![alt text][image1]

#### 1. Populate the `process_image()` function with the appropriate analysis steps to map pixels identifying navigable terrain, obstacles and rock samples into a worldmap.  Run `process_image()` on your test data using the `moviepy` functions provided to create video output of your result. 
And another! 

![alt text][image2]
### Autonomous Navigation and Mapping

#### 1. Fill in the `perception_step()` (at the bottom of the `perception.py` script) and `decision_step()` (in `decision.py`) functions in the autonomous mapping scripts and an explanation is provided in the writeup of how and why these functions were modified as they were.


#### 2. Launching in autonomous mode your rover can navigate and map autonomously.  Explain your results and how you might improve them in your writeup.  

**Note: running the simulator with different choices of resolution and graphics quality may produce different results, particularly on different machines!  Make a note of your simulator settings (resolution and graphics quality set on launch) and frames per second (FPS output to terminal by `drive_rover.py`) in your writeup when you submit the project so your reviewer can reproduce your results.**

Here I'll talk about the approach I took, what techniques I used, what worked and why, where the pipeline might fail and how I might improve it if I were going to pursue this project further.  



![alt text][image3]


