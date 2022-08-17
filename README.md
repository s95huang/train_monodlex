# train_monodle
The goal is to train and deploy monodle algorithm on kitti and waymo dataset~

## environment
```
Ubuntu 18.04
python 3.6
CUDA 10.2
torch 1.7.0
torchvision 0.8.0
```
## Kitti dataset
### Resnet 18 backbone (140 epos, 3 class , kitti dataset)
* about 6-7 hours on 2070 super @ batch size 8, speed is  1.69it/s
```
2022-08-17 03:31:38,449   INFO  Pedestrian AP@0.50, 0.50, 0.50:
bbox AP:65.6720, 57.3000, 49.5406
bev  AP:14.3654, 12.3060, 11.6397
3d   AP:12.4371, 11.6057, 10.6213
aos  AP:40.15, 34.84, 30.54
Pedestrian AP_R40@0.50, 0.50, 0.50:
bbox AP:65.2233, 54.5003, 47.4822
bev  AP:7.2939, 5.6527, 4.5247
3d   AP:5.6203, 4.2076, 3.6058
aos  AP:36.30, 29.83, 25.65
Pedestrian AP@0.50, 0.25, 0.25:
bbox AP:65.6720, 57.3000, 49.5406
bev  AP:33.6586, 27.9270, 25.4217
3d   AP:33.2143, 27.5061, 25.2415
aos  AP:40.15, 34.84, 30.54
Pedestrian AP_R40@0.50, 0.25, 0.25:
bbox AP:65.2233, 54.5003, 47.4822
bev  AP:30.3001, 24.0647, 20.0436
3d   AP:29.7611, 23.5589, 19.6174
aos  AP:36.30, 29.83, 25.65

2022-08-17 03:31:40,988   INFO  Car AP@0.70, 0.70, 0.70:
bbox AP:89.6000, 87.0448, 78.7389
bev  AP:21.2775, 18.3207, 15.3069
3d   AP:13.7657, 11.8388, 10.6541
aos  AP:88.02, 84.95, 75.73
Car AP_R40@0.70, 0.70, 0.70:
bbox AP:95.1267, 88.5063, 79.2598
bev  AP:19.8345, 15.5816, 13.4467
3d   AP:12.1202, 9.6084, 8.0617
aos  AP:93.28, 86.23, 76.04
Car AP@0.70, 0.50, 0.50:
bbox AP:89.6000, 87.0448, 78.7389
bev  AP:58.0345, 43.6686, 41.4915
3d   AP:48.8995, 39.9070, 35.1034
aos  AP:88.02, 84.95, 75.73
Car AP_R40@0.70, 0.50, 0.50:
bbox AP:95.1267, 88.5063, 79.2598
bev  AP:56.4260, 41.9960, 37.8249
3d   AP:48.6928, 37.1138, 32.4404
aos  AP:93.28, 86.23, 76.04

2022-08-17 03:31:42,955   INFO  Cyclist AP@0.50, 0.50, 0.50:
bbox AP:49.4907, 35.6401, 35.4868
bev  AP:10.7879, 9.0909, 9.0909
3d   AP:10.7656, 9.0909, 9.0909
aos  AP:25.98, 19.24, 19.08
Cyclist AP_R40@0.50, 0.50, 0.50:
bbox AP:48.0519, 32.1620, 31.1126
bev  AP:3.0462, 1.2454, 1.2505
3d   AP:3.0218, 1.2046, 1.2286
aos  AP:25.85, 17.83, 17.36
Cyclist AP@0.50, 0.25, 0.25:
bbox AP:49.4907, 35.6401, 35.4868
bev  AP:20.4650, 14.3344, 13.2231
3d   AP:20.0567, 14.1472, 13.0723
aos  AP:25.98, 19.24, 19.08
Cyclist AP_R40@0.50, 0.25, 0.25:
bbox AP:48.0519, 32.1620, 31.1126
bev  AP:15.4390, 8.0366, 7.1550
3d   AP:14.7953, 7.6394, 7.0004
aos  AP:25.85, 17.83, 17.36

```
The performance is lower since we switched from dcnv2 to resnet18

## pip3 list
```
absl-py                       0.15.0
actionlib                     1.12.1
angles                        1.9.12
bondpy                        1.8.5
cachetools                    4.2.4
camera_calibration            1.15.0
camera_calibration_parsers    1.11.13
carla                         0.9.13
catkin                        0.7.29
certifi                       2021.5.30
charset-normalizer            2.0.7
controller_manager            0.18.4
controller_manager_msgs       0.18.4
cv_bridge                     1.13.0
cycler                        0.10.0
Cython                        0.29.24
dataclasses                   0.6
decorator                     4.4.2
diagnostic_analysis           1.9.7
diagnostic_common_diagnostics 1.9.7
diagnostic_updater            1.9.7
dynamic_reconfigure           1.6.5
future                        0.18.2
gazebo_plugins                2.8.7
gazebo_ros                    2.8.7
gencpp                        0.6.5
geneus                        2.2.6
genlisp                       0.4.16
genmsg                        0.5.16
gennodejs                     2.0.1
genpy                         0.6.16
google-auth                   2.10.0
google-auth-oauthlib          0.4.6
grpcio                        1.47.0
idna                          3.3
image_geometry                1.13.0
imageio                       2.9.0
importlib-metadata            4.8.3
interactive-markers           1.11.5
joint_state_publisher         1.12.15
kdl-parser-py                 1.13.3
kiwisolver                    1.3.1
lanelet2-python               1.0.1
laser_geometry                1.6.7
llvmlite                      0.36.0
Markdown                      3.3.7
matplotlib                    3.3.4
message_filters               1.14.13
networkx                      2.5.1
numba                         0.53.1
numpy                         1.19.5
oauthlib                      3.2.0
opencv-python                 4.4.0.42
Pillow                        8.3.1
pip                           21.3.1
protobuf                      3.19.0
pyasn1                        0.4.8
pyasn1-modules                0.2.8
pyparsing                     2.4.7
python-dateutil               2.8.2
python_qt_binding             0.4.4
PyWavelets                    1.1.1
PyYAML                        5.4.1
qt-dotgraph                   0.4.2
qt-gui                        0.4.2
qt-gui-cpp                    0.4.2
qt-gui-py-common              0.4.2
requests                      2.27.1
requests-oauthlib             1.3.1
resource_retriever            1.12.7
rosbag                        1.14.13
rosboost-cfg                  1.14.9
rosclean                      1.14.9
roscreate                     1.14.9
rosgraph                      1.14.13
roslaunch                     1.14.13
roslib                        1.14.9
roslint                       0.11.2
roslz4                        1.14.13
rosmake                       1.14.9
rosmaster                     1.14.13
rosmsg                        1.14.13
rosnode                       1.14.13
rosparam                      1.14.13
rospy                         1.14.13
rosservice                    1.14.13
rostest                       1.14.13
rostopic                      1.14.13
rosunit                       1.14.9
roswtf                        1.14.13
rqt_action                    0.4.9
rqt_bag                       0.5.1
rqt_bag_plugins               0.5.1
rqt_console                   0.4.9
rqt_dep                       0.4.9
rqt_graph                     0.4.11
rqt_gui                       0.5.3
rqt_gui_py                    0.5.3
rqt_image_view                0.4.16
rqt_launch                    0.4.8
rqt_logger_level              0.4.8
rqt-moveit                    0.5.10
rqt_msg                       0.4.8
rqt_nav_view                  0.5.7
rqt_plot                      0.4.13
rqt_pose_view                 0.5.8
rqt_publisher                 0.4.8
rqt_py_common                 0.5.3
rqt_py_console                0.4.8
rqt-reconfigure               0.5.4
rqt_robot_dashboard           0.5.7
rqt-robot-monitor             0.5.14
rqt_robot_steering            0.5.10
rqt_runtime_monitor           0.5.7
rqt-rviz                      0.7.0
rqt_service_caller            0.4.8
rqt_shell                     0.4.9
rqt_srv                       0.4.8
rqt_tf_tree                   0.6.0
rqt_top                       0.4.8
rqt_topic                     0.4.11
rqt_web                       0.4.8
rsa                           4.9
rviz                          1.13.25
scikit-image                  0.17.2
scipy                         1.5.4
sensor-msgs                   1.12.8
setuptools                    59.6.0
six                           1.16.0
smach                         2.0.1
smach_ros                     2.0.1
smclib                        1.8.5
tensorboard                   2.7.0
tensorboard-data-server       0.6.1
tensorboard-plugin-wit        1.8.0
terminaltables                3.1.0
tf                            1.12.1
tf_conversions                1.12.1
tf2_geometry_msgs             0.6.5
tf2_kdl                       0.6.5
tf2_py                        0.6.5
tf2_ros                       0.6.5
tifffile                      2020.9.3
timm                          0.4.12
topic_tools                   1.14.13
torch                         1.7.0
torchaudio                    0.7.0
torchvision                   0.8.0
tqdm                          4.62.2
typing-extensions             3.10.0.2
urdfdom-py                    0.4.6
urllib3                       1.26.11
Werkzeug                      2.0.3
wheel                         0.37.1
xacro                         1.13.17
zipp                          3.6.0

```
