# Milestone #1
Completion of Nodes for Milestone 1 with testing:
  1) Carl & Farwa - Master Node
  2) Patrick - IMU Node 
  3) Krystal & Brian - Control Node
  4) Gallop - Arduino Node (COMPLETED)

# node_ws

This repo contains catkin workspace containing the packages for ART

There is one package for all nodes called art_nodes in located node_ws/src/art_nodes

All cpp files should be saved in node_ws/src/art_nodes/src. It needs to be build, follow the ReadMe at node_ws/src/art_nodes

## For Future Reference

#### creating a workspace & package

Creating a workspace directory

`mkdir your_workspace`

The next code contains all the src code for the packages

`mkdir your_workspace/src`

Initialize workspace

`cd your_workspace/src`  
`catkin_init_workspace`

Create package. 

`catkin_create_pkg your_package_name roscpp std_msgs`

roscpp and std_msgs are dependencies added to CMakeList.txt and package.xml


#### compiling the node

After you created a node\_file.cpp in your\_package\_name, declare our node as a executable. In your\_workspace/src/your\_package\_name, add these lines in your CMakeList.txt:

`add_executable(desired_name src/node_file.cpp)`  
`target_link_libraries(desired_name ${catkin_LIBRARIES})`  

First line creates executable called desired_name, directs ROS to its source files. Second line specifies what libraries will be used.  

Build our workspace using catkin\_make command in the workspace directory

`cd your_workspace`  
`catkin_make`

Always source your setup.bash file in the workspace you have created. This script allows ROS to find the packages that are contained in your workspace.  

`source ./devel/setup.bash` 

start your node  

`rosrun your_package_name desired_name`



