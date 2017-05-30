## Project: Search and Sample Return
### Writeup Template: You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---


**The goals / steps of this project are the following:**  

**Notebook Analysis**  

* In [6] of the Notebook, I added two functions: `below_color_thresh()` and `in_between_color_threshs()`, to detect obstacles and rocks, respectively. In the former, I return a binary image when RGB is less than the threshold. For the latter, I check that RGB is between a bottom and a top thresholds.

[//]: # (Image References)

[image1]: ./output/rock01.png
[image2]: ./output/perspective01.png
[image3]: ./output/yellow_color_detection01.png
[image4]: ./output/autonomous01.png
![alt text][image1]
![alt text][image2]
![alt text][image3]

* For ground pixels, I changed the default threshold to (157, 142, 131), to improve fidelity in the autonomous mode.
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
* The following changes occurred in `perception_step()`:
* source and destionation points for perspective transform were added
* perspective transfom was done
* binary images of ground, obstacles and rock samples were obtained
* `Rover.vision_image` was updated with the aforementioned binary images
* Binary images of ground, obstacles and rock samples were transformed to rover coordinates
* Rover coordinates were transformed to world coordinates, using Rover state to obtained rover position and yaw
* Rover navigable angles and distances were filled in
* In `decision_step()` no changes were done, because when the navigable angles are filled in in the Rover state; `decision_step()` uses different checks as an implementation of the decision tree that was explained in the course.  
![alt text][image4]
