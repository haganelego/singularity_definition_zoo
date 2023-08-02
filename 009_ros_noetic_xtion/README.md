# How to run Xtion pro Live

1. launch camera
```bash
source /opt/ros/noetic/setup.bash
roslaunch openni2_launch openni2.launch
```

2. visualize the image
```bash
source /opt/ros/noetic/setup.bash
# rgb
rosrun image_view image_view image:=/camera/rgb/image_raw
# depth
rosrun image_view image_view image:=/camera/depth/image_raw
```