cmake_minimum_required(VERSION 3.15)
project(RBY1-Examples-Teleop)

find_package(Eigen3 3.4.0 REQUIRED)
find_package(rby1-sdk REQUIRED)

set(MODEL_PATH ${CMAKE_CURRENT_SOURCE_DIR}/model)

add_subdirectory(third-party)
add_subdirectory(cpp)