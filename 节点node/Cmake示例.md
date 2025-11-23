---
date: 2025-11-22
tags:
  - node
  - Cmake
---
新建`CMakeLists.txt`，输入下面内容，以编译c++
````
cmake_minimum_required(VERSION 3.22)

project(first_node)

# add_executable - 生成first_node可执行文件
add_executable(first_node first_ros2_node.cpp)
	<创建的可执行文件名> <源文件名>

#查找rclcpp头文件和库文件路径
find_package(rclcpp REQUIRED) REQUIRED表示是必须的

#给可执行文件链接库文件 
target_link_libraries（ros2_cpp_node ${rclcpp_LIBRARIES}） 
<可执行文件名> <库文件名> 添加需要动态链接库

#给可执行文件包含头文件
target_include_directories(ros2_cpp_node PUBLIC ${rclcpp_INCLUDE_DIRS})
<可执行文件名> <头文件名>
