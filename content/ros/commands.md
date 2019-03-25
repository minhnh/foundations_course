# ROS Commands 

## Environment variables
* `ROS_MATER_URI`: IP address of the ROS master, default value: `http://localhost:11311`

## Workspace setup with `python-catkin-tools`
* Make sure that no ROS environment is setup (i.e. no ROS specific environment variable like `ROS_MASTER_URI` exists).
  Sorting out the mess of workspace dependencies is more than it's worth. To check for ROS environment variable:
    ```
    env | grep -i ros
    ```
* Once the enviroment is clean (i.e. you do not get access to ROS and catkin commands like `roscd`), you can first
  source the system ROS environment:
    ```
    source /opt/ros/<ros version>/setup.bash
    ```
* In the local ROS workspace (if `~/catkin_ws/src` contains source packages, then `~/catkin_ws` is the ROS workspace),
  initialize the workspace with:
    ```
    catkin config --init
    ```
* The first few lines of the printed out message should be:
    ```
    Profile:                     default
    Extending:          [cached] /opt/ros/kinetic
    Workspace:                   /your/catkin/workspace
    ```
    Note the workspace now extend the system ROS packages.

## Topics and messages
For detailed information on ROS command line interface, please refer to ROS documentation for
[topics](http://wiki.ros.org/rostopic) and [messages](http://wiki.ros.org/rosmsg). Important commands include:
* `rostopic list`: list all topics on the current master
* `rostopic info <topic name>`: view message type, subscribers and publishers of a topic
* `rostopic echo <topic name>`: print all messages published on a topic
* `rostopic pub <topic name> <message type> <message>`: publish a message on a topic. Note that autocompletion is
  available for all fields, even the message to be published.
* `rosmsg info <message type>`: view all fields and their types in a message

## Services

## Action

