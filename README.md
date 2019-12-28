Udacity Robotics Software Engineer Nanodegree Project 2 Go Chase It by Michael Strobl

Submission Folder

    .Project2                          # Go Chase It Project
    ├── my_robot                       # my_robot package                   
    │   ├── launch                     # launch folder for launch files   
    │   │   ├── robot_description.launch
    │   │   ├── world.launch
    │   ├── meshes                     # meshes folder for sensors
    │   │   ├── hokuyo.dae
    │   ├── urdf                       # urdf folder for xarco files
    │   │   ├── my_robot.gazebo
    │   │   ├── my_robot.xacro
    │   ├── world                      # world folder for world files
    │   │   ├── myworld.world
    │   ├── CMakeLists.txt             # compiler instructions
    │   ├── package.xml                # package info
    ├── ball_chaser                    # ball_chaser package                   
    │   ├── launch                     # launch folder for launch files   
    │   │   ├── ball_chaser.launch
    │   ├── src                        # source folder for C++ scripts
    │   │   ├── drive_bot.cpp
    │   │   ├── process_images.cpp
    │   ├── srv                        # service folder for ROS services
    │   │   ├── DriveToTarget.srv
    │   ├── CMakeLists.txt             # compiler instructions
    │   ├── package.xml                # package info                  
    └──                              

Start the project

1- Build the project:
    
    $ cd ~/catkin_ws
    $ catkin_make


2- Launch the robot inside your world

    $ cd ~/catkin_ws
    $ source devel/setup.bash
    $ roslaunch my_robot world.launch

3- Add the following settings to the Rviz Integration (under _Displays_)

- Select odom for fixed frame
- Click the Add button and add RobotModel and your robot model should load up in RViz.
- add Camera and select the Image topic that was defined in the camera Gazebo plugin
- add LaserScan and select the topic that was defined in the Hokuyo Gazebo plugin

4- Run drive_bot and process image (in new terminal)

    $ cd ~/catkin_ws
    $ source devel/setup.bash
    $ roslaunch ball_chaser ball_chaser.launch 

5- Visualize
To visualize the robot’s camera images, you can subscribe to camera RGB image topic from RViz. Or you can run the rqt_image_view node:

    $ cd ~/catkin_ws
    $ source devel/setup.bash
    $ rosrun rqt_image_view rqt_image_view  

Now place the white ball at different positions in front of the robot and see if the robot is capable of chasing the ball!

Sources:

- Udacity Robotics Software Engineer Nanodegree Project 2
- For Gazebo materials: http://wiki.ros.org/simulator_gazebo/Tutorials/ListOfMaterials
