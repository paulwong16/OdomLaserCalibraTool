# laser-odom_calibration

## 1. Prerequisites

1. ubuntu 16.04 + ROS Kinetic

2. Eigen3

## 2. Usage

```
    cd catkin_ws/src
    git clone https://github.com/MegviiRobot/OdomLaserCalibraTool
    cd ..
    catkin_make
    source devel/setup.bash
    roslaunch example.launch
```

__INPUT:__

A rosbag includes laser scan and odometer data(left & right wheels' velocity). Please check the topic name with launch file.

*Note that we use rostopic type geometry_msgs::Vector3Stamped to record odometer's raw data, for other types please modify the [code](https://github.com/MegviiRobot/OdomLaserCalibraTool/blob/master/src/io.cpp#L72).

__OUTPUT:__

Extrinsic parameters between LiDAR and odomter(x, y, yaw), intrinsic paramters of odomter(left & right wheels' radius, track between two wheels) and related uncertainty analysis.

e.g.

<img src="https://github.com/MegviiRobot/OdomLaserCalibraTool/blob/master/result.png" alt="result" />

## 3. Authors

1. Zhijie WANG, fomer research intern at Megvii, received B.Eng from Beijing University of Posts & Telecommunications, currently a master student in University of Waterloo, contact with &lt;paul dot wangzhijie at outlook dot com&gt; if you have questions with code.

2. Yijia HE, you can find the chinese version [in his homepage](https://blog.csdn.net/heyijia0327/article/details/88571176), if you have any question, please contact &lt;heyijia at megvii dot com&gt;.

3. Xiao Liu, [his homepage](http://www.liuxiao.org/)

## 4. References

Censi, Andrea, Franchi, Antonio, Marchionni, Luca & Oriolo, Giuseppe (2013). Simultaneous calibration of odometry and sensor parameters for mobile robots. IEEE Transactions on Robotics, 29, 475-492.
