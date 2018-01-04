## Project: Search and Sample Return
Autonomous rover locates rock samples and navigates environment by determining navigable terrain

---


**The goals / steps of this project are the following:**  

**Training / Calibration**  

* Download the simulator and take data in "Training Mode"
* Test out the functions in the Jupyter Notebook provided
* Add functions to detect obstacles and samples of interest (golden rocks)
* Fill in the `process_image()` function with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` created in this step should demonstrate that the mapping pipeline works.
* Use `moviepy` to process the images in the saved dataset with the `process_image()` function.  Include the video produced as part of the submission.

**Autonomous Navigation / Mapping**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook). 
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands. 
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

You're reading it!

### Notebook Analysis
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.


#### 1. Populate the `process_image()` function with the appropriate analysis steps to map pixels identifying navigable terrain, obstacles and rock samples into a worldmap.  Run `process_image()` on your test data using the `moviepy` functions provided to create video output of your result.  

### Autonomous Navigation and Mapping

#### 1. Fill in the `perception_step()` (at the bottom of the `perception.py` script) and `decision_step()` (in `decision.py`) functions in the autonomous mapping scripts and an explanation is provided in the writeup of how and why these functions were modified as they were.


#### 2. Launching in autonomous mode your rover can navigate and map autonomously.  Explain your results and how you might improve them in your writeup.  

Here I'll talk about the approach I took, what techniques I used, what worked and why, where the pipeline might fail and how I might improve it if I were going to pursue this project further.

My initial approach has simply been to complete the project. At the end of the term, I plan to come back to each project and expand beyond what is simply required to have a passing project. The only techniques that I used to complete this project are exactly those that were taught in this course. I performed perspective transform and color thresholds to scan pictures in real time and decide what to do next. We used each picture to determine a navigable angle direction and a distance (length of nav_angles) that represented what a navigable distance is. The rover had been given many default values including what was an appropriate distance for needing to stop, what was an appropriate max throttle and velocity, and etc. I compared the incoming nav_angle length generated from each picture to the values for stopping distance, so that my rover would stop and turn if necessary to produce a better navigable angle to pursue to further the mapping completion. Generally, the rover did not stop much. The rover simply changed angles and ran around. Eventually the map would become more and more complete with time (even if the rover was not smart enough to avoid areas already visited). I did not change any of these values and my rover seemed to navigate just fine. Changing some of these values may enable the rover to complete a full mapping of the environment much faster, but I have yet to play around with that. If I could improve my code to improve the rover, I would prvide a way for the rover to not visit areas it has already visited unless picking up a rock. Obviously,  another natural progression would be to get the rover to pick up all the rocks and bring them back to the point of origin.
 
#### Graphics Settings: 
* Screen resolution: 1024 x 768
* Graphics Quality: Good
* Windowed: Yes
* FPS: 33
