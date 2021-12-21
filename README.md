# ReadClockHand

Step 1: Extract the hour hand and the minute hand from the original analog clock 
image into two images by cropping, manual thresholding, and connected component algorithm
; hour hand image and minute hand image. The goals of clock hand extraction is that not to 
be confused in future angle calculation.

Step 2: Put the hour and the minute hand image into Canny edges to make the hand line thin.

Step 3: Put the hand edge image (both hour hand and minute hand) into hough transform (cv2.HoughLines)
algorithm to calculate the angles of hour and minute hands.

Step 4: Check the angles whether the hand is at the correct 
position or the hand is on the opposite position. If the hand 
is on the opposite direction (hands at > 6 ), need to plus 180 degree 
to the angle to get the actual angle.

Step 5: Get the actual angles (0<actual angle<360) from both hour and minute hand 
to calculate the time. Every 30 degrees increases 1 hour and every 6 degrees increases 1 minute. (hr angle/30,min angle/6)

# Requirements

Python 3.8

Opencv

Numpy

Matplotlib
