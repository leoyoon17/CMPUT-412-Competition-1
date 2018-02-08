## CMPUT 412 Competition 1: Pursuit & Evasion, By Jae-yeon (Leo) Yoon and Sumeyye Aydin ##

Objectives
==========

The general objective of the competition was to utilize the optical sensor on the Turtlebot, as well as smooth motion. More specifically, our team was to improve the wander behavior of our robot to swiftly manouver around the environment for the evasion portion of the competition. For the pursuit section of the competition, we were to use the optical sensor (Asus Xtion Pro Live) to track a moving target.


Background
==========
For the pursuit section of the competition we utilized the packages provided by OpenCV (Open source Computer Vision) to track the target.
Initially, the image collected by the optical sensor is converted/bridged into the array of values.
![Image Conversion](http://wiki.ros.org/cv_bridge/Tutorials/ConvertingBetweenROSImagesAndOpenCVImagesPython?action=AttachFile&do=get&target=cvbridge3.png)  

```python 
bridge = CvBridge() 
```

To actually track a moving target, the concept of Optical Flow was utilized (the pattern of apparnet motion of image objects between two consecutive frames caused by the movement of object or camera. Its good to note that the cv2 library comes with with code to easily utilize optical flow to track targets.

![Optical Flow](https://docs.opencv.org/3.3.1/optical_flow_basic1.jpg) 

```python
cv2.calcOpticalFlowPyrLK(prev_frame_gray, frame_gray, corners, None, **lk_params)
```

Finally, the concept of velocity ramping was used to ensure that we follow the target with little jerky movements.

