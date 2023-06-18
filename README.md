# Driver-Drowsiness-Detection

View The result.png to get the overview.

1.Model

We proposed a pre-trained shape predictor 68 face landmarks model officially released by dlib. The model is trained using the ibug 300W large face landmark dataset.The size of the model depends on the information/features we want to predict. the speed/accuracy of the model is best when it is trained with the i-bug 300W dataset. The machine learning algorithm used is the Ensemble of regression trees.

2.Face Detection

Face detection We will be using dlib shape predictor 68 face landmarks.dat to recognize the face of the driver. An application is installed in the infotainment system of the car which will take the live feed from the camera and analyze it. If the driver is found drowsy then it will play an alert sound using the car’s speakers. A camera is being installed in the dashboard of the car which starts working as soon as the car starts moving. It has an infrared ability which can monitor the driver during dark also. It will capture the live feed of the driver and send it to the analyzing application. In our analyzing model, we will be using the following functions: a.get frontal face detector()-It is used in detecting a face in a frame or image. b.shape predictor 68 face landmarks()-To predict key(x,y,z) coordinates of a given shape. During face detection, we will be using the following function: getFaceDirection()-It is used to analyze the face and detect the direction of the face. It is used to point out the nose tip, chin, left eye left corner, right eye right corner, left and right corner of the mouth. If the face is not in the straight direction an alert will be heard as ”SIT STRAIGHT”.

3.Mouth Detection

Mouth detection In this case, the mouth will be pointed out by 6(x,y) coordinates which will be starting from left most corner of the mouth and will be plotted clockwise. We will be using the same equation as used to calculate the eye aspect ratio to calculate the mouth aspect ratio. The threshold value of the mouth aspect ratio is 0.6. If we find a value that is more or equal to 0.6 then we can detect that the driver is yawning. we will be using the following function to monitor yawning: mouth aspect ratio()-In this function we will find the Euclidean distance of each point and find the mouth aspect ratio [9]. If the driver is found yawning then an alert ”Yawning” will be heard.

4.Eye Detection

Each eye will be pointed out by 6 (x,y) coordinates which will be starting from the leftmost corner of each eye and will be plotted clockwise as shown in Figure-3. There is an equation of EAR (shown later) that determines the relation between the width and the height of the given coordinates. The threshold value of the eye aspect ratio is 0.25, if the value dips down for 20 seconds then it will detect that the eyes are closed. We will be using the following function to detect whether the eye is closed or open: eye aspect ratio()-In this function we will find the Euclidean distance of each point that is plotted in the eye and find the aspect ratio of the eye . If the eye is closed then an alert ”Drowsiness Detected” will be heard.
