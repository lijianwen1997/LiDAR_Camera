# LiDAR_Camera_Compass

## Requirements
Ubuntu 20.04 and ROS Neotic

## Dependenices
```
sudo apt install -y                     \
    ros-$ROS_DISTRO-pcl-ros             \
    build-essential         \
    libeigen3-dev           \
    libjsoncpp-dev          \
    libspdlog-dev           \
    libcurl4-openssl-dev    \
```
## Compile 
```
catkin_make --cmake-args -DCMAKE_BUILD_TYPE=Release
```
## Record and replay
```
roslaunch ouster_ros record.launch bag_file:=/media/external/5_18_3
roslaunch ouster_ros replay.launch bag_file:=/media/external/5_18_3.bag.active
```

## Compass

```
python3 imu_pub.py 
```
Read data from Arduino and publish to `/imu` topic

## GPS
```
roslaunch ublox_gps ublox_device.launch
```
Publish to `/ublox/fix` and `/ublox/fix_velocity`
