# Intel RealSense Gazebo/ROS
Intel Realsense Tracking and Depth camera simulations and URDF macros.

## FORK

This fork changes the realsense D435 model in `gazebo` to publish
`sensor_msgs/Pointcloud2` messages under the topic `depth/color/points`.
The change is made by setting this [tag](https://github.com/nilseuropa/realsense_ros_gazebo/blob/f3656354c737f421a8fad91bd26b5a7cbb8ddb80/xacro/depthcam.xacro#L239) to **true**.


## RealSense T265 ##

![](doc/t265.png)

### Usage ###
```xml
<xacro:include filename="$(find realsense_ros_gazebo)/xacro/tracker.xacro"/>

<xacro:realsense_T265 sensor_name="camera" parent_link="base_link" rate="30.0">
  <origin rpy="0 0 0" xyz="0 0 0.5"/>
</xacro:realsense_T265>
```

### Publishers ###
* /camera/**fisheye1**/*
* /camera/**fisheye2**/*
* /camera/**gyro**/sample _( accel and gyro are in the same imu message )_
* /camera/**odom**/sample



## RealSense R200 ##

![](doc/r200.png)

### Usage ###
```xml
<xacro:include filename="$(find realsense_ros_gazebo)/xacro/depthcam.xacro"/>

<xacro:realsense_R200 sensor_name="camera" parent_link="base_link" rate="30.0">
  <origin rpy="0 0 0" xyz="0 0 0.5"/>
</xacro:realsense_R200>
```

### Publishers ###

* /camera/**color**/*
* /camera/**depth**/*
* /camera/**infra1**/*
* /camera/**infra2**/*



## RealSense D435

![](doc/d435.png)

### Usage ###

```xml
<xacro:include filename="$(find realsense_ros_gazebo)/xacro/depthcam.xacro"/>

<xacro:realsense_d435 sensor_name="d435" parent_link="base_link" rate="10">
  <origin rpy="0 0 0 " xyz="0 0 0.5"/>
</xacro:realsense_d435>
```

### Publishers ###

* /camera/**color**/*
* /camera/**depth**/*
* /camera/**infra1**/*
* /camera/**infra2**/*
