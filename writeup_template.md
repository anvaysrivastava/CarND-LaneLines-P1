
**Finding Lane Lines on the Road**
## How to Run
* Run Notebook
* Create a folder output inside test_images
* Inside Notebook Cell -> Run All 

## Steps of Pipeline

The Pipeline for video is a superset of pipeline for image.
###The steps I have taken to create lanes in image are
* Convert to Gray Scale.
* Add Blur using gaussian_blurr
* Detect edge using canny edge detection.
* Get Hough Transform and plot average lane lines
* convert each line into Y=mX+b
* if the slope is in acceptable range, then process that line as part of lane.
* Split lines into +ve and -ve slopes, since there will be two lanes. Calculate average lane slope and "distance from origin"(bias) for each cluster.
* plot the average lane lines of two clusters.

###Additional steps for Video are
* Init global average lane values for the two lines.
* For the present frame, calculate lane lines.
* Have a weighted sum of average lane lines and present frame's lane lines.
* Plot the new average.

## Shortcoming of present pipeline
* Hard coded to have 2 lanes.
* Hard coded that the camera perspective will be in the middle of the lane.
* Edge detection not working properly on the change of shadow/road texture.


## Possible improvements to pipeline.
* Higher contrast in videos for better edge detection.
* Better logic of creating clusters of lane lines, rather than filtering based on slopes.
