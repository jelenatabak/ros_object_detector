# ros_object_detector
The package is used for object detection inside the ROS environment. Python package [dodo_detector](https://github.com/douglasrizzo/dodo_detector) is used for inference. After detecting objects in RGB images, bounding boxes of detected objects are applied to the organised point cloud. The centroid of the detected object in the global frame is published.

## Running the code
``` bash
roslaunch ros_object_detector ros_object_detector.launch
```

## Subscribed topics
``/camera/color/image_raw`` ([sensor_msgs/Image](http://docs.ros.org/en/api/sensor_msgs/html/msg/Image.html)) <br />
  RGB image. <br />

``/camera/depth_registered/points`` ([sensor_msgs/PointCloud2](http://docs.ros.org/en/api/sensor_msgs/html/msg/PointCloud2.html) <br />
  Point cloud. <br />


## Published topics
``ros_object_detector/labeled_image`` ([sensor_msgs/Image](http://docs.ros.org/en/api/sensor_msgs/html/msg/Image.html)) <br />
  Image with bounding boxes. <br />

``ros_object_detector/detected_objects`` ([ros_object_detector/DetectedObjectArray]) <br />
  3D positions of detected objects. <br />


## Parameters
``ssd_confidence`` (*int*) <br />
  Confidence level to report objects as detected by the neural network, between 0 and 1. <br />

``image_topic`` (*string*) <br />
  
``point_cloud_topic`` (*string*) <br />
  
``camera_frame`` (*string*) <br />
  
``base_frame`` (*string*) <br />