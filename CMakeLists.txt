##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 3.0.2)
project(rosjava_messages)

##############################################################################
# Catkin
##############################################################################

find_package(catkin REQUIRED genjava)

generate_rosjava_messages(
  PACKAGES
    std_msgs
    rosgraph_msgs            # ros/ros_comm_msgs
    std_srvs
    rosjava_test_msgs        # not released in melodic
    actionlib_msgs           # ros/common_msgs
    common_msgs
    diagnostic_msgs
    geometry_msgs
    nav_msgs
    sensor_msgs
    shape_msgs
    stereo_msgs
    trajectory_msgs
    visualization_msgs
    tf2_msgs                 # geometry_experimental/tf2_msgs
    #ar_track_alvar_msgs     # not released in noetic
    uuid_msgs                # ros-geographic-info/unique_identifier
    #yocs_msgs               # not released in noetic
    #concert_msgs            # not released in noetic
    #concert_service_msgs    # not released in noetic
    #gateway_msgs            # not released in noetic
    #rocon_app_manager_msgs  # not released in noetic
    #rocon_device_msgs       # not released in noetic
    #rocon_interaction_msgs  # not released in noetic
    #rocon_service_pair_msgs # not released in noetic
    #rocon_std_msgs          # not released in noetic
    #rocon_tutorial_msgs     # not released in noetic
    #world_canvas_msgs       # not released in melodic
    #scheduler_msgs          # not released in noetic
    move_base_msgs           # ros-planning/navigation
    map_store                # ros-planning/map_store

    roscpp                   # !!!!!!! REMOVE THIS ONCE https://github.com/ros-planning/navigation/pull/312 is fixed! !!!!!!!!
)

catkin_package()

##############################################################################
# Installation
##############################################################################

install(DIRECTORY ${ROS_MAVEN_DEPLOYMENT_REPOSITORY}/org/ros/rosjava_messages/
        DESTINATION ${CATKIN_GLOBAL_MAVEN_DESTINATION}/org/ros/rosjava_messages)
