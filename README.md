# Launch file Descriptions:

## display.launch

1. Launches robot+mounted lidar in a rviz/basic_display configuration in RViz
2. Used to check and verify visualization
3. Command to launch:"roslaunch robot_urdf display.launch"

## gazebo.launch

1. Launches just the robot in a empty gazebo world
2. Used to verify robot spawning in gazebo
3. Command to launch:"roslaunch robot_urdf gazebo.launch"

## teleop.launch 

1. Launches robot+lidar in the competition_arena world, with gazebo sim paused
2. Used with car_teleop package to control the car using a keyboard
3. Command to launch:"roslaunch robot_urdf teleop.launch"
4. It also launches an rviz window which already where lidar scans are visualized
5. Unpause gazebo sim to solve error on RVIZ

## subscriber.launch 

1. Launches robot+lidar in the empty world, with gazebo sim paused
2. Used with open_loop_controller package to make the robot run in a straight line
3. Command to launch:"roslaunch robot_urdf subscriber.launch"

# How to build

1. cd to workspace folder and run "catkin_make"
2. if everything builds successfully (unless you have dependency issues), you can run any launch files

# How to Use

1. Use display.launch(roslaunch robot_urdf display.launch) to visualize robot_lidar in rviz, use the joint_state_publisher_gui to move nodes
2. Use gazebo.launch(roslaunch robot_urdf gazebo.launch) to spawn JUST THE ROBOT in gazebo
2. For Teleop , run this package's teleop.launch file first(roslaunch robot_urdf teleop.launch),once gazebo spawns the world,model and controller,unpause gaz sim, and then open another terminal and type "roslaunch car_teleop teleop.launch".
3. For Simple Pub-Sub, run the subscriber.launch file first(roslaunch robot_urdf subscriber.launch),once everything spawns properly, unpause the sim, open another terminal and run "roslaunch open_loop_controller command_publisher.launch", this should make the robot go in a straight line. To subscribe to the controller command topics, run "roslaunch open_loop_controller command_subscriber.launch"