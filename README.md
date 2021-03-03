### Overview:

__Projects Goal:__ Tracking Snooker balls, generating 2D top view. <br />

__Environment:__ Jupyter Notebook, Python, OpenCV <br />

<br />
Final result should look like this: <br />

![input_output](/images/input_output_img.png)

#### Output video - [YouTube link](https://www.youtube.com/watch?v=RLief79B7YQ)
---

### General info:
<br />
In this project I created a model which detects Snooker balls in a video and generates a 2D version of the table.

input video: [YouTube link](https://www.youtube.com/watch?v=hw02UKK4Kb0&t=590s)

#### Steps:

For each frame:

1) Warp the perspective of the original frame.

2) Using HSV image to get color of table, mask the table, invert the mask to get image of masked objects on the table.

3) Finding contours of each object 

4) Filtering contours based on their shapes and sizes.

5) Calculating average color inside of each contour to get each balls color.

6) Drawing a colored ball for each contour at its center on a 2D generated table.

![steps image](/images/steps_image.png)


- for __designing the 2D table__ I just used cv2 functions `Circle` , `Line` . markdowns according to this [link](https://www.snookerbilliardspool.co.uk/TableMarking.asp)

<br />

### Overall:

The model can track the balls and generate a 2D version of the table, although the final output is not perfect. <br />
This is a simple model which does not know position of balls and does not remember balls locations, it only projects 'what it sees' no matter how many balls or what colors they are.


- more info and code can be found in the notebook - [`TrackingSnookerBalls.ipynb`](/TrackingSnookerBalls.ipynb)
